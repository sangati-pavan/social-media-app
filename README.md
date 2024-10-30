# FullStack Social Media App

Overview :

This social media platform allows users to interact by creating posts, commenting, liking, following/unfollowing users, and engaging in real-time chat. Built with the MERN stack, it leverages advanced state management, real-time capabilities, and asynchronous programming for a complete user experience.

1. Features :   

    User Authentication: Sign-up and login with JWT.
    Posting & Interaction: Users can create posts, comment, and like.
    Follow System: Users can follow and unfollow each other.
    Real-time Chat: Real-time messaging with WebSockets.
    Notifications: Email and in-app notifications for likes, comments, and follows.
    Profile & Feed: Personalized profile pages and a global post feed.

2. Tech Stack :

    2.1 Frontend :

        React.js
        Redux: State management for posts, likes, comments, etc.
        Context API: Manages authentication and session.
        Socket.io: Real-time messaging.

    2.2 Backend :

        Node.js & Express.js
        MongoDB: For user, post, and message storage.
        Socket.io: WebSocket-based real-time communication.
        JWT: User authentication.
        NodeMailer / SendGrid: Email notifications.

3. Project Structure :

    client/: Contains all frontend code.
    src/components: React components.
    src/redux: Redux store and actions.
    src/context: Context API for user sessions.
    server/: Contains backend code.
    routes/: All API endpoints.
    models/: MongoDB schemas.
    controllers/: Handles business logic.
    middlewares/: Authentication and validation.

4. Installation :

    4.1 Clone the repository

        git clone https://github.com/sangati-pavan/social-media-app.git
        cd social-media-app
        
    4.2 Install dependencies


        # Install server dependencies
        cd server
        npm install

        # Install client dependencies
        cd ../client
        npm install

    4.3 Environment Variables

        In both server and client directories, create .env files for environment variables.

        server/.env
       
        MONGO_URI=<your-mongodb-connection-string>
        JWT_SECRET=<your-jwt-secret>
        NODEMAILER_USER=<your-email>
        NODEMAILER_PASS=<your-email-password>
        client/.env
        arduino
    
        REACT_APP_API_URL=http://localhost:5000

    4.4 Start the Application

        # Start the server
        cd server
        npm start

        # Start the client
        cd ../client
        npm start

5. Key Features and Implementation :

    1. User Authentication (JWT, Context API)
    Signup & Login: Passwords hashed using bcrypt and managed with JWT tokens.
    Protected Routes: Only authenticated users can access certain features.
    2. Post Creation, Commenting, and Likes (Redux, MongoDB)
    Post Creation: Users create posts with text, images, or videos.
    Comments & Likes: Handled via Promises for smooth asynchronous updates.
    3. Follow/Unfollow System
    Follow & Unfollow: Stored in MongoDB with email notifications for user actions.
    4. Real-time Chat (Socket.io, Redux)
    Real-time Messaging: Users can chat without refreshing the page.
    Chat History: Stored in MongoDB, accessible when users reopen chats.
    5. Notifications
    Email Notifications: For likes, comments, and follows using NodeMailer or SendGrid.
    In-app Notifications: Real-time updates for user interactions.

6. API Documentation :

    6.1 Auth Routes

    POST /api/auth/signup - Register a new user.
    POST /api/auth/login - Login an existing user.

    6.2 Post Routes

    POST /api/posts - Create a post.
    GET /api/posts - Fetch all posts.
    PUT /api/posts/:id/like - Like a post.

    6.3 Comment Routes

    POST /api/posts/:id/comments - Add a comment to a post.
    GET /api/posts/:id/comments - Get comments for a post.

    6.4 Follow Routes

    POST /api/users/:id/follow - Follow a user.
    POST /api/users/:id/unfollow - Unfollow a user.

7. Database Structure (MongoDB)

    Users Collection
    Fields: username, email, password, followers, following, posts
    Posts Collection
    Fields: postContent, userId, likes, comments, createdAt
    Comments Collection
    Fields: commentText, userId, postId, createdAt
    Chat Collection
    Fields: userId, message, createdAt
    
8. Contributing :

    Feel free to submit pull requests or open issues for new ideas or bugs.
