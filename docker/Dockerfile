FROM python:3.10

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

RUN addgroup --system web \
    && adduser --system --ingroup web web

USER web

WORKDIR /home/web/code

COPY --chown=web:web . ./

EXPOSE 8000

USER root
RUN pip install -r requirements/base.txt
RUN pip install -r requirements/prod.txt

USER web
RUN chmod +x ./launch_scripts/prod.sh

CMD ["./launch_scripts/prod.sh"]