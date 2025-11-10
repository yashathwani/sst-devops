10 nov intro to docker

more docker today. basically its for dev and shipping stuff fast without worrying about the server.

packing things:
- u put ur app + libs + all dependencies in one box (container).
- this way it runs the same on your laptop and the server.

commands we learned:
- docker run: starts a new one. use -it flag for ubuntu if u want to use the terminal.
- docker exec: if its already running, use this to go inside and run commands.
- docker ps: see what is running.
- docker container inspect: shows all the hidden details like the ip address.

handling images:
- docker images: lets u see what templates u have.
- docker commit: if u change things inside a container, save it as a new image with this.
- docker push: sends your image to docker hub so others can use it. note: image name must start with ur username!

networking:
- inspect the container to find its ip.
- u can use curl if u know the ip to talk to the container.

layers and dockerfile:
- dockerfiles have steps. each step is a new "layer".
- layers are good cuz docker caches them to make things faster.
- detached mode (-d): runs the container in the background so it doesnt block ur terminal.

why docker over vms:
- vms are heavy cuz they have a whole operating system. 
- docker is light cuz it uses the host os. way more efficient.
- watch out for amd vs arm stuff, can cause issues if u build on one and run on another.
