# Spark in Docker (sparking docker)
This repo contains dockerfile for a spark cluster in docker container. 

## Instructions:

docker build -t sanjets/spark_base -f Dockerfile_base .
docker images

docker network create --driver bridge spark-net-bridge 

docker run -dit --name 194c4d1be1a9 --network spark-net-bridge --entrypoint /bin/bash sanjets/spark_base

The docker run command you provided starts a Docker container in detached (-d), interactive (-i), and tty (-t) mode.

    --name: Specifies a name for the container. The name spark-master is given to this container.
    --network: Attaches the container to a specified network. The network spark-net-bridge is specified in this case.
    --entrypoint: Overrides the default command to run when the container starts. The command /bin/bash is specified, which starts a bash shell inside the container.
    sanjeets/spark_base: The Docker image to use as the base for the container. The image sdesilva26/spark_master with tag 0.0.2 is specified.

This docker run command will start a container based on the sdesilva26/spark_master:0.0.2 image and will attach
it to the spark-net-bridge network. The container will run in detached mode, so it will run in the background. 
The default command in the image is overridden by the --entrypoint option to start a bash shell inside the container.

## To Do:
1. Single Node Spark Cluster (If we run just Dockerfile_base, it will act as single node cluster)
    Will come up with a set of instruction for this. 
2. Multi Node Spark Cluster
3. Spark with Airflow.



docker build -t sanjets/spark_submit -f Dockerfile_submit .

In order to launch pyspark prompt in base image. Follow below command
    go to pyspark directory and run this command ```. pyspark```


docker create network -d bridge spark-net

docker run -dit --name spark-master --network spark-net-bridge --entrypoint /bin/bash sdesilva26/spark_master:0.0.2
docker run -dit --name spark-master --network spark-net-bridge --entrypoint /bin/bash sdesilva26/spark_master:0.0.2


docker build -t sanjets/spark_master -f Dockerfile_master .


ToDo: Test and add instruction 
ToDo: reclone repo to get rid of rebase error

Point 2 in todo is done, need to test it

