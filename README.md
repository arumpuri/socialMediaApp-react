# socialMediaApp-react
## Overview
This documentation provides a comprehensive guide to a social media application. The features includes functionalities such as user authentication, posting, liking, following, and real-time messaging.

## Features
* Authentication & Authorization: User registration, login, and JWT-based token handling.
* User Profiles: Profiles with bio, profile picture, and follower/following lists.
* Posting & Feeds: Users can create, view, like, and comment on posts.
* Following System: Users can follow/unfollow others and view their own feed.
* Messaging: Real-time messaging using Socket.io.
* Notifications: Notifications for actions such as likes, comments, and follows.

## Technologies Used
* Frontend: React with Vite for fast development.
* Backend: Express.js as a server framework.
* Database: MongoDB for managing users, courses, and assignments.
* Authentication: JSON Web Tokens (JWT) for secure authentication and authorization.

## Installation Guide
**Clone the Repository**
```
git clone https://github.com/yourusername/mooc-web-classroom.git
cd mooc-web-classroom

```
**Backend Setup**
* Navigate to the /server folder:
```
cd server
```
* Install dependencies:
```
npm install

```
* Set up environment variables by creating a `.env` file with the following:
```
PORT=5000
MONGO_URI=<your-mongo-db-uri>
JWT_SECRET=<your-secret-key>

```
* Run the backend server:
```
npm start

```
**Frontend Setup**
* Navigate to the `/socialMediaApp-react` folder::
```
cd socialMediaApp-react

```
* Install dependencies:
```
npm install

```
* Set up environment variables by creating a `.env` file in `/socialMediaApp-react`:
```
VITE_API_URL=http://localhost:5000

```
* Run the backend server:
```
npm run dev

```
**Database Setup**
Ensure that MongoDB is installed and running. If you are using MongoDB Atlas, ensure your connection string is correct in the `.env` file.

## Prerequisites
Before setting up the project, ensure you have the following installed:

* Node.js (v16 or higher)
* MongoDB
* Git

## API Documentation

### Authentication
POST `/api/auth/register`
Registers a new user (student or instructor).
Body parameters:
* name: Full name of the user.
* email: Email address of the user.
* password: Password for the account.
POST `/api/auth/login`
Logs in a user and returns a JWT token.
Body parameters:
* email: Email address.
* password: Account password.
  
### User Management (userRoutes.js)
* View Profile
GET `GET /api/users/:userId`
Response:
Success: Returns profile data, including username, bio, follower/following counts.
* Follow/Unfollow User
POST `/api/users/:userId/follow`
Response:
Success: Updates follower/following lists.

### Posts (postRoutes.js)
* Create Post
POST `/api/posts`
Response:
Success: Returns post data with post ID, user info, timestamp.
* Like/Unlike Post
POST `/api/posts/:postId/like`
Response:
Success: Updates like count for the post.
* Get Feed
GET `/api/posts/feed`
Response:
Returns a paginated list of posts from followed users.

### Messaging (messageRoutes.js)

* Send Message
POST `/api/messages/:chatId`
* Retrieve Messages
GET `/api/messages/:chatId`

## Frontend (React)
### Project Structure
```
frontend/
├── src/
│   ├── components/
│   │   ├── Navbar.js
│   │   ├── Feed.js
│   │   └── PostItem.js
│   ├── pages/
│   │   ├── Home.js
│   │   └── Profile.js
│   ├── services/
│   │   └── api.js
│   ├── App.js
│   └── index.js

```
### Components
* Navbar: Includes links to the home, profile, and message sections.
* Feed: Displays posts from followed users.
* Profile: Shows user profile, posts, followers, and following.
* PostItem: Component for individual posts.
* Chat: Real-time chat interface using Socket.io.
* Notifications: Displays recent notifications.

