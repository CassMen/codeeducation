FROM golang:alpine3.14 AS etapa1
WORKDIR /usr/src/app

RUN touch start.go
RUN echo '\
    package main; \
    import "fmt"; \
    func main() { \
        fmt.Println("Code.education Rocks!"); \
    } \
    ' >> start.go

RUN go mod init codeedu/start
RUN go build

#######
FROM scratch
COPY --from=etapa1 /usr/src/app start
WORKDIR /start
CMD [ "./start" ]