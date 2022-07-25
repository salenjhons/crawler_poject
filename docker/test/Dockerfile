FROM python:3.6-alpine

ENV APP_HOME /app
COPY . /${APP_HOME}
WORKDIR ${APP_HOME}

RUN pip install -r requirements.txt -r requirements-test.txt && \
    python -m unittest discover -s tests && \
    coverage run -m unittest discover -s tests && \
    coverage report --include crawler/crawler.py
