# kommandoer 

## start med at builde docker compose

    docker-compose build

## Start docker compose

med den lokale `docker-compose.yml"

    docker compose up -d   

## Abonner på alle topics i Mosquitto

    docker run --rm eclipse-mosquitto mosquitto_sub -h host.docker.internal -t "#" -v

## Send demo message til Mosquitto mqtt

    docker run --rm eclipse-mosquitto mosquitto_pub -h host.docker.internal -t sensor/test -m '{"value": 42}'

## Opret virtuelt env til python

    py -3.12 -m venv .venv   

### aktiver .venv

    py -3.12 -m venv .venv 

### installer python pakker i .venv
 
    pip install paho-mqtt pymongo      

## aktiver Pytons virtuelle env

    .\.venv\Scripts\Activate.ps1

## Kør python subscriber, som migrerer til MongoDB

    python mqtt_to_mongo.py

## Se data i mongodb

    docker exec mongodb mongosh "mongodb://localhost:27017/iot" --quiet --eval "db.messages.find().sort({ timestamp: -1 }).limit(10).forEach(doc => printjson(doc));"

