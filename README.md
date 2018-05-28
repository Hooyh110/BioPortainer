[![DOI](https://zenodo.org/badge/105034013.svg)](https://zenodo.org/badge/latestdoi/105034013)

<p align="center"><img width="427" height="545" src="https://raw.githubusercontent.com/LaBiOS/BioPortainer/master/images/logonew1.png"></p>

**BioPortainer** is a Portainer fork specifically designed for bioinformatics-related Docker applications. Bioportainer can be easily implemented, through deployment of a single Docker image, providing access to more than 60 pre-configured templates, available from BioPortainer´s unique repository, which will assist users through a straightforward and intuitive process for installation, configuration and management of a great variety of Docker-based bioinformatics tools, either in Docker Hosts or in Swarm Clusters.

---

## Test BioPortainer NOW!

To test the operation of BioPortainer and demonstrate the ease of use and the possibility of using the service in different operating systems and platforms we provide some installation templates on dply.co's servers.

**dply.co** allows the creation of an absolutely free server for two hours, and can be used for a longer time for payment. If you choose not to buy more time for the server, it is deleted automatically after 2 hours without any charge.

dply.co servers are hosted in the DigitalOcean cloud and have the following specifications:

- 1 CPU
- 512MB RAM
- 20GB Disk

We currently offer the following operating systems: CentOS 6, CentOS 7, Debian 7, Debian 8, Fedora 24, Fedora 25, Ubuntu 14.04, Ubuntu 16.04.

Test the BioPortainer on a machine with Ubuntu 16.04 by clicking the button:

[![Dply](https://dply.co/b.svg)](https://dply.co/b/77iNLq7X) 


---

## Deploy BioPortainer Image

To start BioPortainer, the user must have [Docker](https://docs.docker.com/engine/installation/) and [Docker Compose](https://docs.docker.com/compose/) installed on his operating system, according to the tutorials available in the project documentation. The BioPortainer image is available in the Docker Hub and its use is the recommended method of installation.

Two steps are required to start a container containing BioPortainer. In the first step, the BioPortainer image is downloaded from the Docker Hub servers to the host, and in the second, a container is created on the host machine with the default BioPortainer installation. If the host machine is a Linux, the following commands must be performed in the terminal:

```
$ docker pull labios/bioportainer
```

```
$ docker run -d -p 9000:9000 --name BioPortainer \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v ${PWD}/bioportainer_data:/data \
  labios/bioportainer \
  --templates http://bioportainer.ml/templates.json
```

BioPortainer can also be installed through the Docker Compose, according to the procedure below:

1 - Download docker-compose.yml:

```
$ wget http://bioportainer.ml/docker-compose.yml -P bioportainer
```

2 - Run Docker Compose:

```
$ cd bioportainer; docker-compose up -d
```

---

## Access BioPortainer


```
http://<IP or Host>:9000

or

http://localhost:9000
```

---

## Screenshot BioPortainer

- Menu Container

![Container](https://raw.githubusercontent.com/LaBiOS/BioPortainer/master/images/Screenshot%20from%202017-11-01%2006-31-53.png)

- Menu Images

![Images](https://raw.githubusercontent.com/LaBiOS/BioPortainer/master/images/Screenshot%20from%202017-11-01%2006-32-21.png)

- Application templates list

![Templates](https://raw.githubusercontent.com/LaBiOS/BioPortainer/master/images/Screenshot%20from%202017-11-01%2006-30-14.png)

- Application templates: Dugong CMD

![DugongCMD](https://raw.githubusercontent.com/LaBiOS/BioPortainer/master/images/Screenshot%20from%202017-11-01%2006-30-28.png)

- Application templates: Dugong GUI

![DugongGUI](https://raw.githubusercontent.com/LaBiOS/BioPortainer/master/images/Screenshot%20from%202017-11-01%2006-30-47.png)

- Application templates: Galaxy Stable

![Galaxy](https://raw.githubusercontent.com/LaBiOS/BioPortainer/master/images/Screenshot%20from%202017-11-01%2006-31-17.png)
