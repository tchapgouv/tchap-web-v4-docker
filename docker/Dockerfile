# Builder
FROM node:16-buster as builder

RUN apt-get update && apt-get install -y git dos2unix

WORKDIR /src

COPY . /src
RUN yarn --network-timeout=100000 install

RUN dos2unix /src/scripts/package-github.sh && bash /src/scripts/package-github.sh

# Copy the config now so that we don't create another layer in the app image
RUN cp /src/config.sample.json /src/webapp/config.json

# App
FROM nginx:alpine

COPY --from=builder /src/webapp /app

# Override default nginx config
COPY /nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf

RUN rm -rf /usr/share/nginx/html \
  && ln -s /app /usr/share/nginx/html
