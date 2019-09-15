# QGIS Rancher

*This project contains sets of information about QGIS website infrastructure and orchestration.*

[insert QGIS infrastructure diagram here]

# Installation

## Rancher

In this project, [Rancher (v1.6)](https://rancher.com/docs/rancher/v1.6/en/) is used for managing all services that we want to spin up.
So we need to spin up our rancher server first. 

1.  Make sure docker-compose already installed on your server/machine.
    ```bash
    apt install docker.io
    apt install python-pip python-setuptools pycparser
    pip install docker-compose
    ```
    
2.  Clone this project repository to your desired directory.
    ```bash
    git clone [the repository]
    ```

3.  Set environment variables (for SSL Let's Encrypt configuration):

    Create `.env` file in this project root directory and copy content from `env.template` and edit the variables as you wish.

    > `ADMIN_EMAIL` (eg: admin@qgis.org)
    
    > `DOMAIN_NAME` (eg: rancher.qgis.org *make sure this is a valid domain name)
    
4.  Run the compose file in this project root directory.
    ```bash
    docker-compose up
    ```
    To check the status of the services, run:
    
    `docker logs --follow rancher-ssl` -> for certificate generation status
    
    `docker logs --follow rancher-server` -> for rancher server status
    
5.  Rancher service should be now accessible on your domain.

## Rancher Catalog

Add rancher catalog from this remote repository to your rancher server.

1. Manage rancher catalog from catalog page.

2. Add new catalog source from this remote repository.

## QGIS Feed

This section will describe how to setup [QGIS Feed](https://github.com/qgis/qgis-feed) services using rancher server.

### Hetzner Cloud

This applied if you are running your rancher server on Hetzner infrastructure and decided to create a new host for this service also using Hetzner infrastructure.

1. Go to `Add a host` option on your rancher server.

2. Activate Hetzner infrastructure option (if it's not activated).

3. Generate API key on your Hetzner project.

4. Add the API key to the rancher server and configure your new host.

## QGIS Plugins

[available soon]

## QGIS Changelog

[available soon]

## QGIS Documentation

[available soon]

## QGIS Website

[available soon]
