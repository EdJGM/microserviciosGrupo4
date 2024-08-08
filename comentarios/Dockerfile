FROM python:3
COPY . /app
COPY requirements.txt /app
WORKDIR /app
RUN pip install -r requirements.txt
CMD ["python", "main.py"]
