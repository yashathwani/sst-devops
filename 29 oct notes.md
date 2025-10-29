# 29 oct notes

devops is just dev + ops + culture. goal is to ship stuff faster and break silos between teams.
hard part is culture change.

concepts:
- shift left: do testing early in dev process.
- security stuff: 
  - sast: scan the code.
  - dast: scan the app while it runs.
  - sca: check third party libs for bugs.
  - like using preparedstatement to stop sql injection.

ci process:
1. checkout code
2. install depedencies
3. linting
4. build/compile
5. unit tests
6. security (sast and sca)
7. artifact (docker images)
8. deploy to staging

lifecycle is a loop: plan -> code -> build -> test -> release -> deploy -> operate -> monitor. it keeps going.

service stuff:
- api gateway: handles routing and auth.
- sync: blocking real time.
- async: non blocking using message brokers like kafka.

tools: git, jenkins, docker, kubernetes, terraform, prometheus, grafana.
