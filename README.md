# docker-practice-project
#create mongo container:
```  
docker run -d `
>> -p 27017:27017 `
>> --name mongodb `
>> --network mongo-network `
>> -e MONGO_INITDB_ROOT_USERNAME=admin `
>> -e MONGO_INITDB_ROOT_PASSWORD=password `
>> mongo
```
#create mongo-express container:
```
docker run -d `
>> -p 8081:8081 `
>> --name mongo-express `
>> --network mongo-network `
>> -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin `
>> -e ME_CONFIG_MONGODB_ADMINPASSWORD=password `
>> -e ME_CONFIG_MONGODB_URL="mongodb://admin:password@mongodb:27017" `
>> mongo-express
```
#terminal-veiw:
![image](https://github.com/user-attachments/assets/d2924989-5c12-4394-854d-9c2b1132d588)

# in vscode clone this repo

copy and paste in vscode terminal.
REPO:
```
git clone https://github.com/shradha-khapra/docker-testapp.git
```
change directory to the app file and run the node js app :
```
cd docker-testapp
node server.js
```
- its currently hosted on : localhoat:5050 (open in browser)
- ![image](https://github.com/user-attachments/assets/29ed8ff3-69cc-4bf4-8b06-3823c4348dea)

- create new db in mongo-express ie hosted in : localhost:8081 (username:admin password:pass)
- create new db with same same as in server.js file
- add a sample user record in JSON format.
- ![image](https://github.com/user-attachments/assets/a0901b3c-f16e-455d-8c89-463a9c63b03b)

- and got to localhost:5051/getUsers to check if its updated and connected
- if its connected it will show the same data
- ![image](https://github.com/user-attachments/assets/965c8605-0cbc-4bd9-8366-1f0f0737d045)
- navigate back to localhost:5050 and add a new user
- ![image](https://github.com/user-attachments/assets/291ca6ac-a8de-44b2-ad59-d489c0f50c7c)
- check in mongo-express page if itss updated (refresh the page)
- ![image](https://github.com/user-attachments/assets/05d0b29f-5e03-48f9-9bc6-83151b53bfd3)
#  architecture daigram:
![image](https://github.com/user-attachments/assets/20313aed-4ebc-4bc3-a89a-7784358abd83)

source : https://www.youtube.com/watch?v=exmSJpJvIPs&t=1617s


