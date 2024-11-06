# URL Shortener Application

This is a URL shortener application built using Node.js, Express.js, MongoDB, EJS, and JWT for user authentication. The application allows users to shorten URLs, track their usage, and view their URL history.

## Features

- **URL Shortening**: Users can enter any URL and get a shortened URL.
- **User Authentication**: Users can sign up and log in to generate and view their shortened URLs.
- **URL Analytics**: Users can view the total number of clicks for each shortened URL.
- **User URL History**: Users can see all the URLs they've shortened along with their visit history.

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **Frontend**: EJS (Embedded JavaScript templating)

### Libraries:

- `shortid` for generating unique short URLs
- `mongoose` for MongoDB object modeling
- `cookie-parser` for managing cookies in the browser
- `nanoid`, `uuid` for unique identifier generation

## Endpoints

### Public Routes

- `GET /url/:shortId`: Redirects to the original URL associated with the shortened ID.

### Authenticated Routes

- `GET /`: Home page showing a form to shorten URLs and display URL history.
- `POST /url`: Submit a URL to generate a shortened version.
- `GET /user/login`: Login page.
- `POST /user/login`: Submit login credentials.
- `GET /user/signup`: Signup page.
- `POST /user/signup`: Submit signup form.

### Analytics Route

- `GET /url/analytics/:shortId`: View analytics for a shortened URL.

## How It Works

### Login and Signup:

1. Users can sign up using their email and password.
2. Once signed up, they can log in to access their URL history.

### URL Shortening:

1. After logging in, users can provide a URL they want to shorten.
2. A unique short ID is generated for each URL, and it’s stored in the MongoDB database.

### Redirecting:

1. When a user visits a shortened URL (e.g., `http://localhost:8001/url/:shortId`), they are redirected to the original URL.

### Analytics:

1. Users can view analytics for each shortened URL, including the total number of clicks.
