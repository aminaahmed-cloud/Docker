</details>

******

# Demo App - Developing with Docker

This repository contains a demo application that demonstrates a simple user profile app developed using Docker. The application includes:

- **Frontend:** `index.html` with pure JavaScript and CSS styles.
- **Backend:** Node.js backend with the Express module.
- **Database:** MongoDB for data storage.

All components of this application are Docker-based.

## Getting Started

### Starting the Application with Docker

#### Step 1: Create Docker Network

```bash
docker network create mongo-network 
```


<img src="https://i.imgur.com/LGAj5lQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>



<img src="https://i.imgur.com/FUDsZtr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</details>

******

Step 2: Start MongoDB

```bash
docker run -d -p 27017:27017 \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
--name mongodb --net mongo-network mongo
```

<img src="https://i.imgur.com/GVGKPaA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

Step 3: Start Mongo Express

```bash
docker run -d -p 8081:8081 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
--net mongo-network --name mongo-express \
-e ME_CONFIG_MONGODB_SERVER=mongodb \
mongo-express
```


<img src="https://i.imgur.com/qL2nt8Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

Step 4: Open Mongo Express from Browser

Open http://localhost:8081 in your web browser.

Step 5: Create Database and Collection in Mongo Express

Create a new database named "user-account". Inside the "user-account" database, create a new collection named "users".

</details>

******

Step 6: Start Node.js Application Locally

```bash
cd app
npm install 
node server.js
```
</details>

******

Step 7: Access Node.js Application UI from Browser

Open http://localhost:3000 in your web browser.

</details>

******

# Using Docker Compose
Step 1: Start MongoDB and Mongo Express

```bash
docker-compose -f docker-compose.yaml up
```

You can access Mongo Express at http://localhost:8080 from your browser.

</details>

******

Step 2: Create Database and Collection in Mongo Express

In the Mongo Express UI, create a new database named "user-account". Inside the "user-account" database, create a new collection named "users".

</details>

******

Step 3: Start Node.js Application

```bash
cd app
npm install
node server.js
```
<img src="https://i.imgur.com/hMrF3Fu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

Step 4: Access Node.js Application from Browser

Open http://localhost:3000 in your web browser.

# Building a Docker Image

To build a Docker image from the application, run the following command in the root directory of your project:

```bash
docker build -t my-app:1.0 .
```

The dot "." at the end of the command denotes the location of the Dockerfile.

<img src="https://i.imgur.com/piLoaYb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</details>

******

