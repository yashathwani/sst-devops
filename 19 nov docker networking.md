19 nov docker networking

talking about docker networking today. how containers talk to each other and the internet.

basics:
- ip address: unique id for every device. every container gets its own ip.
- subnetting: splitting a big network into smaller ones. u use cidr like /24 (gives 256 ips).
- network id: first ip in the group (names the network).
- broadcast id: last ip in the group (to talk to everyone).

docker0 (zero bridge):
- when docker is installed u get a thing called docker0. 
- its like a virtual switch. it lets containers talk to the world and each other.
- containers use a "veth pair" (virtual cable) to connect to it.

bridge network:
- by default everything runs on docker0.
- u can make your own bridge: docker network create -d bridge my_bridge.
- good for isolating groups (engineering, hr etc) so they don't mix.

troubleshooting:
- use "docker inspect" to see the networking details of any container.
- containers on the same bridge can talk via ip.

summary:
networking is just about connecting containers via bridges like docker0. u can use subnets to keep things organized.
