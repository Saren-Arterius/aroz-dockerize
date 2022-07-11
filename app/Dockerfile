FROM golang:1.18.0-alpine
RUN apk add git
RUN git clone https://github.com/tobychui/arozos.git /arozos
WORKDIR /arozos/src
RUN git fetch && git checkout v1.123
RUN go build
RUN apk add util-linux ffmpeg
# CMD /arozos/src/arozos -port 80
