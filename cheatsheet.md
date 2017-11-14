

## Run a container and enter bash

Run do a few things. search for local image->not found->pull->start 

    docker run --name test-ghost -it ubuntu:latest 

alpine version

    docker run -it --rm node:alpine sh 

Enter terminal on a running container
-it flag sends output to terminal or it will just excute commands

    docker exec -it <containerIdOrName> bash 


## Container view and remove 

Start container 

     docker start 'container name or id'

Stop container 

     docker rm 'container name or id'

Remove container

      docker rm 'container name or id'

Remove all container 

    docker rm $(docker ps -a -q)

Remove all images

    docker rmi $(docker images -a -q)


## Run, mount volume and open port

    docker run --name container-name -v host-dir:guest-dir -p hostPort:dockerPort image-name

Copy file from container to host 

    docker cp <containerId>:/file/path/within/container /host/path/target

Show all images

    docker images -a -q
            
  
## Logging and inspec  

Show command history logs from a container 

    docker logs container-id

Show container details like ip addess, name, volume details etc

    docker inspect container-id


## Docker build

    docker build -t image-name -f dockerfile-name diretory 

## Copy file from guest

    $ docker cp container-name:guest-dir/filename host-dir/filename



## Commit and push

    docker commit -m 'commit message' -a 'author name' container-name-or-id your-repo-id/repo-name:tag

    docker push container-name-or-id your-repo-id/repo-name
