###Creating Docker Image 


#Step to Deploy the docker image in Azure 
-create a Resource Group if Don't have it 

after that click on resource group and click on crete button 
-in left side nav vabar you will get a list of app choose the containeraztion 
-choose the container ->  Container Instances.

On the Basics page, choose a subscription and enter the following values for Resource group, Container name, Image source, and Container image.

Resource group: Create new > myresourcegroup
Container name: mycontainer
Image source: Quickstart images
Container image: give yours !!!
<img width="1055" alt="image" src="https://github.com/user-attachments/assets/8ecb2032-6354-4c44-902b-64e140449e5e" />

<img width="1164" alt="image" src="https://github.com/user-attachments/assets/c2c0d12d-040a-454c-af08-09696163bfbb" />


OR CLI Method !!!

az container create \
  --resource-group <your-resource-group-name> \
  --name badminton-server-instance \
  --image vashuvd/badminton-server:latest \
  --cpu 1 \
  --memory 1 \
  --ports 8089 \
  --os-type Linux \
  --location westindia \
  --public-ip

OR you can setup the yaml file and direct deploy from your local terminal 
- configure your azure account to your terminal
- configure your yaml file
     apiVersion: '2025-02-10'
   location: westindia
   name: badminton-server-instance
   properties:
     containers:
     - name: badminton-server
       properties:
         image: vashuvd/badminton-server:latest
         resources:
           requests:
             cpu: 1
             memoryInGb: 1
     osType: Linux
     ipAddress:
       type: Public
       ports:
       - port: 8089

   
