FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app

COPY requirements.txt ./
RUN pip install --upgrade pip && pip install -r requirements.txt

COPY . .

# Собираем статику, если нужно
RUN python manage.py collectstatic --noinput

CMD ["uvicorn", "astrolis.asgi:application", "--host", "0.0.0.0", "--port", "8000"]
