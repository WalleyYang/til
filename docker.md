#### Docker Compose

##### Run container
`docker-compose up`

##### Stop container
`docker-compose down`

##### Run container in background
`docker-compose up -d`

##### Build images before starting container
`docker-compose up --build`

##### Recreate container from existing image
`docker-compose up --force-recreate`

#### Containers

##### List all containers
`docker ps -a`

##### List running containers
`docker ps`

##### List stopped containers
`docker ps -f "status=exited"`

##### Remove container
`docker rm <container>`

#### Images

##### Build image and tag it
`docker build -t <image name>:<tag> .`

##### Remove image
`docker rmi <image>`

##### Prune dangling images (not tagged and not reference by any containers)
`docker image prune`

##### Prune all not be used by existing containers
`docker image prune -a`

##### Tag image
`docker tag <image> <repository>:<tag>`

##### Push tagged image to registry
`docker push <repository>:<tag>`

##### Run image from registry
`docker run <repository>:<tag>`

#### Volumes

##### List volume
`docker volume ls`

##### Remove volume
`docker volume rm <volume>`

##### Remove dangling volumes
`docker volume prune`
