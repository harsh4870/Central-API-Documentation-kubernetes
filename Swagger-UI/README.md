# Swagger UI Kubernetes deployment
Central API Documentation on Kubernetes Swagger UI.

## Getting Started

# For External hosted Swagger UI

```
docker run -d \
    -p 8080:8080 \
    -e API_URLS="[{url: 'https://petstore.swagger.io/v2/swagger.json', name: 'Petshop'},{url: 'https://raw.githubusercontent.com/OAI/OpenAPI-Specification/master/examples/v3.0/uspto.yaml', name: 'Instagram'}]" \
     swaggerapi/swagger-ui
```

# For local files Swagger UI


```
docker run -d \
    -p 8080:8080 \
    -v $(pwd)/example-swagger.yaml:/usr/share/nginx/html/example-swagger.yaml \
    -e URLS="[{url: '/example-swagger.yaml', name: 'Petshop'}]" \
     swaggerapi/swagger-ui
```

# For Kubernetes adding local files inside docker image

```
COPY . /usr/share/nginx/html/
```
OR

```
COPY ./example-swagger.yaml /usr/share/nginx/html/example-swagger.yaml
```


