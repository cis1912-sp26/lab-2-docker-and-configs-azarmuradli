FROM python:3.10-slim

WORKDIR /service/app

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/


COPY services/notes/. .


COPY utilities /utilities


RUN uv sync --no-cache --link-mode=copy


CMD ["uv", "run", "fastapi", "dev", "main.py", "--host", "0.0.0.0", "--port", "8001"]