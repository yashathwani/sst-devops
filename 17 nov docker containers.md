17 nov docker containers

today was about docker volumes. basically a way to keep your data safe.

why we need them:
containers are temporary (ephemeral). if a container stops or dies, all the data inside is gone. volumes save that data so it stays safe even if the container is deleted. 
super important for things like databases (mysql etc).

how it works:
every container has a "writable layer" for storing changes, but volumes are better cuz they are independent of the container life.

different types:
1. named volumes: docker manages these for u. u give them a name and can use them again for other containers.
2. anonymous volumes: docker makes these automatically when needed, but they don't have a name and aren't really for sharing.
3. bind mounts: these are just folders on your computer that u map to the container. u have to manage the paths and permissions yourself.

sharing stuff:
u can use one volume for multiple containers if they need to share the same data.

some commands:
- docker volume create <name>: makes a new volume.
- docker volume inspect <name>: shows where the data is actually stored on ur pc.
- docker run -v <vol_name>:<path>: this connects the volume to a path inside the container.
- use :ro at the end if u want the container to only read and not write.

summary:
volumes make sure ur data doesnt vanish. they decouple the app from the storage.
