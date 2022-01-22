FROM python:3.8-slim-buster
WORKDIR /app
COPY requirements.txt .
RUN python -m pip install -r requirements.txt
COPY . /app
EXPOSE 5000
CMD ["gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "-c", "config.py", "app:app"]


FROM python:3.8-slim-buster
EXPOSE 5000
COPY requirements.txt .
RUN python -m pip install -r requirements.txt
WORKDIR /app
COPY . /app
CMD ["gunicorn", "--workers=1", "--bind", "0.0.0.0:5000", "app:app"]