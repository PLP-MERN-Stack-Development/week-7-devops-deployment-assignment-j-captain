# **Socket.IO Chat Application**  
### **A Real-Time Chat App Built with MERN Stack & Deployed on Render**  

🚀 **Live Demo:** [https://plp-mern-wk-5-web-sockets-frontend-4.onrender.com/](#) | [https://plp-mern-wk-5-web-sockets.onrender.com]

## **📌 Table of Contents**  
1. [Features](#-features)  
2. [Tech Stack](#-tech-stack)  
3. [Project Structure](#-project-structure)  
4. [Setup & Installation](#-setup--installation)  
5. [Running Locally](#-running-locally)  
6. [Deployment on Render](#-deployment-on-render)  
7. [Environment Variables](#-environment-variables)  
8. [Troubleshooting](#-troubleshooting)  
9. [Future Improvements](#-future-improvements)  
10. [License](#-license)  

---

## **✨ Features**  
✔ **Real-time messaging** using **Socket.IO**  
✔ **User authentication** (optional, if implemented)  
✔ **Message history** stored in **MongoDB**  
✔ **Online/Offline status** detection  
✔ **Responsive UI** built with **React.js**  
✔ **Deployed on Render** (frontend + backend)  

---

## **🛠 Tech Stack**  
### **Frontend**  
- **React.js** (UI components & state management)  
- **Socket.IO Client** (real-time communication)  
- **Axios** (HTTP requests, if used)  
- **CSS/SCSS** (styling)  

### **Backend**  
- **Node.js** (runtime)  
- **Express.js** (server framework)  
- **Socket.IO** (WebSocket handling)  
- **MongoDB** (database)  
- **Mongoose** (ODM for MongoDB)  

### **Deployment**  
- **Render** (hosting for frontend & backend)  
- **MongoDB Atlas** (cloud database)  

---

## **📂 Project Structure**  
## Project Structure

### Backend
```
server/
├── config/
│   └── db.js            # Database connection
├── controllers/
├── models/
│   ├── User.js          # User model
│   ├── Message.js       # Message model
│   └── Room.js          # Chat room model
├── socket/
│   ├── auth.js          # Socket authentication
│   └── chat.js          # Socket event handlers
├── utils/
├── server.js            # Main server file
└── package.json
```

### Frontend

client/
├── public/
├── src/
│   ├── components/
│   │   ├── MessageInput.jsx
│   │   ├── MessageList.jsx
│   │   └── OnlineUsers.jsx
│   ├── context/
│   │   └── SocketContext.jsx
│   ├── hooks/
│   ├── pages/
│   │   └── ChatPage.jsx
│   ├── socket/
│   │   └── socket.js
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── .eslintrc.cjs
├── index.html
├── package.json
└── tailwind.config.js

 ## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login an existing user

### File Upload
- `POST /api/upload` - Upload files (images/documents)

## Socket.io Events

### Server Emits
- `new_message` - When a new message is received
- `previous_messages` - When a user joins a room
- `typing` - When a user is typing
- `user_list` - List of online users
- `private_room_created` - When a private chat is created
- `message_read` - When a message is read by a user

### Client Emits
- `send_message` - Send a new message
- `join_room` - Join a chat room
- `start_private_chat` - Start a private chat
- `mark_as_read` - Mark a message as read
- `typing` - Notify when user is typing

 
### **Install Dependencies**  
**Backend:**  
 
cd server
npm install
 

**Frontend:**  
```bash
cd ../client
npm install
 

---

## **🏃 Running Locally**  
### **1. Start the Backend**  
 
cd server
npm start  # or `nodemon server.js` for development
 
- Runs on `http://localhost:5000`  

### **2. Start the Frontend**  
 
cd ../client
npm start
 
- Runs on `http://localhost:3000`  

### **3. Configure MongoDB**  
- Set up a **MongoDB Atlas** cluster and update `server/.env` with:  
  
  MONGODB_URI=your-mongodb-atlas-connection-string
  

 
## **☁ Deployment on Render**  
### **1. Backend Setup**  
- **Create a new Web Service** on Render.  
- Connect to your GitHub repo and select the `server/` directory.  
- Set environment variables in Render dashboard:  
  ```
  MONGODB_URI=your-mongodb-uri
  PORT=5000
  NODE_ENV=production
 
- **Enable WebSockets** in Render settings.  

### **2. Frontend Setup**  
- **Create a Static Site** (or Web Service if using SSR).  
- Set build command:  
 
  cd client && npm install && npm run build
  
- Update the Socket.IO client connection in React:  
 
  const socket = io("https://your-backend-url.onrender.com");
 

### **3. CORS & Proxy Handling**  
Ensure your Express backend allows the frontend URL:  
```js
app.use(cors({ origin: "https://your-frontend.onrender.com" }));
 

 

## **🔑 Environment Variables**  
**`server/.env`**  
 env
MONGODB_URI=your-mongodb-uri
PORT=5000
JWT_SECRET=your-secret-key (if using auth)
 

 

## **⚠ Troubleshooting**  
🔹 **Socket.IO Connection Failing?**  
- Check **CORS** settings in the backend.  
- Ensure **WebSockets** are enabled in Render.  

🔹 **MongoDB Not Connecting?**  
- Whitelist **0.0.0.0/0** in MongoDB Atlas (temporarily).  

🔹 **Frontend Not Updating?**  
- Clear cache or check `useEffect` dependencies in React.  

---

## **🚀 Future Improvements**  
- [ ] **User Authentication** (JWT/OAuth)  
- [ ] **Group Chats & Rooms**  
- [ ] **Message Read Receipts**  
- [ ] **File Uploads** (Images, PDFs)  
- [ ] **Notifications** (Push/Email)  

**screenshots**

![image1](<Screenshot (106).png>)
 ![image2](<Screenshot (100).png>) 
 ![image3](<Screenshot (101).png>)
  ![image4](<Screenshot (102).png>) 
  ![image5](<Screenshot (103).png>) 
  ![image6](<Screenshot (104).png>)
   ![image7](<Screenshot (105).png>)



## **📜 License**  
MIT © [j-captain](https://github.com/your-j-captain)  

 

**🎉 Happy Coding!** Let me know if you need any enhancements. 🚀