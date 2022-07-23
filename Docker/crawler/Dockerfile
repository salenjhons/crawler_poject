FROM python:3.6-alpine



#RUN apk add git=2.32.0-r0

ENV APP_HOME /app
COPY . /${APP_HOME}
WORKDIR /${APP_HOME}

ENV MONGO mongodb
ENV MONGO_PORT 27017
ENV RMQ_HOST rabbitmq
ENV RMQ_QUEUE crawler
ENV RMQ_USERNAME guest
ENV RMQ_PASSWORD guest
ENV CHECK_INTERVAL 20
ENV EXCLUDE_URLS '.*github.com'

#RUN git clone https://github.com/express42/search_engine_crawler.git ${APP_HOME}

RUN pip install -r ${APP_HOME}/requirements.txt 

CMD [ "python3","-u", "crawler/crawler.py", "https://vitkhab.github.io/search_engine_test_site/" ]