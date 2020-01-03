FROM python:3

COPY ./requirements.txt /usr/src/
COPY ./manage.py /usr/src/
COPY ./blog /usr/src/blog
COPY ./homepage /usr/src/homepage
COPY ./personal_website /usr/src/personal_website
COPY ./amazon_crawler /usr/src/amazon_crawler

WORKDIR /usr/src/

RUN pip install --upgrade pip && \
    pip install -r requirements.txt

CMD gunicorn personal_website.wsgi:application --bind 0.0.0.0:8000
