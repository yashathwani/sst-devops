1 dec kubernetes pods

k8s class again. mostly about pods and setup.

cluster setup:
- we used 3 machines: 1 master and 2 workers.
- master node handles the brain (control plane).
- worker nodes do the actual work (data plane).
- setup used shell scripts and kubeadm (kubectl init).
- this downloads all the configs like etcd, scheduler, etc.

what r pods:
- smallest thing k8s can deploy.
- containers in a pod live on the same node and share everything (network/resources).
- scheduled together.

architecture stuff:
- brain (control plane): api server, etcd (data store), controller, scheduler.
- muscle (data plane): includes kubectl to talk to the brain.
- kubectl uses rest or grpc to talk to the api server.
- api server checks if you r allowed before it docs stuff in etcd.

deploying:
- "kubectl get pod" to see whats happening.
- can isolation stuff with namespaces (like default or kube-system).

networking:
- coredns handles the names inside the cluster.
- u need a network plugin like Weave for things to work.
- k8s looks at how much cpu/ram is free before putting a pod on a node.

summary:
pods r basic but k8s handles all the hard setup and scheduling for u.
