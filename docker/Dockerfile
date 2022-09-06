FROM python:3.10

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

RUN addgroup --system web \
    && adduser --system --ingroup web web

USER web

WORKDIR /home/web/code

COPY --chown=web:web . ./

RUN pip install -r requirements/base.txt