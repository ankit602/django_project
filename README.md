Django Video Upload & Subtitle Extraction
This project is a Django-based web application that allows users to upload videos, extract subtitles, and display them as closed captions. It includes features such as searching for specific phrases within videos and retrieving timestamps for easy navigation. The project uses Docker for containerization and PostgreSQL for the database.

Features
Video Upload: Users can upload videos for processing.
Subtitle Extraction: Extracts subtitles from videos using FFmpeg or Python libraries.
Search Functionality: Search for phrases within a video and jump to the timestamp where it occurs.
List View: Displays uploaded videos and corresponding subtitles.
Containerized: The entire application, including Django, PostgreSQL, and other services, is containerized using Docker.
Prerequisites


cd your-repo-name
Step 2: Build and Run Docker Containers
Run the following command to build the Docker images and start the containers:
bash
Copy code
docker-compose up --build
This will:

Build the Django app and PostgreSQL containers.
Set up the PostgreSQL database and start the Django application.
Expose the Django app on port 8000.
Access the application by opening a web browser and going to:
http
Copy code
http://localhost:8000
Step 3: Apply Database Migrations
Run the migrations to set up the database tables:

bash
Copy code
docker-compose exec web python manage.py migrate
Step 4: Create a Superuser (Optional)
To access the Django admin panel, create a superuser account:

bash
Copy code
docker-compose exec web python manage.py createsuperuser
Follow the on-screen prompts to create the account.

Using the Application
Upload Videos: Upload video files from the main page.
View Videos: Uploaded videos will be listed with their subtitles.
Search Subtitles: Search within videos by entering a phrase to find timestamps and jump to the relevant sections.
Docker Containers
This project is composed of two main containers:

Web Container: The Django web application.
Database Container: PostgreSQL database that stores video metadata and subtitles.
Troubleshooting
Database Connection Issues: If you encounter database connection errors, ensure that the PostgreSQL container is running. You can check the logs with:
bash
Copy code
docker-compose logs db
Applying Migrations: Make sure to run the migrations if you see any issues related to missing database tables:
bash
Copy code
docker-compose exec web python manage.py migrate
FFmpeg Issues: If you get an error about FFmpeg not being installed, ensure that it's properly installed and accessible in your system's PATH.
Screenshots
You can find screenshots of the application in use within the screenshots/ directory.

Folder Structure
php
Copy code
.
├── video_app/                  # Django app for handling video upload and processing
├── media/                      # Folder where uploaded videos are stored
├── static/                     # Static files for the frontend (CSS, JS, etc.)
├── templates/                  # HTML templates for rendering views
├── Dockerfile                  # Dockerfile for building the Django app container
├── docker-compose.yml          # Docker Compose file for orchestrating containers
├── manage.py                   # Django's management script
├── README.md                   # This file
└── requirements.txt            # Python dependencies for the project
Requirements
Install required Python libraries:

bash
Copy code
pip install -r requirements.txt
License
This project is licensed under the MIT License.
