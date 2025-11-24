24 nov kubernetes

class about kubernetes (k8s) today. it's for automating ur containers at scale. 

pods:
- smallest thing in k8s. it has ur containers inside.
- k8s schedules them on worker nodes. 

architecture (2 main parts):
1. control plane: the "brain"
   - api server: the front door for all requests.
   - etcd: where k8s saves all its data (key-value store).
   - controller: makes sure the cluster stays how u want it.
   - scheduler: decides which node a pod should go to.
2. data plane: the worker nodes
   - kubelet: the agent on every node that runs the pods.
   - cri: handles the container life (like docker).
   - kube-proxy: handles the network rules.

cool features:
- bin packing: k8s puts containers where they fit best.
- self-healing: if a container dies, k8s restarts or replaces it automatically.
- scaling: u can scale up/down with one command.
- rollout/rollback: update your app with zero downtime. if it breaks, u can go back fast.
- secret management: store passwords/config without rebuilding images.

scaling types:
- hpa: scales pods based on cpu usage.
- vpa: scales cpu/ram of a single pod.
- cluster autoscaler: adds more nodes if u run out of space for pods.

summary:
k8s is a powerhouse for running containers. it handles all the hard stuff like scaling and healing for u.
