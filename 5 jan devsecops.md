5 jan devsecops

big class today. full ci pipeline with github actions + docker + security.

what we r building:
- complete pipeline that builds, tests, scans and pushes docker images.
- security is baked in (thats the "sec" in devsecops).

pipeline flow:
code push -> github runner -> build -> test -> security scan -> docker build -> image scan -> container test -> push to dockerhub

prereqs:
- java maven project with dockerfile.
- dockerhub account.
- github secrets: DOCKERHUB_USERNAME, DOCKERHUB_TOKEN (dont hardcode passwords!).

trigger:
- runs on push to master. can also manually trigger from github ui.

stages explained:

1. checkout: pulls ur repo into the runner.

2. setup java: installs java 11 and maven. caches dependencies.

3. linting: mvn checkstyle:check. catches bad code style. we let it continue even if it fails.

4. sast (codeql): scans source code for security bugs like sql injection.

5. sca (owasp): checks if ur dependencies have known vulns. protects from supply chain attacks.

6. unit tests: mvn test. breaks pipeline if tests fail.

7. build: mvn clean package -DskipTests. creates the jar.

8. docker build: docker build -t user/app:latest. makes the image.

9. trivy scan: scans the image for vulns. fails if critical issues found.

10. container test: runs the container and curls it to check if its alive (smoke test).

11. login: uses secrets to auth with dockerhub.

12. push: docker push. only happens if everything passes.

why this is "industry grade":
- multiple layers of security.
- fails on critical vulns.
- runtime check before pushing.
- secrets not exposed.

summary:
this pipeline is a quality gate. only tested, scanned, and verified stuff gets pushed. thats devsecops.
