FROM golang:alpine AS builder
WORKDIR /app
COPY ./hello.go /app
RUN go build -o goapp
ENTRYPOINT ["/app/goapp"]

FROM alpine:latest
COPY --from=builder /app/goapp /app/goapp
ENTRYPOINT ["/app/goapp"]
