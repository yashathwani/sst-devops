15 dec hpa

horizontal pod autoscaler class. basically k8s scales ur pods automatically based on load.

what is hpa:
- it watches cpu usage (or custom stuff) and adds or removes pods.
- if load goes up pods increase. if it goes down pods decrease. u dont have to do it manually.
- analogy: like calling more ppl to work when its busy and sending them home when its slow.

what u need:
- k8s cluster (kubeadm setup).
- metrics server: this collects cpu/ram data. without it hpa cant see anything.

commands to know:
- kubeadm: for setting up cluster.
- kubectl apply -f file.yaml: deploy stuff like metrics server.
- kubectl scale --replicas=X deployment/name: manually scale pods.
- kubectl top pods: see resource usage. needs metrics server running.

how to use hpa:
1. make ur deployment.
2. deploy metrics server first.
3. create hpa resource. tell it like "if cpu goes over 50%, scale up to 10 pods."

limits vs requests:
- requests: minimum resources guaranteed to pod.
- limits: max resources pod can use.

troubleshooting:
- if kubectl top doesn't work, metrics server is probably not running.
- use kubectl get pods to check whats happening.

summary:
hpa makes k8s smart about scaling. just set some thresholds and it does the work for u.
