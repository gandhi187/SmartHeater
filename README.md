# SmartHeater 

Collecting actual temperature-values from sensors connecting to a raspberry PI 
The Data is sent via an ESB to a WSDL web service

### Project-Architecture
![alt text](https://github.com/gandhi187/SmartHeater/blob/master/Pr%C3%A4sentation1.png "Architecture")


### WSDL-Example Request

Request:
Endpoint: http://localhost:8082/bank/temp?temp_system_api_wsdl


```xml

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:sch="http://www.mulesoft.com/schemas/Mule/Schema.xsd">
   <soapenv:Header/>
   <soapenv:Body>
      <sch:getTempRequest/>
   </soapenv:Body>
</soapenv:Envelope>
```
---

Response:

```xml
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
      <ns0:getLoanResponse xmlns:ns0="http://www.mulesoft.com/schemas/Mule/Schema.xsd">
         <ns0:loanList>
            <ns0:loan>
               <ns0:timesstamp>2018-05-06T19:24:16</ns0:timesstamp>
               <ns0:tempdata>27.0</ns0:tempdata>
            </ns0:loan>
         </ns0:loanList>
      </ns0:getLoanResponse>
   </soap:Body>
</soap:Envelope>
```

## To-Do
*Implement Controll-Service for heater
*Implement E-Mail-Service in python (postfix)
*Integrate additional sensor in system
