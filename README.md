# Data Modeling with Apache Cassandra
The repository shows how to model user activity data to create a database and ETL pipeline in Apache Cassandra.


## Getting Started

### Setup Apache Cassandra

In this section, we describe how to install and start a Apache Cassandra database on local machine. The instructions apply to Linux and the method of installing Cassandra that we will use is through installing a Docker image:

1. Install Docker from apt packages
    ```bash
    sudo apt install docker.io
    ```

2. Installing the docker image
    ```bash
    docker pull cassandra:latest
    ```
    
    This `docker pull` command will get the latest version of the official Apache Cassandra image available from the Dockerhub.

3. Start the daemon manually
    ```bash
    sudo dockerd
    ```
    
4. In a second terminal, start Cassandra with a docker run command:
    ```bash
    docker run -p 9042:9042 --name cassandra_container cassandra:latest
    ```
    
    The `--name` option will be the name of the Cassandra cluster created.

**Troubleshooting**

- If you already have created a container of a specific name (e.g. cass_cluster), you can remove it by
  ```bash
  docker rm cass_cluster
  ```

- If you already have created a container of a specific name, you can remove it by
  ```bash
  docker rm cass_cluster
  ```
  
- When that container is sill running you need to stop it first before you can delete it with
  ```bash
  docker stop cass_cluster
  ```
  
- To get a list of existing containers and their names simply invoke
  ```bash
  docker ps -a
  ```


