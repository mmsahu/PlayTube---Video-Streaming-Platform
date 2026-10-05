 🎬 PlayTube — Video Streaming Platform
 
PlayTube is a full-stack video streaming platform built with React, Node.js, Express.js and MongoDB. It provides a YouTube-inspired experience with video streaming, Shorts, channels, subscriptions, playlists, comments, creator tools, recommendations and AI-powered search.
This README is written specifically for the project structure and code contained in this repository.
🚀 Project Overview
PlayTube allows users to:
- Create an account and sign in
- Sign in with Google using Firebase Authentication
- Create and manage a channel
- Upload videos and Shorts
- Watch videos with custom playback controls
- Like / dislike content
- Comment and reply
- Subscribe to channels
- Save videos and playlists
- View liked content and watch history
- Create and manage playlists
- Explore recommended content
- Search videos, Shorts, channels and playlists
- Use Gemini AI for search keyword correction and category filtering
- Use a creator dashboard (PTStudio) for content, analytics and revenue views
- Reset passwords using OTP email
✨ Main Features
👤 Authentication
- User registration
- User sign in
- JWT authentication
- Cookie-based authentication
- Protected routes
- Forgot password
- OTP-based password reset
- Google authentication through Firebase
🎥 Video Platform
- Upload videos
- Video playback
- Video view tracking
- Like / dislike
- Download video
- Save video
- Comments
- Comment replies
- Video recommendations
📱 Shorts
- Upload Shorts
- Shorts feed
- Auto play / pause
- View tracking
- Like / dislike
- Save Shorts
- Comments and replies
📺 Channel System
- Create channel
- Update channel
- Channel avatar
- Channel banner
- Channel description
- Channel category
- Subscribe / unsubscribe
- Channel content management
📚 Playlists
- Create playlists
- Add videos to playlists
- Save playlists
- Manage playlists
- View saved playlists
🔎 AI-Powered Search
PlayTube integrates Google Gemini (gemini-2.5-flash) for search assistance.
The AI search can:
- Correct spelling/typing mistakes
- Extract meaningful search keywords
- Search across videos
- Search Shorts
- Search channels
- Search playlists
The project also contains AI-based category filtering for categories such as:
- Music
- Gaming
- Movies
- TV Shows
- News
- Trending
- Entertainment
- Education
- Science & Tech
- Travel
- Fashion
- Cooking
- Sports
- Pets
- Art
- Comedy
- Vlogs
📊 Creator Studio — PTStudio
The project includes a creator dashboard called PTStudio with:
- Dashboard
- Content management
- Video management
- Shorts management
- Playlist management
- Analytics page
- Revenue page
🛠️ Tech Stack
Frontend
Technology	Usage
React 19	UI development
Vite	Development/build tool
React Router DOM	Client-side routing
Redux Toolkit	State management
Axios	API requests
Tailwind CSS	Styling
React Icons	Icons
React Spinners	Loading indicators
Recharts	Analytics charts
Socket.IO Client	Real-time client communication
Firebase	Google Authentication


Backend
Technology	Usage
Node.js	Runtime
Express.js	REST API
MongoDB	Database
Mongoose	MongoDB ODM
JWT	Authentication
bcryptjs	Password hashing
Multer	File upload handling
Cloudinary	Media storage
Nodemailer	OTP/password-reset email
Socket.IO	Real-time communication
Google Gemini	AI search
fluent-ffmpeg	Media processing support
Validator	Input validation


📁 Project Structure
PlayTube/
│
├── backend/
│   ├── config/
│   │   ├── cloudinary.js
│   │   ├── connectDb.js
│   │   ├── sendMail.js
│   │   └── token.js
│   │
│   ├── controller/
│   │   ├── aiController.js
│   │   ├── authController.js
│   │   ├── playlistController.js
│   │   ├── postController.js
│   │   ├── shortController.js
│   │   ├── userController.js
│   │   └── videoController.js
│   │
│   ├── middleware/
│   │   ├── isAuth.js
│   │   └── multer.js
│   │
│   ├── model/
│   │   ├── channelModel.js
│   │   ├── playlistModel.js
│   │   ├── postModel.js
│   │   ├── shortModel.js
│   │   ├── userModel.js
│   │   └── videoModel.js
│   │
│   ├── route/
│   │   ├── authRoute.js
│   │   ├── contentRoute.js
│   │   └── userRoute.js
│   │
│   ├── index.js
│   ├── package.json
│   └── package-lock.json
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── component/
│   │   ├── customHooks/
│   │   ├── pages/
│   │   ├── redux/
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── utils/
│   │   └── firebase.js
│   │
│   ├── package.json
│   ├── package-lock.json
│   └── vite.config.js
│
└── README.md
📦 Installation
Prerequisites
Install:
- Node.js
- npm
- Git
- MongoDB / MongoDB Atlas
- Cloudinary account
- Google Gemini API key
- Firebase project
- Gmail account with App Password for OTP email
Recommended Node.js version: 18+
⚙️ Backend Setup
Open terminal:
cd backend
npm install
The backend currently provides this development script:
npm run dev
Start backend:
npm run dev
The backend uses:
http://localhost:8000
when PORT=8000 is configured.
The current backend/package.json contains the dev script only. For Render production deployment, add a start script such as "start": "node index.js".

