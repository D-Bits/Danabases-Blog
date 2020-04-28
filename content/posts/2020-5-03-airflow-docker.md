---
layout: post
title: Getting Setup with Airflow and Docker
publishdate: 2020-04-27
updated: February 27, 2020
draft: true
tags: ["python", "automation", "docker"] 
---

Recently, I finally got a working, and expedient, development environment setting up for building pipelines with Apache Airflow. Because simply getting things setup and ready for development is one the biggest hurdles to overcome in working with Airflow, I decided to share my setup and experience with you, in hopes that you will find it useful, should you be required to use Airflow in the future.

## What is Airflow?

Airflow is an Apache Foundation top level project (TLP) that is designed to allow users to programmatically author workflows, represented as direct acyclic graphs, or DAGs. However, as incredibly powerful as Airflow is, it can require a whole bunch of complicated manual setup and configuration, should be installing it the old school way. This is where Docker comes into play.

## What is Docker?

*Docker* is software that allows you to 

## Setting Up `docker-compose.yml` File

Ultimately, our Airflow container, along with all of the attached services we will be relying on, will be specified in a `docker-compose.yml` file, containing the following code:

```yaml
version: '3.7'

services:
    postgres:
        image: postgres:12.1
        environment:
            - POSTGRES_USER=${POSTGRES_USER}
            - POSTGRES_PASSWORD=${POSTGRES_PASSWORD}
            - POSTGRES_DB=${POSTGRES_DB}
        ports: 
            - "543:5432"
        logging:
            options:
                max-size: 10m
                max-file: "3"
        volumes: 
            - pgdata:/var/lib/postgresql/data/airflow/

    webserver:
        image: puckel/docker-airflow:1.10.9
        restart: always
        depends_on:
            - postgres
        environment:
            - LOAD_EX=y
            - EXECUTOR=Local
        logging:
            options:
                max-size: 10m
                max-file: "3"
        volumes:
            - ./dags:/usr/local/airflow/dags
            # - ./plugins:/usr/local/airflow/plugins
        ports:
            - "8080:8080"
        command: webserver
        healthcheck:
            test: ["CMD-SHELL", "[ -f /usr/local/airflow/airflow-webserver.pid ]"]
            interval: 30s
            timeout: 30s
            retries: 3

# List the volumes we will be storing data in
volumes: 
    pgdata:      
```

If you are familiar with YAML and docker-compose files, you will see that our demo project consists of two services, each running inside a Docker container: `webserver` (our Airflow instance), and a PostgreSQL instance running inside of the `postgres` container.

## Final Thoughts

I realize that I didn't go over creating DAGs, or actually doing anything with Airflow (stay tuned for a future post regarding that), in the post. However, that was not my goal. My goal here was simply to show you a 