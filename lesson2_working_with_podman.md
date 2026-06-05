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