🌐 Frontend Setup
Open another terminal:
cd frontend
npm install
Start the frontend:
npm run dev
Vite normally starts the application at:
http://localhost:5173
Create a production build:
npm run build
Preview the production build:
npm run preview
🔐 Environment Variables
Backend .env
Create:
backend/.env
The backend code uses the following environment variables:
PORT=8000

MONGODB_URL=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

GEMINI_API_KEY=your_gemini_api_key

USER_EMAIL=your_gmail_address
USER_PASSWORD=your_gmail_app_password
What each variable is used for
PORT
Backend server port.
MONGODB_URL
MongoDB/MongoDB Atlas connection string.
JWT_SECRET
Used for authentication token generation.
CLOUDINARY_NAME
Cloudinary cloud name.
CLOUDINARY_API_KEY
Cloudinary API key.
CLOUDINARY_API_SECRET
Cloudinary API secret.
GEMINI_API_KEY
Google Gemini API key used by the AI search controller.
USER_EMAIL
Gmail account used by Nodemailer.
USER_PASSWORD
Gmail App Password used for sending password-reset OTP emails.
🔥 Firebase Configuration
The frontend contains:
frontend/utils/firebase.js
It uses:
VITE_FIREBASE_APIKEY=your_firebase_web_api_key
The project currently uses Firebase for Google Authentication.
The Firebase configuration in the source contains the project identifiers for the configured Firebase project, while the API key is read from the Vite environment variable.
Create:
frontend/.env
and add:
VITE_FIREBASE_APIKEY=your_firebase_api_key
☁️ Cloudinary
PlayTube uses Cloudinary for uploaded media.
The backend config is:
backend/config/cloudinary.js
It reads:
CLOUDINARY_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
Uploaded files are sent to Cloudinary and the application stores/uses the returned secure media URL.
🤖 Google Gemini AI
AI functionality is implemented in:
backend/controller/aiController.js
The project uses:
gemini-2.5-flash
for:
AI Search
The AI:
1. Receives the user's search text.
2. Corrects spelling/typing mistakes.
3. Extracts meaningful keywords.
4. Searches videos, Shorts, channels and playlists.
AI Category Filter
The AI classifies search queries into the project's supported content categories.
Add:
GEMINI_API_KEY=your_gemini_api_key
to the backend .env.
📧 Password Reset / OTP
The project uses Nodemailer in:
backend/config/sendMail.js
Gmail configuration:
USER_EMAIL=your_email@gmail.com
USER_PASSWORD=your_gmail_app_password
The application sends a password-reset OTP which expires after the configured period in the authentication flow.
🔗 API Structure
The backend registers these main API groups:
/api/auth
/api/user
/api/content
Authentication
/api/auth/...
Handles:
- Sign up
- Sign in
- Password reset
- Authentication-related operations
User / Channel
/api/user/...
Handles:
- User data
- Channel creation
- Channel updates
- Subscriptions
- User-related operations
Content
/api/content/...
Handles:
- Videos
- Shorts
- Playlists
- Posts
- Likes/dislikes
- Comments
- Views
- Search/recommendation related content
🧭 Frontend Routes
Important routes included in the current React application:
/
 /shorts
 /signin
 /signup
 /forgetpassword
 /createchannel
 /create-video
 /create-post
 /create-short
 /create-playlist
 /watch-video/:videoId
 /watch-short/:shortId
 /channelpage/:channelId
 /subscribepage
 /saveplaylist
 /savevideos
 /likedvideos
 /history
 /ptstudio/dashboard
 /ptstudio/content
 /ptstudio/analytics
 /ptstudio/revenue
