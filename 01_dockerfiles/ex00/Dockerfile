FROM alpine

LABEL maintainer="avolgin"

RUN apk update && apk add emacs

# Change entrypoint
ENTRYPOINT ["emacs"]

# to build image in current directory
# docker build -t <image_name> .
