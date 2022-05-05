PART 1
1. Install git:

    apt-get install git

2.To download and install docker-compose

   sudo curl -L "https://github.com/docker/compose/release/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   sudo chmod +x /usr/local/bin/docker-compose
   docker-compose --version


3. Pull the latest docker images:

   docker pull infracloudio/csvserver:latest
   docker pull prom/prometheus:v2.22.0

4. Clone the specified repo:

   git clone https://github.com/infracloudio/csvserver.git

5. Run containers using docker images:

   docker run -d -i infracloudio/csvserver/inputFile:/csvserver/inputdata infracloudio/csvserver:latest

6. To run docker on specified portal

   docker run -d -i -v /home/ubuntu/csvserver/inputFile:/csvserver?inputdata -p 9393:9300 infracloudio/csvserver:latest

7. Running docker image with environment variable specified

   docker run -d -i -v /home/ubuntu/csvserver/inputFile:/csvserver?inputdata --env CSVSERVER_BORDER+Orange -p 9393:9300 infracloudio/csvserver:latest


PART 2

By using a docker container file we have written a YAML file to finish Part 1

    docker-compose up

PART 3

We have to collect the matrix from the application so all the configuration files for Promotheus. It is existed Promotheus we are calling from these promotheus containers from the composed files.

    docker-compose up
