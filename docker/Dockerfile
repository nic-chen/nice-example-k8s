FROM golang:latest

COPY src/ $GOPATH/src/nice-example/

WORKDIR $GOPATH/src/nice-example

#删除重复的trace
#RUN rm -rf $GOPATH/src/go.etcd.io/etcd/vendor/golang.org/x/net/trace

RUN make build


ENTRYPOINT ["cmd/nice-example", "-c", "/go/src/nice-example/cmd/config.yaml", "all"]