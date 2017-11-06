# Docker

## Create Docker Host on Azure

`docker-machine create --driver azure --azure-subscription-id %AZURE_SUB% --azure-resource-group my-docker-resources --azure-location northeurope --azure-open-port 80 dockerhost`

`docker-machine env dockerhost`

## Create Docker Host on AWS (not all regions are supported yet)
`docker-machine create --driver amazonec2 --amazonec2-region eu-central-1 --amazonec2-zone a docker01`

## Set environment variables for a container

`docker run -it -e foo=bar ubuntu bash`

## Get Host IP from within a container

apt-get install iproute2
/sbin/ip route | awk '/default/ { print $3 }'
