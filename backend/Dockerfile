FROM python:slim-bullseye

WORKDIR /app
ADD main.py /app
ADD requirements.txt /app

RUN pip install -r requirements.txt

ENV api_url=""
ENV api_key=""

CMD python -u /app/main.py -api_url=$api_url -api_key=$api_key