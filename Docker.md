# Docker

## Create Docker Host on Azure

`docker-machine create --driver azure --azure-subscription-id %AZURE_SUB% --azure-resource-group my-docker-resources --azure-location northeurope --azure-open-port 80 dockerhost`

`docker-machine env dockerhost`

## AWS
`docker-machine create --driver amazonec2 --amazonec2-access-key AKI******* --amazonec2-secret-key 8T93C*******  aws-sandbox`