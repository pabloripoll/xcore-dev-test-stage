ARG ALPINE_VERSION=3.9
ARG NODE_VERSION=10.16.3

FROM node:${NODE_VERSION}-alpine AS node
FROM alpine:${ALPINE_VERSION}

# Install main packages and remove default server definition
RUN apk add --no-cache \
  bash \
  g++ \
  git \
  make \
  openssl-dev \
  python \
  vim \
  nano \
  wget \
  build-base

# Configure NodeJS
COPY --from=node /usr/lib /usr/lib
COPY --from=node /usr/local/lib /usr/local/lib
COPY --from=node /usr/local/include /usr/local/include
COPY --from=node /usr/local/bin /usr/local/bin

RUN node -v

RUN rm -rf /usr/local/bin/yarn /usr/local/bin/yarnpkg
RUN npm install -g yarn --force
RUN npm -v
RUN yarn -v

# internxt
RUN npm install --global internxt/xcore-daemon && \
#npm cache clean && \
#apk del git openssl-dev python vim && \
#rm -rf /var/cache/apk/* && \
#rm -rf /tmp/npm* && \
xcore --version

# Create project root
RUN mkdir -p /var/www/htdocs

WORKDIR /var/www/htdocs

# Container ports
EXPOSE 4000 4001 4002 4003

CMD [""]