FROM maven:3.6.3-openjdk-11
COPY . ./app
WORKDIR /app
RUN mvn clean package
WORKDIR /app/target
EXPOSE 8080
CMD java -jar rest-service-initial-0.0.1-SNAPSHOT.jar
#docker stop $(docker ps -a -q)
#docker rm $(docker ps -a -q)
#docker rmi $(docker images -q)
#docker build -t arifuse:orchestrator .
#docker run -it -p 8080:8080 --name orchestrator_cont arifuse:orchestrator
#sudo docker build -t mrodfuentes/rtest .
#sudo docker run -it -p 8080:8080 --name rtest_cont mrodfuentes/rtest
#sudo docker push mrodfuentes/rtest:latest
#sudo docker stop rtest_cont
#sudo docker rm rtest_cont
#sudo docker rmi rtest_img
#kubectl run rtest-spring --image=mrodfuentes/rtest-spring:latest