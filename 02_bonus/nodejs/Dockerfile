FROM node:7.4-alpine

ENV PATH /root/.yarn/bin:$PATH

RUN apk update \
  && apk add curl bash binutils tar \
  && rm -rf /var/cache/apk/* \
  && /bin/bash \
  && touch ~/.bashrc \
  && curl -o- -L https://yarnpkg.com/install.sh | bash \
  && apk del curl tar binutils

EXPOSE 3000

#docker build -t yarn .
#docker run -it --rm -p 3000:3000 yarn
# in order to start, copy some app (using COPY)
# CMD ["node","name of js file"] in Dockerfile
# or simply node <file> in it mode
