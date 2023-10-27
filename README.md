
# Atm Video Pack App - DigitalMinds

ATMVideopack System adalah solusi kompak yang dirancang khusus untuk memantau dan
mengompresi aliran video dari CCTV dengan efisiensi tinggi. Mini PC canggih ini membantu
Anda mengawasi keamanan dengan mudah dan menyimpan ruang penyimpanan yang
berharga dengan teknologi kompresi canggih. Dengan desain yang ringkas dan kemampuan
andalnya, ATMVideopack System adalah pilihan terbaik untuk memastikan keandalan
pemantauan CCTV Perbankan Anda.


## Authors

- [@aditya3232](https://github.com/aditya3232)
- [@myahyasa](https://github.com/myahyasa)
- [@DigitalMindsTechnology](https://github.com/DigitalMindsTechnology)



## Features

- Dashboard
- Log access with detail
- Setting door & cctv
- Master data office, user door access, and cctv
- Setting admin web


## Tech Stack

**Website:** Laravel Framework 10.14.1

**Backend:** Go 1.21.1 

**CSS:** TailwindCSS & Bootstrap 5

**Storage:** Minio latest

**Queue:** Rabbit MQ 3.12.6

**Search:** ElasticSearch 7

**Database:** Mysql


## License

[MIT](https://choosealicense.com/licenses/mit/)



# Catatan! 👋

[Servis berserta portnya]
- atmVideoPack-services port : 3636
- atmVideoPack-humanDetection-publisherRmq-services port : 3333
- atmVideoPack-humanDetection-consumerRmq-services port : optional
- atmVideoPack-vandalDetection-publisherRmq-services port : 3434
- atmVideoPack-vandalDetection-consumerRmq-services port : optional
- atmVideoPack-statusMcDetection-publisherRmq-services port : 3535
- atmVideoPack-statusMcDetection-consumerRmq-services port : optional

# API Spec yang Digunakan Mesin

## 1 Publisher Human Detection

Request :
- Method : POST
- Endpoint : `{{local}}:3333/publisher/atmvideopack/v1/humandetection/create`
- Header :
    - x-api-key :
- Body (form-data) :
    - tid : string, required
    - date_time : string, required
    - person : string, required
    - file_capture_human_detection : string, required
- Response :

```json 
{
    "meta": {
        "message": "string",
        "code": "integer",
    },
        "data":{
            "tid": "string",
            "date_time": "string",
            "person": "string",  
            "file_capture_human_detection": "string"  
        }
 }
```
## 2 Publisher Vandal Detection

Request :
- Method : POST
- Endpoint : `{{local}}:3434/publisher/atmvideopack/v1/vandaldetection/create`
- Header : 
    - x-api-key : 
- Body Body (form-data) :
    - tid : string, required
    - date_time : string, required
    - person : string, required
    - file_capture_vandal_detection : string, required
- Response :

```json 
{
    "meta": {
        "message": "string",
        "code": "integer",
    },
        "data" : {
            "tid": "string",
            "date_time": "string",
            "person": "string",  
            "file_capture_vandal_detection": "string"
        }
}
```
## 3 Publisher Status MC (Mini PC) Detection 

Request :
- Method : POST
- Endpoint : `{{local}}:3535/publisher/atmvideopack/v1/statusmcdetection/create`
- Header : 
    - x-api-key : 
- Body Body (form-data) :
    - tid : string, required
    - date_time : string, required
    - status_signal : string, required
    - status_storage : string, required
    - status_ram : string, required
    - status_cpu : string, required
- Response :

```json 
{
    "meta": {
        "message": "string",
        "code": "integer",
    },
        "data" : {
            "tid": "string",
            "date_time": "string",
            "status_signal": "string",  
            "status_storage": "string",
            "status_ram": "string",
            "status_cpu": "string"
        }
}
```
## 4 Add Device

Request :
- Method : POST
- Endpoint : `{{local}}:3636/api/atmvideopack/v1/device/create`
- Header : 
    - x-api-key : 
- Body Body (form-data) :
    - tid : string, required, unique
    - ip_address : string, required
    - sn_mini_pc : string, required
    - location_id : string
- Response :

```json 
{
    "meta": {
        "message": "string",
        "code": "integer",
    },
        "data" : {
            "tid": "string",
            "ip_address": "string",
            "sn_mini_pc": "string",  
            "location_id": "string",
        }
}
```

## Appendix

Contact :
- Digital Minds Technology - Jakarta Timur
- Email : digitalmindstechnology@gmail.com
- Mobile : 081398696144


![Logo](https://camo.githubusercontent.com/6480cae900aacb5c6a44924eafaf01f0da37404d3b7e0509675528dff1a74b43/68747470733a2f2f696d616765732e696e746572657374696e67656e67696e656572696e672e636f6d2f696d672f6965612f344e36316f7845514f4a2f627261696e2d757365722d696e746572666163652d322e6a7067)

