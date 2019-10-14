commit code
Build the code through maven
Sonar code analysis
Archiving artifacts[packages]
Dockerization[docker build]
Push image to docker hub/nexus
Deploying docker image into the kubetnets node
                                CREATE PIPELINE
                                EX:GOCD[pipeline name]
Step1:maven clean


Step2:mvn compile



step3: mvn package



step4:dockerization

build
--no-cache
--tag
vijju:latest✔
--tag
vijju:commit
--label
org.label-schema.name="vijju"
--file
Dockerfile
.
  
  
  
step5:dockerhub
  
docker tag vijju ramyareddymallu/vijju:latest
docker login -u ramyareddymallu -p rajasekharreddy
docker push ramyareddymallu/vijju:latest

step6:deploying

cd devops/QA/transit
ansible-playbook -i hosts playbook.yml
