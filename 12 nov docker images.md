12 nov docker images

today class was about making docker images and using dockerfiles. 

images vs containers
images are like the package for ur app. it has everything to run.
containers are where the image actually runs. its isolated and fast cuz it uses the host kernel.

commands
docker build: making the image. use -t to give it a name. always use lowercase for tags.
docker run: starting it up. -d runs in background (detached) and -p for port forwarding.

dockerfile stuff
FROM: the base image u start with.
RUN: runs commands while building. every RUN adds a new "layer".
CMD and ENTRYPOINT: both start the app. CMD can be changed by user later, ENTRYPOINT stays fixed.

making it fast
multi-stage builds: use this to keep images small. only keep what u need in the final image.
copy on write (cow): way docker loads files to save memory.
layers: try to have as few layers as possible. combine commands with && to make it faster.
base image: use something small. for java use JRE for running instead of full JDK to save space.

example
we saw a java app using multi-stage build. build with jdk then switch to jre for the final small image.
basically just practice the commands to get good at it.
