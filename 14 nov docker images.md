14 nov docker images

intro to containers today. 

some history: 
isolation isnt new. unix had "chroot" in the 70s. it was like a file system jail. u thought u were in a separate machine but still shared the same kernel.

what is a container really:
just a lite package with ur code and libs. shares the host os kernel instead of having its own (vms have their own os so they are heavy). 
containers are way faster and uses less resources.

how it works inside:
1. namespaces: this is how linux isolates stuff like pid, hostname, network, file systems.
2. cgroups: this handles the resources. ensures one container doesnt hog all the cpu or memory.

os stuff:
docker runs natively on linux cuz it uses the linux kernel. 
on windows and mac it needs a small vm because they dont have the linux kernel built in.

it is ephemeral:
meaning containers are temporary. u start, stop, or kill them easily. good for scaling but u need to store ur data somewhere else if u want to keep it.

networking:
use port mapping! map ur host machine port to the container port so the outside world can talk to ur app.

conclusion:
containers are a big deal for portability and scaling modern apps. its all about namespaces and cgroups under the hood.
