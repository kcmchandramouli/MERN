# Dockerize MERN
-   Create a Network so that the docker contains can talk to each other.
    -   ```docker network create <network name>```
-   Write a [Dockerfile](mern/frontend/Dockerfile) for frontend part with the given commands in the master branch.
-   Create a Front End image.
    -   ```docker build -t <mern-frontend image name> <Path to the frontend dockerfile>```
-   Create a Front End container
    -   ```docker run --name=<Container_Name> --network=<Network_Name> -d -p 5173:5173 <mern-frontend image>```
-   Now you can access your frent end application in browser with ```localhost:5173```. Here you can just see the frent end application but can't do anything as you don't have the backend application.
-   But before running the backend container. Create Data Base. Running Data Base first even before the front end is the best practice.
-   Create a Data Base 
    -   ```docker run --network=<Network_Name> --anme <Data_Base_Name> -d -p 27017:27017 -v <Volume_Path_In_HOST>:<Volume_Path_In_Container> <Data_Base_Image>```
    -   Now you can access in web brouser with ```localhost:27017```.
-   Write a [Dockerfile](mern/backend/Dockerfile) for backend part with the given commands in the master branch.
-   Create a backend image.
    -   ```docker build -t <Image_Name> <Path_To_The_Backend_Dockerfile>```
-   Create a BackendEnd container
    -   ```docker run --name=<Container_Name> --network=<Network_Name> -d -p 5050:5050 <mern-backend image>```
    -   You can access in web brouser with ```localhost:5050```.

-   If all the containers you can save/edit/delete the employe details.

## Using Docker Compose
-   We can build docker images & Create containers for this 3 tire application at one go with docker-compose.
-   Write Dockerfiles for Frentend & Backendend parts with the commands given in master branch.
-   For that Create a [```docker-compose.yml```](docker-compose.yml) file.
-   The compose file should contain Service, Network & Volume.