Creator management routes include:
/ptstudio/managevideo/:videoId
/ptstudio/manageshort/:shortId
/ptstudio/manageplaylist/:playlistId
🔒 Authentication & Protected Routes
The frontend uses a ProtectedRoute component.
Features requiring authentication redirect unauthenticated users back to the home page.
Protected functionality includes:
- Shorts
- Channel pages
- Creating videos
- Creating Shorts
- Creating posts
- Creating playlists
- Watching individual videos
- Watching Shorts
- Subscriptions
- Saved content
- Liked content
- History
- PTStudio creator tools
🔌 Socket.IO
The project includes:
socket.io
socket.io-client
for real-time communication capabilities.
Backend dependency:
socket.io
Frontend dependency:
socket.io-client
🏃 Run the Complete Project
You need two terminals.
Terminal 1 — Backend
cd backend
npm install
npm run dev
Terminal 2 — Frontend
cd frontend
npm install
npm run dev
Then open:
http://localhost:5173
🌍 Render Deployment
The repository can be deployed as two Render services.
Backend — Web Service
Create:
Render → New → Web Service
Use:
Root Directory:
backend
Build:
npm install
For production, add this script to backend/package.json:
"scripts": {
  "dev": "nodemon index.js",
  "start": "node index.js"
}
Then use Render Start Command:
npm start
Important
The current backend code contains:
const port = process.env.PORT
For Render, it is safer to use:
const port = process.env.PORT || 8000
The current CORS configuration also contains:
origin: "http://localhost:5173"
For production, replace it with your deployed frontend origin, for example:
origin: "https://your-frontend.onrender.com"
Frontend — Static Site
Create:
Render → New → Static Site
Use:
Root Directory:
frontend
Build command:
npm install && npm run build
Publish directory:
dist
The frontend currently defines the backend URL in:
frontend/src/App.jsx
Current value:
export const serverUrl = "http://localhost:8000"
For deployment, replace it with your Render backend URL, for example:
export const serverUrl = "https://your-backend.onrender.com"
A better production approach is to use:
export const serverUrl =
  import.meta.env.VITE_SERVER_URL || "http://localhost:8000";
and set:
VITE_SERVER_URL=https://your-backend.onrender.com
🧪 Production Checklist
Before deploying:
- [ ] Create MongoDB Atlas database
- [ ] Configure MongoDB connection string
- [ ] Create Cloudinary account
- [ ] Configure Cloudinary credentials
- [ ] Create Gemini API key
- [ ] Configure Firebase Google Authentication
- [ ] Configure Gmail App Password
- [ ] Create backend .env
- [ ] Create frontend .env
- [ ] Add .env to .gitignore
- [ ] Never commit API keys
- [ ] Add backend production start script
- [ ] Configure production CORS
- [ ] Configure frontend production API URL
- [ ] Build frontend with npm run build
- [ ] Deploy backend
- [ ] Deploy frontend
- [ ] Test login/signup
- [ ] Test Google login
- [ ] Test channel creation
- [ ] Test video upload
- [ ] Test Shorts
- [ ] Test comments
- [ ] Test subscriptions
- [ ] Test playlists
- [ ] Test AI search
- [ ] Test password reset
⚠️ Important Security Notes
Never upload these to GitHub:
.env
MongoDB credentials
JWT secret
Cloudinary API secret
Gemini API key
Gmail App Password
Recommended .gitignore:
node_modules/
.env
.env.*
dist/
build/
If a secret has already been pushed to GitHub, rotate/revoke it and create a new credential.
🧑‍💻 Author
Mohan Sahu
B.Tech Computer Science Graduate
MERN Stack Developer | Full-Stack Developer
📌 Project Highlights
PlayTube demonstrates practical full-stack development using:
- React
- Node.js
- Express.js
- MongoDB
- Mongoose
- Redux Toolkit
- Tailwind CSS
- JWT Authentication
- Firebase Authentication
- Cloudinary
- Google Gemini AI
- Nodemailer
- Socket.IO
- REST APIs
The project is suitable as a MERN Stack / Full-Stack Developer portfolio project.
⭐ GitHub
If you find this project useful, consider giving the repository a ⭐.
📄 License
This project is currently intended for educational and portfolio purposes. Add an appropriate open-source license before distributing it commercially.
