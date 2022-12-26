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

<img width="600" alt="github_device_management_restfulAPI" src="https://user-images.githubusercontent.com/120157640/209511773-1fa3c720-b425-4f3d-9963-f05c71881c62.PNG">

##### Show devices Informations
The API is used for displaying all of Edge Devices in framework
```
GET http://localhost:5555/api/v1/devices
```
Response Sample:
```
[
  { "created":1667282391903, 
    "description":"This device is a product for monitoring and controlling digital inputs and outputs over a LAN",
    "id":"c9afb433-da08-49e8-83da-5f0b22fb9f95",
    "name":"MQTT_Device",
    "register":"false",
    "image":"",
    "resource_list":[
     { "id":"2d76a579-c00b-4055-8843-c22388bab504",
       "name":"ObjTemp",
       "description":"Object Temperature"
       "type":"",
       "image":"",
       "autoevent":"",
       "frequency":"1s",
       "get":"true",
       "put":"false" },{...}]
   }
]
```
#### Register device information
The API is used for registering Edge Device Information
```
POST http://localhost:5555/api/v1/devices
```
Request Sample:
```
{
 "id":"a7d3f2aa-e26b-4e3a-b929-8383e238c948",
 "name":"device's name",
 "description":"device's description",
 "image":"device's image.jpg",
 "resources":[
  {
   "id":"9eb617b0-5b14-4c11-93d3-caeb569b5f74",
   "name":"resource's name",
   "description":"resource's description",
   "type":"sensor_type or actuator_type or status_type",
   "image":"resource's image.jpg"
  },...
 ]
}
```
#### Delete devices information
The API is used for deleting All Edge Device Information
```
DELETE http://localhost:5555/api/v1/devices
```
#### Show device information
The API is used for displaying device information by device's id
```
GET http://localhost:5555/api/v1/devices/{device's id}
```
Response Sample:
```
  { "created":1667282391903, 
    "description":"This device is a product for monitoring and controlling digital inputs and outputs over a LAN",
    "id":"c9afb433-da08-49e8-83da-5f0b22fb9f95",
    "name":"MQTT_Device",
    "register":"true",
    "image":"rasp.jpg",
    "resource_list":[
     { "id":"2d76a579-c00b-4055-8843-c22388bab504",
       "name":"ObjTemp",
       "description":"Object Temperature"
       "type":"sensor",
       "image":"sensor.jpg",
       "autoevent":"true",
       "frequency":"1s",
       "get":"true",
       "put":"false" },{...}]
   }
```
#### Modify registered device's information
The API is used for Modifying device information by device's id
```
PUT http://localhost:5555/api/v1/devices/{device's id}
```
Request Sample:
```
{
  "name":"device's name",
  "description":"device's description",
  "image":"device's image"
}
```
#### Delete device information
The API is used for deleting Edge Device Information by device's id
```
DELETE http://localhost:5555/api/v1/devices/{device' id}
``` 
#### Show Resource Information by device's id and resource's id
The API is used for displaying resource information
```
GET http://localhost:5555/api/v1/devices/{device's ID}/resources/{resource's ID}
```
Response Sample:
```
  {
    "id":"2d76a579-c00b-4055-8843-c22388bab504",
    "name":"Object_temp",
    "description":"object temperature",
    "type":"sensor_type",
    "image":"sensor.jpg",
    "autoevent":"true",
    "frequency":"1s",
    "get":"true",
    ""put":"false"
  }
```
#### Modify registered resource's information
The API is used for Modifying resource's information by device's id and resource's id
```
PUT http://localhost:5555/api/v1/devices/{device's id}/resources/{resource's id}
```
Request Sample:
```
{
  "name":"resource's name",
  "description":"device's description",
  "image":"device's image"
}
```
#### Check Command 
The API is used for checking available command to Edge Device
```
GET http://localhost:5555/api/v1/check_command/devices/{device's id}/resources/{resource's id}
```
Response Sample:
```
{
 "get":"true",
 "put":"true"
}
```
#### GET Command
The API is used for getting resource's value
```
GET http://localhost:5555/api/v1/command/devices/{device's ID}/resources/{resource's ID}
```
Response Sample:
```
  {
    "device_id":"c9afb433-da08-49e8-83da-5f0b22fb9f95",
    "device_name":"ex_modbus",
    "resource_id":"2d76a579-c00b-4055-8843-c22388bab504",
    "resource_name":"ex_modbus_resource_name",
    "time":1667288180493422371,
    "value":"2.793000e+01"
  }
```
#### PUT Command
The API is used for controlling resource's value
```
PUT http://localhost:5555/api/v1/command/devices/{device's ID}/resources/{resource's ID}
```
Request Sample:
```
{
  "value":"1.2588"
}
```
