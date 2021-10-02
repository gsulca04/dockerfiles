FROM golang:1.16.8-alpine3.14 AS build

WORKDIR /src/
COPY hello-world.go go.* /src/
RUN CGO_ENABLED=0 go build -o /go/app

FROM scratch
COPY --from=build /go/app /go/app
ENTRYPOINT ["/go/app"]