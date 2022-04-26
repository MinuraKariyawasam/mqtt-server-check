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

# COMMANDS TO RUN
# 1) docker build -t toyota-data .
# 2) docker run -e MQTT_URL=mqtt-test.rahtiapp.fi -e MQTT_PORT=443 -e CLIENT_ID=student474 toyota-data
# 3) docker image tag toyota-data yourusername/toyota-data:1.0
# 4) docker image push yourusername/toyota-data:1.0



