Fully qaulified container name 

- Images are fetched from the registries
- Podman doesnt work with a default registry 
- FQCN ( fully qualified container name)

eg 

instead of podman run -d nginx , you should use podman run -d docker.io/library/nginx 

once image is stored you can then use the short name 

commands 

#podman search ubi9
#podman pull registry.redhat.io/ubi9/ubi 
#podman run -it : opens up an interactive shell  
#podman login : used to login to a specific registry
#podman search ; searches for container images
#podman images : shows images stored by the current user 
#podman ps : shows containers running 
#podman ps -a : shows containers no longer running 
#podman run ; pulls the container images and runs it.
#podman run -it ubi /bin/bash 

#################################################################
Rootless vs RootContainers

- a rootless container runs as a non-privileged user 
- any user can start a rootless container 

Root containers runs with root privileges 

rootless containers dont have ip's but work with ports only 

sudo podman inspect -l -f "{{.NetworkSettings.IPAddress }}"
10.88.0.2



#################################################################

Container Management 

podman ps -a : shows current and past running containers 
podman stop : stops a running container 
podman start : starts a container that was started previsouly 
podman inspect : shows properties used by containers and images 
podman exec -it containername sh : runs an additional shell , secondary process
ctrl-p , ctrl q : detaches from a current interactive session 

a container comes from an image 

Using variables 

-e key =value 

podman logs containername 


exit status 

0 = nothing is wrong - success
1 = something is wrong 


man podman run 
podman run --help 


####################################################

podman networking 

- use podman network ls to see current networks
- to start containers in different namespace use , podman network create  
- traffic between networks is blocked 
- rootless containers dont have ip address

#######################################################

accessing containers 

- containers cannot be reached by external users 
- To access a container a port can be exposed 
- port forwarding , podman run -d -p 127.0.0.1:8080:80 nginx 
- HOST_PORT : 8080
- CONTAINER_PORT: 80 

#################################################

Restrict containers 
