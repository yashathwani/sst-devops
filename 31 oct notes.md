# 31 oct notes

ci/cd is just continuous integration and continuous deployment. basically automating the building, testing and shipping of code.

ci part:
- code repo: when u push code, it starts the pipeline.
- steps in pipeline:
  1. linting: fix syntax errors and keep code quality good. 
  2. building: download packages and compile.
  3. unit test: test small parts of app. use "mocking" if u need to fake external calls.
  4. sca/sast: security scans to find bugs or vulnerabilities in code/libs.

artifacts: 
- these are the files u get after build (like jar, war, or docker images). needed for deploy.

docker and containers:
- dockerization: putting app in a container.
- docker image: like a static file u can deploy anywhere. 
- images have layers. they get cached to make builds faster.
- after build, push image to a repo (artifact repo).

cd part:
- deployment starts from the artifact repo.
- sit (system integration testing): first place u deploy to test how app works with other systems.

ip stuff:
- public ip: temp ip, changes when u stop/start the instance.
- elastic ip: stays same even if u reboot. important for production so u have a fixed endpoint.

summary:
- ci/cd makes dev and ops work easier with automation.
- docker makes app portable.
- elastic ip is for stable hostnames.
