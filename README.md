# StudyBud

StudyBud is a Django-based study-room and discussion platform designed to help students connect, create study rooms, discuss topics, and collaborate with other learners.

The application provides user authentication, study-room management, topic-based searching, room discussions, user profiles, recent activity, and REST API endpoints.

## Features

* User registration and login
* User logout
* User profile management
* Browse study rooms
* Search study rooms
* Browse study topics
* Create study rooms
* Edit study rooms
* Delete study rooms
* Join rooms through participation
* Room-based messaging and discussions
* View room participants
* User activity history
* Django admin interface
* REST API for study rooms
* Responsive web interface

## Tech Stack

### Backend

* Python
* Django 6.1.1
* Django REST Framework 3.18.1
* SQLite

### Frontend

* HTML5
* CSS3
* JavaScript
* Django Templates

### Development Tools

* Git
* GitHub
* Python Virtual Environment

## Project Structure

```text
StudyBud/
│
├── base/
│   ├── api/
│   │   ├── serializers.py
│   │   ├── urls.py
│   │   └── views.py
│   │
│   ├── migrations/
│   ├── templates/
│   │   └── base/
│   │
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
│
├── static/
│   ├── images/
│   ├── js/
│   └── styles/
│
├── templates/
│   ├── main.html
│   └── navbar.html
│
├── studybud/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── manage.py
├── requirements.txt
├── .gitignore
└── README.md
```

## Core Functionality

### User Authentication

StudyBud uses Django's built-in authentication system.

Users can:

* Register an account
* Log in
* Log out
* Update their profile
* View other user profiles

### Study Rooms

Users can create study rooms based on different topics.

Each room can contain:

* Room name
* Description
* Topic
* Host
* Participants
* Messages
* Creation/update timestamps

Users can create, update, and delete rooms depending on their permissions.

### Search

The application provides room searching through the home page.

Users can search by:

* Room name
* Room description
* Topic

Example:

```text
/?q=python
```

or:

```text
/?q=django
```

### Messaging

Users can communicate with other participants inside study rooms.

Messages are associated with:

* User
* Room
* Message content
* Timestamp

### User Profiles

Each user has a profile/activity page that can display:

* User information
* Rooms created
* Messages posted
* Recent activity

## REST API

The project includes Django REST Framework endpoints.

### API Root

```text
/api/
```

### Get All Rooms

```text
GET /api/rooms/
```

Example:

```text
http://127.0.0.1:8000/api/rooms/
```

### Get a Specific Room

```text
GET /api/rooms/<id>/
```

Example:

```text
http://127.0.0.1:8000/api/rooms/1/
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Move into the project:

```bash
cd StudyBud
```

### 2. Create a Virtual Environment

#### Windows

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

#### macOS/Linux

```bash
python3 -m venv venv
```

Activate it:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run Database Migrations

```bash
python manage.py migrate
```

### 5. Create an Administrator Account

```bash
python manage.py createsuperuser
```

Follow the instructions in the terminal.

### 6. Start the Development Server

```bash
python manage.py runserver
```

Open the application in your browser:

```text
http://127.0.0.1:8000/
```

## Django Admin

The Django administration panel is available at:

```text
http://127.0.0.1:8000/admin/
```

Use the superuser account created with:

```bash
python manage.py createsuperuser
```

## Environment Variables

For security, sensitive configuration should not be committed directly to GitHub.

In particular, the Django `SECRET_KEY` should be stored as an environment variable.

Example:

```text
DJANGO_SECRET_KEY=your-secret-key
```

Never commit:

```text
.env
```

or other files containing passwords, API keys, or production secrets.

## GitHub Setup

Before pushing the project to GitHub, make sure the following files and folders are ignored:

```text
venv/
__pycache__/
*.pyc
db.sqlite3
.env
```

The project should contain:

```text
manage.py
requirements.txt
README.md
.gitignore
base/
studybud/
static/
templates/
```

## Running the Project Locally

After cloning the repository:

```bash
python -m venv venv
```

Activate the environment.

Then install dependencies:

```bash
pip install -r requirements.txt
```

Run migrations:

```bash
python manage.py migrate
```

Start Django:

```bash
python manage.py runserver
```

Then visit:

```text
http://127.0.0.1:8000/
```

## Future Improvements

Possible future improvements include:

* Real-time messaging using WebSockets
* Django Channels integration
* PostgreSQL production database
* Automated unit and integration tests
* API authentication
* API documentation
* Pagination for rooms and messages
* Improved authorization and permissions
* User profile image uploads
* Docker support
* Production deployment configuration
* Improved accessibility
* Enhanced responsive UI/UX

## Security Notes

This project is configured primarily for development.

Before deploying to production:

* Set `DEBUG=False`
* Use a secure `SECRET_KEY`
* Configure `ALLOWED_HOSTS`
* Use a production database such as PostgreSQL
* Configure HTTPS
* Configure secure cookies
* Configure static and media files properly
* Store secrets in environment variables
* Review authentication and authorization permissions

## License

This project currently does not specify an open-source license.

If you plan to distribute the project publicly, consider adding an appropriate `LICENSE` file.
