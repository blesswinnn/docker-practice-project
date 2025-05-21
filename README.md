# 🚀 Docker Practice Project: MongoDB + Mongo Express + Node.js

This project demonstrates how to containerize a simple **Node.js application** and connect it with **MongoDB** using Docker and Docker Compose principles. You’ll also use **Mongo Express** as a lightweight admin UI to interact with your MongoDB instance.

---

## 📦 What You’ll Set Up

- 🐳 MongoDB container
- 🌐 Mongo Express container (MongoDB GUI)
- ⚙️ Node.js app connected to MongoDB
- 🧪 Real-time database interaction

---

## 🧰 Prerequisites

- Docker installed
- VS Code or any terminal
- Basic understanding of terminal commands

---

## 🛠️ Step-by-Step Setup

### 1. **Create a Docker Network**

# 🚀 Docker Practice Project: MongoDB + Mongo Express + Node.js

This project demonstrates how to containerize a simple **Node.js application** and connect it with **MongoDB** using Docker and Docker Compose principles. You’ll also use **Mongo Express** as a lightweight admin UI to interact with your MongoDB instance.

---

## 📦 What You’ll Set Up

- 🐳 MongoDB container
- 🌐 Mongo Express container (MongoDB GUI)
- ⚙️ Node.js app connected to MongoDB
- 🧪 Real-time database interaction

---

## 🧰 Prerequisites

- Docker installed
- VS Code or any terminal
- Basic understanding of terminal commands

---

## 🛠️ Step-by-Step Setup

### 1. **Create a Docker Network**

```bash
docker network create mongo-network
```
### 2. Start MongoDB Container
```
docker run -d \
  -p 27017:27017 \
  --name mongodb \
  --network mongo-network \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=password \
  mongo

```

### 3. Start Mongo Express Container
```
docker run -d \
  -p 8081:8081 \
  --name mongo-express \
  --network mongo-network \
  -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
  -e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
  -e ME_CONFIG_MONGODB_URL="mongodb://admin:password@mongodb:27017" \
  mongo-express

```
### 📁 Clone Node.js App Repo
```
git clone https://github.com/shradha-khapra/docker-testapp.git
cd docker-testapp

```

### 🚀 Run the Node.js App
```
node server.js
```
🖥️ Now, the app is hosted at:
👉 http://localhost:5050

### 🗂️ Mongo Express UI
Access Mongo Express:
👉 http://localhost:8081
Username: admin
Password: password

📌 Inside Mongo Express:
Create a new database (same name as in server.js)

Add a sample user record in JSON format

Example:

```
{
  "name": "John Doe",
  "email": "john@example.com"
}
```
### 🔗 Test Database Connectivity
🧪 View users via Node.js app:
Visit:
👉 http://localhost:5050/getUsers
If the app and DB are connected properly, you’ll see the user data you added via Mongo Express.

### ➕ Add New User via Node App
From the main page (localhost:5050), submit a new user.
Then go back to Mongo Express (localhost:8081) and refresh the collection to confirm the new data was added.

### 🧱 Architecture Diagram

![image](https://github.com/user-attachments/assets/20313aed-4ebc-4bc3-a89a-7784358abd83)

### 🧠 Insights
Containers run in isolation but communicate via a shared Docker network

Mongo Express simplifies interacting with your DB visually

Real-time updates between app ↔ DB ↔ GUI

### 📚 Video Tutorial Source
Watch the full project walkthrough here:
🎥 YouTube Tutorial

### 🙌 Credits
Project idea and demo inspired by Shradha Khapra

### 📜 License
This project is for learning purposes. No license restrictions.

# WORKFLOW SCREENSHOTS
![image](https://github.com/user-attachments/assets/29ed8ff3-69cc-4bf4-8b06-3823c4348dea)
![image](https://github.com/user-attachments/assets/a0901b3c-f16e-455d-8c89-463a9c63b03b)
![image](https://github.com/user-attachments/assets/965c8605-0cbc-4bd9-8366-1f0f0737d045)
![image](https://github.com/user-attachments/assets/291ca6ac-a8de-44b2-ad59-d489c0f50c7c)
![image](https://github.com/user-attachments/assets/05d0b29f-5e03-48f9-9bc6-83151b53bfd3)



