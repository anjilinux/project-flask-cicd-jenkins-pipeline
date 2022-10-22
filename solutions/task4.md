# Task4 solution
#### This file contains all the necessary information’s about my decisions regarding to task4 that is in [instructions.md](instructions.md) file.
#### Answers by ["Mohammad Taghadosi"](https://linkedin.com/in/mtaghadosi)

# Provided solution for task 4:
In the tasks before I implicitly provided my solutions. As you mentioned there is many information needed for designing a complete solution for this app. So, with this information in my hand and also use of some imagination I clarify the complete solution at the end of this assessment.

- We use cloud (AWS or GCP or on-premises).
- In that Cloud we setup our environment.
- The environment has an auto scaling deployment for our nginx web-server and our static files (JavaScript files) and also has a backend file storage to use as a Persistence volume (PV) for our files and databases (this also can be on premises cloud or it can be AWS S3 etc.).
- Also, we need some `statefull` services for our Databases
- Also, the environment has an auto scaling deployment for our PostgreSQL .
- Also, the environment has some internal and external services to be able to communicate with each other and the outside world, in the real world we can use ingress for DNS an HTTPS.
- Also, we have an autoscaling deployment for our backend python API app that must be able to comminute with DB and nginx, so also, we need to use service mesh too.
- Also, we have to use `ConfigMap` and `Serret` files to store our `connectionString` and `user/pass` safely
- We use Jenkins server for CI/CD automation procedures the code explained in [task3](/solutions/task3.md).
- I used YAML files for all of my demonstrations so you can check them in YAML directory.



 ### Answers menu:
- [Task-1](/solutions/task1.md)
- [Task-2](/solutions/task2.md)
- [Task-3](/solutions/task3.md)
- [Task-4](/solutions/task4.md)
- [Task-5](/solutions/task5.md)

