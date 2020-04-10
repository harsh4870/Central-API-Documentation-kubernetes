# Redoc UI Kubernetes deployment
Central API Documentation on Kubernetes Redoc UI.

## Getting Started

# For External hosted Redoc UI

```
docker run -it --rm -p 80:80 \
  -e SPEC_URL='https://petstore.swagger.io/v2/swagger.json' redocly/redoc
```
OR 

```

docker run -p 8080:80 -e SPEC_URL=https://api.example.com/openapi.json redocly/redoc

```

# For local files Redoc UI


```
docker run -it --rm -p 80:80 \
  -v $(pwd)/example-swagger.yaml:/usr/share/nginx/html/example-swagger.yaml \
  -e SPEC_URL=/example-swagger.yaml redocly/redoc
```

# For Kubernetes adding local files inside docker image

```
COPY . /usr/share/nginx/html/
```
OR

```
COPY ./example-swagger.yaml /usr/share/nginx/html/example-swagger.yaml
```


