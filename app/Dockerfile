FROM golang:1.19.0-alpine AS builder
WORKDIR /app
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build . && \
    chmod +x gocker

FROM hello-world:linux
COPY --from=builder /app/gocker /app/

ENTRYPOINT ["/app/gocker"]