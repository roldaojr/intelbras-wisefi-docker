FROM python:2.7-alpine
ENV PYTHONUNBUFFERED 1
ENV PORT 8000
ENV SECRET_KEY "dummy"
EXPOSE ${PORT}
LABEL name="wisefi-controller"

RUN mkdir /web
WORKDIR /web
COPY . /web/
RUN apk add jpeg zlib \
    && apk add --no-cache --virtual .build-deps \
        build-base \
        jpeg-dev \
        zlib-dev \
        linux-headers \
    && pip install -r requirements.txt \
    && apk del .build-deps
RUN python manage.py collectstatic --noinput
CMD sh -c "python manage.py migrate --noinput && python manage.py runserver --noreload 0.0.0.0:${PORT}"
