## Deivce Service
특정 프로토콜(MQTT, Modbus-TCP, Opcua, Cobs)을 사용하여 통신하는 엣지 디바이스와 프레임워크와의 연동을 위한 디바이스 마이크로서비스이며 각 Device Service는 docker-compose.yml, profile.yml, configuration.toml, device_service.tar을 제공한다.

**Device Service 구성요소**
* docker-compose.yml : 엣지 프레임워크와 device service의 연동 정의 방법
* profile.yml : device service의 엣지 디바이스와 연동되는 Resource 정의
* configuration.toml : 엣지 프레임워크와 device service의 통신 환경 변수 설정
* device_service.tar : device service의 docker image 압축 파일

#### Convert device_service.tar to docker image
```
docker load -i {device_service}.tar
```

#### Make directory & Revise each file for your custom enviroment
```
EdgeComputing
L Cobs 
      L CobsSerialProfile.yml
      L configuration.toml
L modbus
      L modbus.yml
      L configuration.toml
L opcua
      L ictSmartlabServer.yml
      L configuration.toml
L mqtt
      L python.Test.Device.MQTT.Profile.yml
      L configuration.toml
```
