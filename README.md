# GitLab on docker for WSL2
## Overview
Docker files to host GitLab and GitLab Runner on WSL2.

## Requirements
- docker
- docker-compose

## Usage
1. Set the IP address of the Windows host to the environment variable `WINDOWS_IP`.

    ```bash
    export WINDOWS_IP = 192.168.1.10
    ```

1. Enable the docker service.

    ```bash
    sudo service docker start
    ```

1. Run the following command in the directory where the `docker-compose.yml` exists.

    ```bash
    docker-compose up -d
    ```

1. GitLab can be accessed from `http://{WINDOWS_IP}:8080/`
    
