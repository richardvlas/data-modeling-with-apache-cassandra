# Data Modeling with Apache Cassandra
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analysis team is particularly interested in understanding what songs users are listening to. Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.

They'd like to create an Apache Cassandra database which can create queries on song play data to answer the questions. The role of this project is to create a database for this analysis. We'll be able to test the database by running queries given to us by the analytics team from Sparkify to create the results.

## Project Description
In this project, we'll model data with Apache Cassandra and build an ETL pipeline using Python. We will need to model the data by creating tables in Apache Cassandra to run queries. The ETL pipeline transfers data from a set of CSV files within a directory to create a streamlined CSV file to model and insert data into Apache Cassandra tables.

## Project Structure
The project includes the following files and folders:

```
├── README.md
├── Data_modeling_with_Apache_Cassandra.ipynb
├── event_datafile_new.csv
├── requirements.txt
├── assets
└── event_data
```

- `README.md` - a markdown file giving an overview of the project and explaining the project structure
- `Data_modeling_with_Apache_Cassandra.ipynb` - implements the logic of the ETL pipeline, iterates through each event file in event_data to process and create a new CSV file in Python. 
- `event_datafile_new.csv` - processed denormalized dataset file from raw event data files
- `requirements.txt` - stores information about all the Python libraries, modules, and packages that are used in the  project. 
- `assets` - folder with project assests (e.g. images)
- `event_data` - directory of CSV files partitioned by date








## Getting Started

### Dependencies

You will need to install all Python dependencies that are stored in the [requirements.txt](requirements.txt) file. 

To install them, first open a terminal window in the folder of this repository and create & activate a virtual environment: 

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Then install the dependencies from the [requirements.txt](requirements.txt) file:

```bash
pip install -r requirements.txt 
```

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


