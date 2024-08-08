FROM golang:alpine

WORKDIR /tester

RUN apk add --no-cache bash git make

RUN git clone https://github.com/informalsystems/tm-load-test.git

WORKDIR /tester/tm-load-test

RUN make