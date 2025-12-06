5 dec kubernetes deployments

today was all about k8s deployments and how they handle pods and replicasets.

pods:
- smallest unit in k8s. 
- ephemeral - if they die, they're gone forever. k8s doesn't restart a lone pod by itself. 
- pods created by "kubectl run" don't have self-healing. that's why we use controllers.

replicasets (rs):
- this guy's job is to make sure "X" number of pods r always running.
- if a pod dies, rs makes a new one. 
- rs doesn't handle updates or rollbacks, so we don't usually use them alone.

deployments:
- this is the big boss controller for stateless apps.
- it manages replicasets and pods for u.
- handles:
  1. rolling updates: updating pods with zero downtime.
  2. rollbacks: going back to an old version if things break.
  3. self-healing: uses rs under the hood.
  4. scaling: easy to add/remove replicas.

how it works (workflow):
- u apply ur yaml -> apiserver checks it -> stores it in etcd.
- deployment controller wakes up -> sees if rs exists -> if not, creates one.
- replicaset ensures pods exist.
- scheduler picks the best node (based on cpu/ram).
- kubelet on the node pulls the image and runs the container.

rollout strategies:
1. rollingupdate (default): replaces pods one by one. no downtime.
2. recreate: kills all old pods first, then starts new ones. good for apps that can't run 2 versions at once.

etcd (deep stuff):
- everything k8s does is stored here as key-value pairs. 
- pods, rs, deployments are just files or entries in etcd.
- path is like /registry/deployments/<ns>/<name>.

rollbaks and history: 
- k8s tracks revisions. 
- check history: kubectl rollout history deployment/name.
- undo: kubectl rollout undo deployment/name.
- u can pause/resume rollouts if u need to debug.

scaling:
- kubectl scale deployment name --replicas=10. k8s updates etcd and then rs creates more pods.

summary:
deployments are the main way to run apps. they handle all the automation for scaling and updates.
