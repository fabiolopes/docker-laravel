FROM golang:1.15.2-alpine3.12 as base

WORKDIR /go/src/hello

COPY src .

RUN go get -v ./...  \
    && go build -ldflags="-s -w"

FROM scratch as prod

COPY --from=base /go/src/hello/hello .

CMD ["/hello"]