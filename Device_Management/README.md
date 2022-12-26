## Device Management
디바이스 프로파일 관리 및 제어를 위한 Device Management 마이크로서비스는 디바이스 관리 및 제어를 위한 Restful API 및 실시간 디바이스 데이터를 위한 Web Socket 통신을 지원한다.
압축된 docker image 파일인 device_management.tar를 docker image로 변환 후 EdgeComputing Framework에 docker-compose.yml에 정의 된 Service 형식을 추가하여 구동가능하다.


#### Convert Device_Management.tar to docker image
```
docker load -i device_management.tar
```

#### Web Socket address (Real-Time Device Data)
```
ws://localhost:5555/WS
```


#### Device Management Restful API List

<img width="355" alt="github_device_management_restfulAPI" src="https://user-images.githubusercontent.com/120157640/209511773-1fa3c720-b425-4f3d-9963-f05c71881c62.PNG">

##### show Devices Informations
The API is used for displaying all of EdgeDevices in framework
```
GET http://localhost/devices
```
Response Sample:
```
[{"created":},...]
```
