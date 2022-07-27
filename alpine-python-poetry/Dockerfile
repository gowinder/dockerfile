FROM alpine:3.16

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/' /etc/apk/repositories
RUN apk update && apk --no-cache add alpine-sdk ca-certificates python3>=3.10 python3-dev>=3.10 curl
RUN python3 -m ensurepip
RUN pip3 install poetry==1.1.13

CMD ["python3"]


