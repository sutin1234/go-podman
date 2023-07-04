# state build
FROM golang:alpine as builder
WORKDIR /go/src

COPY . .
RUN go get
RUN go build -o /go/bin/app

# state run copy from builder
FROM alpine
WORKDIR /go
COPY --from=builder /go/bin/app /app
ENTRYPOINT ["/app"]