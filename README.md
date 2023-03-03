# db-cassandra-setup
This repository contains a Cassandra service dockerised for quick access

## Getting started
- Pull down repository
- Setup prerequisites
- Run `docker-compose up`

## Querying
Once Docker has started, get Container ID and exec in
`docker ps`
`docker exec -it <containerID> /bin/sh`
`cqlsh`

### Create Keyspace
 <code>CREATE KEYSPACE perfmonitor <br>
   ... WITH replication = {'class' : 'SimpleStrategy', 'replication_factor': 1}; </code>

### Use Keyspace
   `USE perfmonitor ;`

### Create Table
<code>
CREATE TABLE app_instance( <br>
               ... id uuid, <br>
               ... app_name text, <br>
               ... proc_id text, <br>
               ... host_id text, <br>
               ... cpu_time int, <br>
               ... num_io_ops int, <br>
               ... PRIMARY KEY (id));
               </code>

### Get info on Table
`DESCRIBE app_instance ;`

## Prerequisites
These steps should be familiar if you're familiar with Docker

- Install [Docker](https://docs.docker.com/docker-for-mac/)

## Terminate service
- Destroy docker images `docker-compose down -v` 

## Source
[Cassandra data modeling essentials](https://www.linkedin.com/learning/cassandra-data-modeling-essential-training-17423744/install-cassandra)

