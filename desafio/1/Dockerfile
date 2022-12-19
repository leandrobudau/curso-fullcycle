FROM golang:1.19.4-alpine AS builder

WORKDIR /usr/src/app

COPY *.mod .
COPY *.go .

RUN go build -o bin

# Optimized image
FROM scratch 

WORKDIR /app

COPY --from=builder /usr/src/app/bin .

CMD ["/app/bin"]