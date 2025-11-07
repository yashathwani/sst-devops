07 nov notes

docker and containerization today. 

what is docker:
- platform to manage containers.
- package app + dependencies into one unit.
- philosophy: "if it fits, it ships". just make it fit in container, then it runs on any machine.

concepts:
- containers: lite portable packages. better than vm cuz they share host kernel.
- images: read-only templates. the foundation.
- daemon: background service running the stuff. 
- client: cli tool to talk to daemon.
- volumes: persistent storage for data.
- networking: lets containers talk to each other.

working with it:
- docker run starts a container.
- use -it flag for interactive shell.
- docker hub is the cloud place for images.

conclusion:
- docker is base foundation for containers even if k8s is more popular now.
- hands-on in cloud shell today.
