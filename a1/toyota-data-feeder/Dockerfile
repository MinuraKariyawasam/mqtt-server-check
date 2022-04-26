FROM python:3.8

WORKDIR /toyota-data

COPY /requirements.txt ./

RUN pip install -r requirements.txt

COPY /feeder.py ./
COPY /ca.crt ./
COPY /toyota_data.csv ./

# MQTT_URL=localhost MQTT_PORT=8883 CLIENT_ID=foo

ENV MQTT_URL=localhost
ENV MQTT_PORT=8883
ENV CLIENT_IDL=foo

CMD [ "python", "feeder.py" ]