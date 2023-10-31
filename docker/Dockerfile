FROM python:3.11-slim

EXPOSE 5000

WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y unixodbc && rm -rf /var/lib/apt/lists/*

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt && rm requirements.txt

COPY start.sh .

RUN chown -R 1001 . && chown -R 1001 /usr/local/lib/python3.11/site-packages/mlflow

USER 1001

CMD [ "./start.sh" ]