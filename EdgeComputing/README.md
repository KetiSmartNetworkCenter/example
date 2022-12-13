## EdgeComputing Framework
docker-compose.yml 파일은 모든 Alpha Version Service를 구성하고 있으며 Device Managemnet, Opcua Device Service, Modbus Device Service, MQTT Device Service, Cobs Device Service는 Device_Management 또는 Device_Service Directory의 README.md 를 참고하여 추가 구동 가능함. 

### Start EdgeComputing
```
docker-compose up -d
```
### 실시간 디바이스 데이터 확인 2가지 방법
1. Eclipse MQTT Broker
```
docker network ls
docker network inspect {network's name} // find Eclipse MQTT Broker IP
mosquitto_sub -h {Eclipse MQTT Broker IP} -p 1883 -t EdgeXEvent
```
2. Device Management Serivce Web Socket
```

```
