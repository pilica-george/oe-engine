FROM ubuntu:18.04

RUN apt-get update \
    && apt-get -y upgrade \
    && apt-get -y install make build-essential git jq vim curl wget

RUN echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ bionic main" | tee /etc/apt/sources.list.d/azure-cli.list

RUN wget https://packages.microsoft.com/keys/microsoft.asc
RUN apt-key add microsoft.asc

RUN apt-get update \
    && apt-get -y install apt-transport-https azure-cli

ENV GO_VERSION 1.11.1

RUN wget https://dl.google.com/go/go${GO_VERSION}.linux-amd64.tar.gz

RUN tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gz

ENV PATH "${PATH}:/usr/local/go/bin"
