Some playing around with Apache Spark can fit in here...
Using docker image from gettyimages

The SparkUI will be running at `http://${YOUR_DOCKER_HOST}:8080`. Usually http://192.168.99.100:8080/

To run `pyspark`, exec into a container:

    docker exec -it sparkbasic_master_1 /bin/bash
    bin/pyspark

To run `SparkPi`, exec into a container:

    docker exec -it sparkbasic_master_1 /bin/bash
    bin/run-example SparkPi 8
