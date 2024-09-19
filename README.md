Django Video Upload & Subtitle Extraction
----------------------------------------------------------------------------
This project is a Django-based web application that allows users to upload videos, extract subtitles, and display them as closed captions. 
It includes features such as searching for specific phrases within videos and retrieving timestamps for easy navigation.

Features
---------------------------------------------------
Video Upload: Users can upload videos for processing.
Subtitle Extraction: Extracts subtitles from videos using Python libraries.
Search Functionality: Search for phrases within a video and jump to the timestamp where it occurs.
List View: Displays uploaded videos and corresponding subtitles.

Prerequisites
----------------
To run the Django application, you'll need:
Python 3.x
PostgreSQL installed and running
FFmpeg (if you're using FFmpeg for subtitle extraction)
Git for cloning the repository

Setup and Installation
-------------------
https://github.com/ankit602/django_project.git
pip install -r requirements.txt
Make sure PostgreSQL is installed and running.

Create a PostgreSQL database and user for the project:
-----------------------------------------------------
psql -U postgres
CREATE DATABASE your_db_name;
CREATE USER your_db_user WITH PASSWORD 'your_password';
ALTER ROLE your_db_user SET client_encoding TO 'utf8';
ALTER ROLE your_db_user SET default_transaction_isolation TO 'read committed';
ALTER ROLE your_db_user SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE your_db_name TO your_db_user;

Update the DATABASES setting in your Django project's settings.py file to reflect your database credentials:
-------------------
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_db_name',
        'USER': 'your_db_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

Apply Migrations
----------
python manage.py migrate


Running the Application
------
python manage.py runserver
http://localhost:8000

Folder Structure
-----
.
├── video_app/                  # Django app for handling video upload and processing
├── media/                      # Folder where uploaded videos are stored
├── static/                     # Static files for the frontend (CSS, JS, etc.)
├── templates/                  # HTML templates for rendering views
├── manage.py                   # Django's management script
├── README.md                   # This file
└── requirements.txt            # Python dependencies for the project



