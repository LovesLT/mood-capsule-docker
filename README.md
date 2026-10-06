# 🌟 Mood Capsule Capstone Project

Hey team! Welcome to the Mood Capsule repository. We’ve got the whole stack containerized with Docker Compose here—meaning the MySQL database, Spring Boot backend, and Angular frontend will all spin up smoothly together on your machine with a single command, no matter if you're on Windows, Mac, or Linux.

Here is how to get it up and running on your computer from scratch.

---

### Step 1: Grab what you need
Make sure you have these two things installed before starting:
1. **Git** (to clone the repo)
2. **Docker Desktop** (make sure the app is actually open and running in your system tray/menu bar!)

---

### Step 2: Clone the Repo
Open up your terminal or PowerShell and clone the project:

bash
git clone [https://github.com/LovesLT/mood-capsule-docker.git](https://github.com/LovesLT/mood-capsule-docker.git)
cd mood-capsule-docker

### Step 3: Set up your .env file
We use a local environment file to handle database credentials safely without pushing secrets to GitHub.

Find the .env.example file in the root folder.

Make a copy of it and name the new file .env:

Windows (PowerShell): Copy-Item .env.example .env

Mac / Linux: cp .env.example .env

The default settings inside work right out of the box for local testing, so you're good to go!

### Step 4: Fire it up! 🐳
Once your .env file is in place, run this single command in the root folder:

Bash
docker compose up --build -d
Give it about 15–20 seconds on your very first run. The database has a health check to make sure it's fully ready before the backend kicks off and runs your Flyway migrations automatically.

### Step 5: Check it out
Once everything is running, you can access the app here:

Frontend UI: http://localhost:4200

Backend Swagger Docs: http://localhost:8080/swagger-ui/index.html

Useful Commands for Later
To check backend logs if something acts up:

Bash
docker compose logs -f backend
To shut everything down:

Bash
docker compose down
To completely wipe the database and start fresh (if migrations get messy):

Bash
docker compose down -v
docker compose up --build -d
