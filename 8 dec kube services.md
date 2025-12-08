8 dec kube services

k8s class recap today. pods, replicasets, deployments and specially services.

pods recap:
- basic block of k8s. 
- containers in a pod share the same ip and network space.
- analogy: pod is like a house, containers r like rooms. house gets the address (ip), not the rooms.
- they r co-located and co-started.

replicasets:
- makes sure u always have the right amount of pods.
- if a pod fails it makes a new one. good for fault tolerance even if u only have 1 pod.

deployments:
- manages pods and rs for u.
- handles scaling and those rolling updates/rollbacks.

services (stable endpoints):
- a service gives a fixed ip to ur app so u can find it.
- types:
  1. clusterip: only for inside the cluster.
  2. nodeport: exposes the app on the node's ip so u can access it from outside. automatically makes a clusterip too.
- service discovery: uses labels to find the right pods.
- load balancing: splits the traffic between pods so one doesn't get crushed. 
- analogy: like movie theater attendants, u can go to any window and get ur ticket.

load balancers:
- internal: for traffic inside.
- external: for internet traffic coming in.

yaml files:
- every resource has these 4 things:
  1. api version: which k8s api to use.
  2. kind: what r u making (pod, service, etc).
  3. metadata: name and namespace.
  4. spec: what u want the thing to do.

summary:
understand these and u know k8s. pods run, services let ppl talk to them, and deployments keep everything alive.
