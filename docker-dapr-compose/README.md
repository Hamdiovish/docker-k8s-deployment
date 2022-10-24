# Setup

> docker network create dapr-env

# Invokation:

## Local:

> java -jar build/libs/rest-service-1.1.0-SNAPSHOT.jar

> dapr init

> dapr run --app-id back --dapr-http-port 3500 --app-port 8080 

> curl -X POST http://localhost:3500/v1.0/bindings/sample \
  -H "Content-Type: application/json" \
  -d '{
        "data": {
          "message": "Message 01"
        },
        "metadata": {
          "key": "key-1"
        },
        "operation": "create"
      }'

## Compose:

> docker-compose up -d

> curl -X POST http://localhost:3501/v1.0/bindings/sample \
  -H "Content-Type: application/json" \
  -d '{
        "data": {
          "message": "Message 01"
        },
        "metadata": {
          "key": "key-1"
        },
        "operation": "create"
      }'
