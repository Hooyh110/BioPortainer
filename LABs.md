## Scenario 1: Testing BioPortainer Installation in a Docker Engine using Play with Docker

In the first scenario, use Play-with-Docker (https://labs.play-with-docker.com) to configure a virtual machine containing the Docker Engine installed. Next, use the ADD NEW INSTANCE option to create the test virtual machine and type the following commands to deploy BioPortainer:

###### Test if Docker is installed and running, by typing:

$ docker info

### Check if there are Docker containers being executed, by typing: 

$ docker ps

### Download BioPortainer image from the Docker Hub, by typing: 

$ docker pull bioportainer/bioportainer

### Confirm download the BioPortainer image, by typing:

$ docker images

### Create a BioPortainer container, by typing:

$ docker run -d --name BioPortainer -p 9000:9000 \
  -v /var/run/docker.sock:/var/run/docker.sock \
  bioportainer/bioportainer

### Confirm creation of the BioPortainer container, by typing:

$ docker ps

Note that the commands described above deploy the BioPortainer container as a daemon (`-d`), published in the port 9000 of the test virtual machine. The Docker socket is defined by the parameter  –v (`/var/run/docker.sock`), to provide information regarding the timing of Docker excecution. Play with Docker allows all published ports of a Docker container (or all the services published in a Docker Swarm) to be automatically presented to outside connections. 

To access the BioPortainer interface the user must use a URL following the pattern: http://ip<ip-separated-by-hifen>-<session_jd>-<port>.direct.labs.play-with-docker.com. The <ip-separated-by-hifen> and <session_jd> variables are available in the Play-with-Docker graphical interface, as shown in the Supplementary File Figure 1 (below). More details can be obtained at . After accessing the BioPortainer URL, user may set up his/her own password and manage the Docker Engine through the BioPortainer graphical interface.


---
