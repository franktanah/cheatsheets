# Docker

## Create Docker Host on Azure

`docker-machine create --driver azure --azure-subscription-id %AZURE_SUB% --azure-resource-group my-docker-resources --azure-location northeurope --azure-open-port 80 dockerhost`

`docker-machine env dockerhost`

## AWS
`docker-machine create --driver amazonec2 --amazonec2-region eu-central-1 --amazonec2-zone docker01`