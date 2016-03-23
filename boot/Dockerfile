FROM frolvlad/alpine-oraclejdk8:slim

ENV \
      # Set boot env vars
      BOOT_HOME=/.boot \
      BOOT_AS_ROOT=yes \
      BOOT_LOCAL_REPO=/m2

RUN \
      # Add boot (boot requires bash)
      apk add --no-cache bash && \
      apk add --no-cache --virtual=build-dependencies wget ca-certificates && \
      wget -O /usr/bin/boot https://github.com/boot-clj/boot-bin/releases/download/latest/boot.sh && \
      chmod +x /usr/bin/boot && \
      apk del build-dependencies && \
      mkdir /.boot && \
      mkdir /project

COPY boot.properties /.boot/boot.properties

# Runs boot to cache basic deps
RUN boot

# Directory the project
WORKDIR /project

ENTRYPOINT ["boot"]
