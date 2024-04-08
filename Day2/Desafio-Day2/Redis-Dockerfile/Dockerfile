FROM python:3.11.9-alpine3.19
RUN apk --update add redis
EXPOSE 6379
ENTRYPOINT ["redis-server", "--protected-mode", "no"]