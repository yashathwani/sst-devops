7 jan cd

cd class today. deploying apps to k8s cluster using github actions.

ci vs cd:
- ci: automating code merges and testing. keep ur main branch always deployable.
- cd: takes it further. actually pushes code to production automatically. no manual deploy.

k8s environment setup:
- need at least 1 node cluster.
- can use virtualbox + vagrant to spin up vms. vagrant scripts automate the whole thing.
- or just use an ami that already has k8s installed. saves time.

github actions for cd:
- automates the whole workflow from build to deploy.
- can use github hosted runners or set up ur own.

self hosted runners:
- ur own machine acts as the runner instead of githubs.
- linux is recommended.
- use config.sh to register it with github.
- add labels and security stuff.

testing layers:
- sit (system integration testing).
- performance testing.
- security testing.
- automate all of it to avoid human mistakes.

project stuff:
- teams build a project using ci/cd with github actions.
- everyone needs to know their own part for the presentation.

tips:
- keep ci and cd separate in real setups. cleaner that way.
- each app might need different pipeline configs based on infra.

summary:
cd is about getting code to production fast and automatically. github actions + k8s makes it smooth.
