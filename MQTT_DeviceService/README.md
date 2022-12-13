#MQTT Device Service

오픈소스 프레임워크의 MQTT 통신 기반 Device Service
구성요소
1. docker-compose.yml 파일
: EdgeComputing 오픈소스 프레임워크에 해당 Service 추가
2. configuration.toml => MQTT Device Service 에 대한 설정 파일
2.1. 해당 파일의 "[[DeviceList]]" 에 Device 및 Profile 이름 설정과
3. resource_profil.yml
: MQRR Device Service 의 Resource 정의