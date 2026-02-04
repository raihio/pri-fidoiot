# Copyright 2020 Intel Corporation
# SPDX-License-Identifier: Apache 2.0

FROM ubuntu:22.04@sha256:c7eb020043d8fc2ae0793fb35a37bff1cf33f156d4d4b12ccc7f3ef8706c38b1

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get clean && apt-get -y update && apt-get -y upgrade && apt-get install -y --no-install-recommends openjdk-17-jdk maven git

# Create a user 'fdouser'. If the user name is updated, please update the same in docker-compose.yaml.
RUN useradd -ms /bin/bash fdouser
RUN mkdir -p /home/fdouser/pri-fidoiot/ ; chown -R fdouser:fdouser /home/fdouser/pri-fidoiot/
RUN mkdir -p /home/fdouser/.m2/; chown -R fdouser:fdouser /home/fdouser/.m2
USER fdouser

WORKDIR /home/fdouser/pri-fidoiot/
ENTRYPOINT ./build/build.sh
