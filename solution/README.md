1. pull the image using below command 
  docker pull infracloudio/csvserver:latest
  docker run -it infracloudio/csvserver:latest sh 
  netstat -tulpn | grep LISTEN  - this command run inside the container to check on which port it's exposing application 
  
2.Created the gencsv.sh file and generated the inputFile from script than run the below command

 docker run -it -p 9300:9300 -v C:\test\inputFile:/csvserver/inputdata infracloudio/csvserver:latest

   access application using http://localhost:9300
 
 3. To change colour run the below command
 
 docker run -it -p 9300:9300 --env CSVSERVER_BORDER=Orange -v C:\test\inputFile:/csvserver/inputdata infracloudio/csvserver:latest
 
 4. Created docker-compose.yaml file run the command docker-compose up -d 

5.Pull the promotheus image and create prometheus.yaml file and add all config in docker-compose.yaml 

6.access the promethes using http://localhost:9090

access the metrics using http://localhost:9300/metrics