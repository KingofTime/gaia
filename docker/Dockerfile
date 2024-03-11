FROM python:3.11.4

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY poetry.lock pyproject.toml /app/

RUN apt install python3-dev libpq-dev && \
 pip3 install poetry
RUN poetry install

COPY ./docker/entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

COPY . /app/

ENTRYPOINT [ "/entrypoint.sh" ]
