# To download the httpd-ab image and to run the container
docker run -dit --name httpd-ab -v /var/www/html:/usr/local/apache2/htdocs/ httpd

# To access the bash in the running container
docker exec -it httpd-ab bash

# To generate the load to the load balancer DNS, replace load balancer DNS with your ALB DNS(EC2 console --> Loadbalancers --> Select the newly created ALB and copy the DNS)
ab -r -c 500 -n 5000000 http://ecs-d-publi-h9d4ufps3s74-2106267235.us-east-1.elb.amazonaws.com/

# To stop the apache bench processor (ctrl for windows, cmd for mac)
ctrl/cmd + c

# To exit from the running container (type exit & hit enter)
exit

# To check running containers
docker ps -a

# To kill the running container with the name httpd-ab
docker kill httpd-ab