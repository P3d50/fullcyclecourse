FROM golang as build
RUN export PATH=$PATH:/usr/local/go/bin
RUN go env -w GO111MODULE=off
WORKDIR /src
COPY hello.go .
RUN go build -o /app .
FROM scratch as bin
COPY --from=build app /
CMD ["/app"]