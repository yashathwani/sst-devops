19 dec ci using github actions

today was about github actions. its basically ci/cd built into github.

what it does:
- automates building, testing, and deploying code right from ur repo.
- no need for external tools like jenkins if u use this.

setting up:
1. make a repo on github (can add readme and stuff).
2. clone it to ur machine: git clone <url>.
3. put ur code in there (like pom.xml for java).

workflow files:
- these r yaml files in .github/workflows folder.
- they tell github what to do when something happens (like a push).

basic yaml structure:
- name: what u call the workflow.
- on: the trigger (like push to main).
- jobs: what to run.
- runs-on: the machine to use (ubuntu, windows, macos). ubuntu is most popular.
- steps: specific tasks like checkout code, setup java, run mvn package etc.

maven stuff:
- setup-java action: picks the jdk version.
- mvn package: builds and tests ur java app.
- caching: save dependencies so next builds r faster.

cost tips:
- use spot instances to save money.
- turn off machines when not using them.

common errors:
- yaml syntax wrong: double check ur indentation.
- version issues: make sure the jdk version exists.
- permissions: actions might need access to certain things.

summary:
github actions is easy ci/cd. just make a yaml in the right folder and it runs automatically when u push.
