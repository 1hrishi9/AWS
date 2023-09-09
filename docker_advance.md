# docker volume
  docker volume create --name dockervolume --opt type=none device=dockervolumepath --opt  o=bind
  
      persist(volume) 


> docker image prune  -----> to delete those image which are not in use 

> docker container prune  -----> to delete those container which are not in use or stop

> docker system prune   --------->

> docker system df  ---------> to check the disk space used by docker

> docker image prune --all -----> delete all images

Sure, here are all the Docker commands related to volumes, along with their flags:

* `docker volume create`: Creates a new Docker volume.
    * `--driver`: The name of the volume driver to use. The default driver is `local`.
    * `--opt`: A list of options to pass to the volume driver.
    * `--label`: A label to attach to the volume.
* `docker volume inspect`: Displays detailed information about a Docker volume.
    * `--format`: The format of the output.
* `docker volume ls`: Lists all of the available Docker volumes.
* `docker volume mount`: Mounts a Docker volume into a container.
    * `--bind`: The path on the host machine to mount the volume.
    * `--read-only`: Mount the volume read-only.
    * `--volume-opt`: A list of options to pass to the volume driver.
* `docker volume prune`: Removes all unused Docker volumes.

Here are some additional commands that you may find useful:

* `docker volume rename`: Renames a Docker volume.
* `docker volume rm`: Removes a Docker volume.
* `docker volume share`: Shares a Docker volume with other users.

For more information on Docker volumes, please refer to the Docker documentation: https://docs.docker.com/engine/reference/commandline/volume/.




# docker networking 

 type of network 
    1. bridge
    2. custom bridge
    3. host
    4. none
    5. Macvlan
    6. overlay
    7. ipvlan