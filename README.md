# helloworld-client-server
Hello World dotnet core web api backend server and nginx frontend client application with kubernetes deployment scripts

To build and deploy the project using a Continous Integration server, follow the below commands:

git clone https://github.com/sreesanpd/helloworld-client-server

cd helloworld-client-server/helloworld-api

dotnet build 

dotnet publish

sudo docker build . -f Dockerfile -t sreesanpd/helloworld-api:latest

cd ../frontend

sudo docker build . -f Dockerfile -t sreesanpd/frontend:latest

sudo docker push sreesanpd/frontend:latest 

sudo docker push sreesanpd/helloworld-api:latest

cd ../kubernetes-deployment

kubectl delete -f frontend.yaml,helloworld-api-deployment.yaml,helloworld-api-service.yaml

kubectl create -f frontend.yaml,helloworld-api-deployment.yaml,helloworld-api-service.yaml


