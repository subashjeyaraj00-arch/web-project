# College Portal Chatbot System

A complete MERN stack (MongoDB, Express.js, Node.js, Vanilla HTML/CSS/JS) chatbot system for a college portal. It features a complete authentication system with Role-Based Access Control (Admin and Student).

## Features

**Admin Dashboard:**
- Role-based authentication (Admin login).
- Add new chatbot responses linked to keywords.
- Upload optional PDF/Doc files and Image previews for each keyword response.
- Edit and delete existing keyword responses.

**Student Dashboard:**
- Real-time interactive chatbot UI (vertical scrollable).
- Smart keyword matching (exact & partial matching).
- Auto-scroll to latest messages.
- Displays standard text, image previews, and file download buttons.
- Greeting detection ("hi", "hello") and fallback messages.

**Design:**
- Modern, clean Dark Theme UI using CSS Variables.
- Smooth CSS animations, glassmorphism-inspired effects.
- Fully responsive styling.

## Folder Structure

```
college-chatbot/
│
├── .env                        # Environment variables
├── package.json                # Project dependencies
├── server.js                   # Main Express application entry point
│
├── config/
│   └── db.js                   # MongoDB connection logic
│
├── models/
│   ├── User.js                 # Mongoose schema for Admins & Students
│   └── ChatbotResponse.js      # Mongoose schema for keyword, response, and files
│
├── routes/
│   ├── auth.js                 # Register & Login APIs (JWT generation)
│   ├── admin.js                # Keyword CRUD operations with Multer upload
│   └── chat.js                 # Chatbot query logic & keyword matching
│
├── middleware/
│   └── authMiddleware.js       # JWT & Admin verification middleware
│
├── uploads/                    # Automatically generated directory for uploaded files
│
└── public/                     # Static Frontend Files
    ├── index.html              # Login & Registration Page
    ├── admin.html              # Admin Dashboard
    ├── student.html            # Student Chat Interface
    ├── css/
    │   └── style.css           # Global Dark Theme stylesheet
    └── js/
        ├── auth.js             # Login/Register fetch API logic
        ├── admin.js            # Admin panel fetch API logic & UI toggles
        └── student.js          # Chatbot UI logic, sending/receiving messages
```

## Setup & Running Instructions

1. **Prerequisites:**
   - [Node.js](https://nodejs.org/) installed on your machine.
   - [MongoDB](https://www.mongodb.com/try/download/community) installed and running locally on default port 27017, OR a MongoDB Atlas URI string.

2. **Installation:**
   Open a terminal in the project directory (`college-chatbot`) and run:
   ```bash
   npm install
   ```

3. **Configure Environment:**
   Ensure the `.env` file exists with the following properties:
   ```env
   PORT=5000
   MONGODB_URI=mongodb://127.0.0.1:27017/college-chatbot
   JWT_SECRET=supersecretcollegechatbotkey123
   ```
   *(Change the MongoDB URI if using a cloud database)*

4. **Start the Server:**
   ```bash
   npm start
   ```
   *Terminal output should say:* "Server running on port 5000" and "MongoDB Connected".

5. **Usage Flow:**
   - Go to `http://localhost:5000` in your browser.
   - Toggle to "Register" and create an account. Select **Admin** to manage data, or **Student** to chat.
   - Upon logging in as Admin: Add keywords like `syllabus` and attach a PDF or Image.
   - Log out, login as a Student, and type `What is the syllabus?`
   - The bot will detect the substring `syllabus` and respond with text and files.

## Tech Stack
- **Frontend**: HTML5, Vanilla JavaScript (ES6+), Vanilla CSS3
- **Backend**: Node.js, Express.js
- **Database**: MongoDB (Mongoose ODM)
- **Security & Utilities**: bcryptjs (hashing), jsonwebtoken (auth), multer (file uploads)

---
*Created by AI Full Stack Developer*
