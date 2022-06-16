##Server-cloud

###Goal
>Server using spring-cloud-eureka to register and discover microservices and also using spring-cloud-gateway to manage ports and load balancer 

###Technologies
* Spring-Cloud-Eureka
* Spring-Cloud-Gateway

## Instructions

**Eureka**

> The eureka server will be available at [https://localhost:8081](https://localhost:8081)
> Here you will be able to view each microservices and their active instances
> 
> For eureka to register your ms you must add the properties below in application.properties
* >spring.application.name= name-your-ms
* >eureka.client.serviceUrl.defaultZone=http://localhost:8081/eureka
>In addition, you must put the annotation _@EnableEurekaClient_ in the application class


**Gateway**

> The gateway will manage your application ports and load balance
> 
> For the gateway to work, in addition to the step above, you must also include the notes below in application.properties:
> 
* >eureka.instance.instance-id=${spring.application.name}:${random.int}
* >server.port=0 