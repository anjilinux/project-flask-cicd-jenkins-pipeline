# Task2 solution
#### This file contains all the necessary information’s about my decisions regarding to task2 that is in [instructions.md](instructions.md) file.
#### Answers by ["Mohammad Taghadosi"](https://mtaghadosi.ir)

# Provided solution for task 2:
 Task 2 doesn’t seem to need some solutions, it’s a pre-description for task 3 and task 4. But I want to mention that if we need to start another project from our original software we can just copy and start a new project or we can use another branch of our git repository. I also want to mention that regarding to the project that we have, we also need a `postgres` database server so I can install it on the k8s on-premises cloud by using helm or manually. I prefer the hard way, because it is more flexible, I created a YAML file that contains all the necessary information to create a complete postgresSQL deployment:
 - [postgresSQL ConfigMap](/YAML/postgres-configmap.yaml)
 - [PostgresSQL Deployment YAML file](/YAML/dep-postgresDB.yaml)

Also i created a PersistentVolume (PV) and a PersistentVolumeClaim (PVC) for storing the database in it:
 - [PersistentVolume (PV) for Postgres DB](/YAML/create-pv-for-postgres.yaml)
 - [PersistentVolumeClaim (PVC) for Postgres DB](/YAML/create-pvc-for-postgres.yaml)

Also we need a service for our DataBase:
 - [Loadbalancer Service for postgres](/YAML/create-loadbalancer-service-postgres.yaml)

Time to install the Database on the cloud, pay attention that I created a namespace named `postgres` and deployed all database in it: 

 ```
 kubectl apply -f postgres-configmap.yaml
 kubectl apply -f create-pv-for-postgres.yaml
 kubectl apply -f create-pvc-for-postgres.yaml
 kubectl apply -f create-loadbalancer-service-postgres.yaml
 kubectl apply -f dep-postgresDB.yaml
 kubectl autoscale deployment postgres -n postgres --cpu-percent=60 --min=3 --max=100
 ```
 #### with auto scale enabled in databases we actually need `statefull` services for sincing the databases. I will NOT cover that in this demonstration.

## I ALSO strongly recommend that we use `ConfigMap` for database connection info and use `Secret` for safe storing username/password combinations, but as long as in this project we defined that configs in the `.env` file I will skip this process. I just want you to know in the industrial level I never ever do that, so I demonstrated the ConfigMap file in the postgres YAML file.



### Answers menu:
- [Task-1](/solutions/task1.md)
- [Task-2](/solutions/task2.md)
- [Task-3](/solutions/task3.md)
- [Task-4](/solutions/task4.md)
- [Task-5](/solutions/task5.md)