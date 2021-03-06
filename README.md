# stuartfenton/docker-golang-base

Based on [`docker/golang`](https://index.docker.io/u/google/golang) but I have updated it to work with 1.5.0 as a [docker](https://docker.io) base image that bundles the latest version of [golang](http://golang.org) installed from [golang.org](http://golang.org/doc/install/).

It serves as a base for the [`stuartfenton/docker-golang-runtime`](https://index.docker.io/u/google/golang-runtime) image.

## Notes

`GOROOT` is set to `/goroot`
`GOPATH` is set to `/gopath`

## Usage

- Create a Dockerfile in your golang application directory with the following content:

        FROM stuartfenton/docker-golang-base

        WORKDIR /gopath/src/app
        ADD . /gopath/src/app/
        RUN go get app
        
        CMD []
        ENTRYPOINT ["/gopath/bin/app"]

- Run the following command in your application directory:

        docker build -t my/app .

# docker-golang-base
