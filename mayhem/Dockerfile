# FROM fuzzers/go-fuzz:1.2.0
FROM golang:1.18 as builder

COPY . /timer
WORKDIR /timer

RUN go mod tidy
RUN go build

FROM debian:bookworm-slim
COPY --from=builder /timer/timer /