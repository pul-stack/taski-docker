FROM python:3.10

WORKDIR /app

RUN pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org gunicorn==20.1.0

COPY requirements.txt .

RUN pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org --default-timeout=100 -r requirements.txt --no-cache-dir

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]

