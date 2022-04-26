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
# 3) # sudo docker tag toyota-data docker-registry.rahti.csc.fi/student474/toyota-data:1.0
     # sudo docker push docker-registry.rahti.csc.fi/student474/toyota-data:1.0
# mosquitto_sub -h mqtt-test.rahtiapp.fi -p 443 -t 'student474/toyota/SPEED' --verbose --insecure and --cafile ca.crt