                                                  Simple TODO API using FastAPI, PostgreSQL, and Docker Compose

-----------------------------------------------------------------------------------------------------

1. Project Overview:

  This project is a basic TODO application that demonstrates how to containerize an application along with a database using Docker and      Docker Compose.

The application provides three simple operations: 
  create a todo, 
  list todos, 
  and delete a todo.

------------------------------

2. What Does This Application Do?

The application provides a REST API with the following functionalities:

-> Create a todo item

-> Retrieve all todo items

-> Delete a todo item

---------------------------------

3. Architecture:


      FastAPI App(Application Logic)      <---->     PostgreSQL DB (Persistent Data)  


Both services are managed and connected through Docker Compose.

-----------------------------------

4. List of Files and their purpose:

-> app.py -- Main FastAPI application containing API logic

-> requirements.txt -- Python dependencies for the app

-> Dockerefile -- Instructions to build the FastAPI application container

-> docker-compose.yml -- Defines and runs app + database containers

-> .dockerignore -- Excludes unnecessary files from Docker build

-> .env.example -- Template file showing environment variables

-> README.md -- Documentation for understanding and running the project

------------------------------------------



5. What Needs to Be Installed?

Before running this project, ensure the following are installed:

-> Docker Desktop

-> Git to clone the repository

-> You do not need to install Python or PostgreSQL manually because Docker manages them.

----------------------------------------

6. How to run the project:

-> Redirect to the file using change directory (cd) command.

-> Create virtual environment for the application and activate it using:
     
    python -m venv venv

    .\venv\Scripts\Activate

-> Start the application using:

    docker compose up --build

-> This will:

    Build the FastAPI application image

    Start the PostgreSQL database

    Start the FastAPI server on port 8000

-> Keep the above terminal open.

    Open a new terminal window to test the API


--------------------------

7. API Endpoints:

-> Create a todo:

    Invoke-RestMethod -Method Post -Uri "http://localhost:8000/todos" `
    -Body '{"title":"Buy milk"}' `
    -ContentType "application/json"

Output we got:

id  -  title

1   -  Buy Milk

-> Get all todos:

    Invoke-RestMethod -Method Get -Uri "http://localhost:8000/todos"

Output we got:

  id  -  title

  1  -   Buy Milk

  2   -  Buy Milk

-> Delete a todo:

    Invoke-RestMethod -Method Delete -Uri "http://localhost:8000/todos/1"

Output we got:

Message: 

Todo deleted


-----------------------------

 8. Common commands for managing containers:
    
-> docker compose up --build -- Build and start services

-> docker compose up -d -- start in background

-> docker compose down -- stop services 

-> docker compose down -v -- stop and delete database volumes
 
-> docker compose ps -- view running containers

-> docker compose logs -f -- view logs

------------------------------------------

9. How to verify your application works:

-> Run the application:

    docker compose up --build


-> In a separate terminal, check the todo list:

    Invoke-RestMethod -Method Get -Uri "http://localhost:8000/todos"

-> Create a todo list:
     
    Invoke-RestMethod -Method Post -Uri "http://localhost:8000/todos" `
    -Body '{"title":"Test Item"}' `
    -ContentType "application/json"

-> Retrieve todos again and confirm the item appear:

    Invoke-RestMethod -Method Get -Uri "http://localhost:8000/todos"

-------------------------------------
    
10. Conclusion:

    If the item appears correctly, the application and database are working together as expected.By building a FastAPI-based TODO service and running it together with a PostgreSQL database inside Docker containers, how environment variables are used for configuration, and how Docker Compose helps orchestrate multi-service environments.

 ----------------------------------------

 Author: Prasanna Kumar
 
 Subject: Creating a Simple TODO API using FastAPI, PostgreSQL, and Docker Compose

 EMP ID: RIS00427
