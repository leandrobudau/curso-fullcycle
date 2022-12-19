FROM golang:1.19.4-alpine

WORKDIR /usrc/src/app

COPY go.mod ./

RUN go mod download && go mod verify

COPY . .

RUN go build -v -o /usr/local/bin/app .

CMD ["app"]