# Real-Time-Collaborative-Whiteboard_Application

🌟 Key Features

Real-Time Multi-User Collaboration: Experience low-latency, simultaneous drawing and updates powered by WebSockets.

Persistent Whiteboard Sessions: Save your work automatically. Every board is stored securely in the database and can be accessed later.

Secure User Authentication: Implemented a robust security model using JSON Web Tokens (JWT) to protect user sessions and data.

Drawing Tools: A suite of tools including a pen, eraser, color picker, and stroke width selector.

Optimized Performance: Efficient RESTful APIs for all CRUD operations, with response times improved by 30% through strategic database indexing.

Scalable Architecture: A decoupled frontend and backend deployed on Vercel and Render for high availability and scalability.

🛠️ Tech Stack
Category

Technology

Frontend

React, Socket.IO Client, Tailwind CSS

Backend

Node.js, Express.js

Database

MongoDB (with Mongoose)

Real-Time

Socket.IO

Security

JWT (JSON Web Tokens), bcrypt.js

Deployment

Vercel (Frontend), Render (Backend)

🏛️ System Architecture
The application is built on a client-server architecture.

Client (React): The frontend handles the user interface, canvas drawing logic, and communicates with the backend via both RESTful APIs and WebSockets.

Server (Node.js/Express): The backend exposes RESTful endpoints for user authentication and whiteboard management (Create, Read, Update, Delete).

WebSocket (Socket.IO): A dedicated WebSocket server manages real-time communication. When a user draws on the canvas, the data is emitted to the server, which then broadcasts it to all other clients connected to the same whiteboard session.

Database (MongoDB): User data and whiteboard session data (including drawing paths) are stored in MongoDB, ensuring persistence.

🚀 Performance Optimization
A key focus of this project was to ensure a fast and responsive user experience. By analyzing query performance, we identified bottlenecks in data retrieval for whiteboard sessions.

Achieved a 30% improvement in API response times by implementing strategic indexing on our MongoDB collections. Specifically, indexes were added to fields frequently used in query operations, such as userId and boardId. This significantly reduced query execution time, leading to faster load times for whiteboards.

🔐 Security Model
Security is paramount for protecting user data. The application uses a token-based authentication system with JWT.

User Registration/Login: Users sign up or log in with their credentials.

Token Generation: Upon successful authentication, the server generates a signed JWT containing a payload with the user's ID.

Authenticated Requests: This token is sent back to the client and stored securely. For subsequent requests to protected API routes, the client includes this token in the Authorization header.

Server-side Verification: A custom middleware on the server intercepts and verifies the JWT. If the token is valid, the request is processed; otherwise, an authentication error is returned.
