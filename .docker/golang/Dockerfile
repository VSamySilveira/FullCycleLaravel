FROM golang:1.14 as builder

WORKDIR /go/src/app
COPY . .

RUN go get -d -v ./...
RUN go install -v ./...

WORKDIR /go/bin

RUN mv ./app ./codeeducation

FROM scratch

COPY --from=builder /go/bin/codeeducation /bin/codeeducation

ENTRYPOINT ["codeeducation"]