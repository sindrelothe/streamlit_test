FROM python:3.8

RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | POETRY_HOME=/opt/poetry python && \
    cd /usr/local/bin && \
    ln -s /opt/poetry/bin/poetry && \
    poetry config virtualenvs.create false

WORKDIR /app

EXPOSE 80

COPY /pyproject.toml /poetry.lock* /app/

RUN poetry install --no-root --no-dev

ENV PYTHONPATH=/app


CMD ["streamlit", "run", "file1.py", "--server.port", "80"]
