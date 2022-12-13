# Edge Computing
엣지 컴퓨팅은 아래 그림과 같이 특정 프로토콜을 사용하여 실제 디바이스와 통신하는 Deivce Service layer, 디바이스 데이터 수집 및 저장을 하는 Core Service layer, 디바이스의 정보를 관리 및 실시간 데이터를 전달하는 Device Management Service layer로 구성함.
<center><img width="70%" src="https://user-images.githubusercontent.com/120157640/207243629-53198c5c-c594-4d8d-8150-4c3da0f8ab45.png"></center>

## Get Started
### Alpha Version Service
**Device Service Layer**
* OPC_UA Device Service
* Modbus Device Service
* MQTT Device Serivce
* Cobs Device Service

**Device Management Service Layer**
* Device Management Service

### Download & Start Edge Computing 
```
git clone https://github.com/KetiSmartNetworkCenter/example.git
cd EdgeComputing/
docker-compose up -d
```
