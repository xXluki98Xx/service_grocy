<!--
Shields
Headers
-->

# Hodgins: 3rd Party Service grocy

A repository, providing an grocy service for Hodgins Server.

## Description

This repository provides an ansible-playbook which will:

- pull the image
- create service folder
- create a systemd service file
- start and enable the systemd service
- open up the firewall

## Requirements

A hodgins server or compatible deployment must be provided.

## Install

Clone the repository next to you existing Hodgins Server code.

```
git clone https://github.com/xXluki98Xx/service_grocy.git
```

Afterwards, you can install the service.

```
ansible-playbook -i <path-to-your-inventory> -k -K -u <hodgins-users> playbooks/service_grocy.yml
```

## Usage

The installation will respond to you with a running grocy service.
Now you can enter the report page:

```
http://hodgins-ip:6060
```

To interact with the container, you will have multiple options.

Via Systemd on your hodgins server (recommended), you can interact with the service
the same way you are interacting with other services on your system.

Get the status:

```
$ sudo systemctl status podman
```

Restart the service (and apply updated images):

```
$ sudo systemctl restart service_grocy
```

Services in Hodgins are running in containers. You can interact with the containers
via Podman.

Check all containers:

```
podman ps
```

Restart a running container:

```
podman container restart service_grocy
```

## Contribute

Thank you so much for considering to contribute! We are happy, when someone is
joining the hard work. Please feel free to contribute, after having a look at
the [Conventions](https://github.com/while-true-do/doc-library/).

- [Bugs and Feature Requests](https://github.com/xXluki98Xx/service_grocy/issues)
- [Pull Requests](https://github.com/xXluki98Xx/service_grocy/pulls)
