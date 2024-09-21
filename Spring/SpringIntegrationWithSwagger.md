## Swagger -
Framework to implement the OAS
## OpenApi Specification - 
Standardized format for describing apis comprehensively.
## Springfox - 
java library to integrate swagger with spring boot application.
## SpringDoc OpenApi -
Alternative to springfox. It is designed to generate API documentation from spring boot application using 
OpenApi 3 specification. Which is latest integration of swagger specification.


Add following dependency in spring application and you will start seeing all the routes in api.
```text
<!-- https://mvnrepository.com/artifact/org.springdoc/springdoc-openapi-ui -->
<dependency>
    <groupId>org.springdoc</groupId>
    <artifactId>springdoc-openapi-ui</artifactId>
    <version>1.8.0</version>
</dependency>
```
once we do maven reload it generates url where we can see swagger ui.<br>
**we can change the url**

