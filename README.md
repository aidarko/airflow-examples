## Overview

Exercise from https://www.udemy.com/course/the-ultimate-hands-on-course-to-master-apache-airflow/
course by Marc Lamberti.


## Local environment setup

Install Astro cli:
https://www.astronomer.io/docs/astro/cli/install-cli?tab=windows#install-the-astro-cli

Initialize environment:
```
astro dev init
```

Start Docker Compose:
```
astro dev start
```

Airflow Webserver: http://localhost:8080

Postgres Database: `localhost:5432/postgres`

Airflow Webserver credentials: `admin/admin`

## DAG
* is_api_available - check if API is available with Sensor
* fetch_stock_proces
* store_prices - upload to Minio
* format_prices - execute Spark job
* get_formatted_csv - read from Minio
* load_to_dw - store in Postgres (Metadata database)

## Project Contents

Your Astro project contains the following files and folders:

- dags: This folder contains the Python files for your Airflow DAGs. By default, this directory includes one example DAG:
  - `example_astronauts`: This DAG shows a simple ETL pipeline example that queries the list of astronauts currently in space from the Open Notify API and prints a statement for each astronaut. The DAG uses the TaskFlow API to define tasks in Python, and dynamic task mapping to dynamically print a statement for each astronaut. For more on how this DAG works, see our [Getting started tutorial](https://docs.astronomer.io/learn/get-started-with-airflow).
- Dockerfile: This file contains a versioned Astro Runtime Docker image that provides a differentiated Airflow experience. If you want to execute other commands or overrides at runtime, specify them here.
- include: This folder contains any additional files that you want to include as part of your project. It is empty by default.
- packages.txt: Install OS-level packages needed for your project by adding them to this file. It is empty by default.
- requirements.txt: Install Python packages needed for your project by adding them to this file. It is empty by default.
- plugins: Add custom or community plugins for your project to this file. It is empty by default.
- airflow_settings.yaml: Use this local-only file to specify Airflow Connections, Variables, and Pools instead of entering them in the Airflow UI as you develop DAGs in this project.