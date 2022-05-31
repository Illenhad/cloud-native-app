FROM golang:1.18-alpine AS build

WORKDIR /usr/src/app

COPY dispatcher.go .
RUN go build dispatcher.go

FROM alpine:3.16.0

EXPOSE 80

COPY static static/
COPY --from=build /usr/src/app/ .

CMD ["./dispatcher"]
