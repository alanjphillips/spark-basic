Using docker image from gettyimages

To run 'spark-basic'

Start up Spark master and worker:
    docker-compose up

To build spark-basic jar:
    sbt package

Copy spark-basic jar to Spark master docker container:
    docker cp target/scala-2.11/spark-basic_2.11-1.0.jar [CONTAINER_ID]:spark-basic_2.11-1.0.jar

Submit:
    bin/spark-submit --class "com.alaphi.sparkapp.SimpleApp" --master local[4] //spark-basic_2.11-1.0.jar


Other notes:
The SparkUI will be running at `http://${YOUR_DOCKER_HOST}:8080`. Usually http://192.168.99.100:8080/

To run `pyspark`, exec into a container:
    docker exec -it sparkbasic_master_1 /bin/bash
    bin/pyspark

To run `SparkPi`, exec into a container:
    docker exec -it sparkbasic_master_1 /bin/bash
    bin/run-example SparkPi 8

