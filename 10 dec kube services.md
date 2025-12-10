10 dec kube services

networking in k8s today. how stuff talks to other stuff.

4 main types of communication:

1. containers in same pod:
- they share the network. so they talk via localhost like apps on ur pc.

2. pods on same node:
- use the virtual network k8s makes.
- handled by cni (container network interface) plugins.
- analogy: plugin is like a bus driver who knows the routes.

3. pods on different nodes:
- data goes thru network plugins and ip tables.
- kube-proxy keeps the network rules on nodes updated and routes traffic to the right pod.

4. pods to services:
- services give a stable ip (cluster ip) so pods can talk even if ips change.
- coredns handles the names. u access service by name not ip.
- endpoints r like entries in ip tables, they point traffic to the right pod.

some commands:
- kubectl get svc: list services.
- kubectl describe svc: more details about a service.

other stuff:
- namespaces and labels: for organizing and picking the right pods.
- coredns: the dns inside k8s, lets u find services by name.

summary:
k8s networking is complex but it makes distributed apps work smooth. services r stable endpoints, kube-proxy and coredns do the heavy lifting.
