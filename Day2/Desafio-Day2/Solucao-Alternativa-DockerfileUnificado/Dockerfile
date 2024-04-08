FROM python:3.11.9-alpine3.19
WORKDIR /opt/app
RUN apk --update add redis && apk --update add git
ENV REDIS_HOST=localhost
RUN git clone https://github.com/badtuxx/giropops-senhas.git && mv giropops-senhas/* . \
    && printf "\nWerkzeug==2.3.7" >> requirements.txt \
    && pip install --no-cache-dir -r requirements.txt
RUN printf "#!/bin/bash \nredis-server --daemonize yes \nflask run --host=0.0.0.0" > /opt/app/entrypoint.sh
EXPOSE 5000
ENTRYPOINT ["sh","entrypoint.sh"]