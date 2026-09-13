## Base Image
FROM python:3.8-slim

## Work Directory
WORKDIR /app

COPY requirements.txt .


## Install requirements
RUN pip install -r requirements.txt
## Copy source code
COPY . .

## Expose container port
EXPOSE 5001

## Execute Application
CMD ["python","app.py"]