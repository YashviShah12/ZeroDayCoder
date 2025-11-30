🚀 MERN Stack Project – Setup & Documentation

A complete MERN stack project using MongoDB, Express, React, Node.js along with AI, Video, Judge0, Cloudinary, Redis, and full authentication flow.

🧩 Prerequisites

Before running the project, ensure the following are installed:

Node.js (LTS version)

MongoDB Atlas account

Redis (local or hosted)

Postman – API testing

VS Code

Git

📥 1. Clone the Repository
git clone <your-repo-url>
cd <project-folder>

🔧 Backend Setup
📁 2. Navigate to Backend
cd backend

📦 Install Backend Dependencies
npm install

⚙️ Create Environment Variables

Create a .env file:

touch .env


Paste the following:

PORT=
DB_CONNECT_STRING=
JWT_KEY=
REDIS_PASS=
JUDGE0_KEY=
GEMINI_KEY=
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=

🔐 Need a secure JWT key?

Generate a 32-character random string:
https://random.org/passwords/?num=1&len=32&format=plain&rnd=new

🚀 Start Backend
npm run dev


Ensure nodemon is installed globally:
npm install -g nodemon
Or run using plain node:
node index.js

🎨 Frontend Setup
📁 3. Navigate to Frontend
cd ../frontend

📦 Install Frontend Dependencies
npm install

🌐 Start Frontend
npm run dev

Default URLs:

Frontend (Vite): http://localhost:5173

Backend: http://localhost:3000


📌 API Endpoints — Full Description

Below is a complete breakdown of all API endpoints grouped by modules.

👤 1. User API
Base URL: /api/user
Method	Endpoint	Description	Access
POST	/login	Authenticates a user and returns JWT token.	Public
POST	/register	Registers a new user with basic credentials.	Public
POST	/adminregister	Creates an admin account with elevated permissions.	Admin
POST	/logout	Logs out the user by clearing authentication token/session.	Authenticated User
DELETE	/deleteprofile	Deletes the user's own profile permanently.	Authenticated User
GET	/checkauth	Verifies if the user’s token is valid and returns user details.	Authenticated User
📝 2. Problem API
Base URL: /api/problem
🔐 Admin Endpoints
Method	Endpoint	Description	Access
POST	/create	Create a new coding problem (title, description, difficulty, testcases).	Admin
GET	/	Retrieve all problems available in the platform.	Admin
PUT	/update/:id	Update an existing problem using its ID.	Admin
DELETE	/delete/:id	Delete a problem permanently using its ID.	Admin
👨‍🎓 User Endpoints
Method	Endpoint	Description	Access
POST	/submit/:id	Submit solution for a specific problem. Code is judged using Judge0 API.	Authenticated User
GET	/solved	Fetch all problems solved by the current user.	Authenticated User
GET	/	Get all problems visible to users.	Public / Authenticated
GET	/:id	Get a specific problem by its ID.	Public / Authenticated
🧪 3. Submission API
Base URL: /api/submission
Method	Endpoint	Description	Access
POST	/submit/:id	Submits the final answer for a problem. Stores result in DB.	Authenticated User
POST	/run/:id	Runs code without submitting using Judge0 (for testing).	Authenticated User
🤖 4. AI API
Base URL: /api/ai
Method	Endpoint	Description	Access
POST	/chat	AI-based chat functionality powered by GEMINI API. Helps in problem hints/explanations.	Authenticated User
🎥 5. Video API
Base URL: /api/video
Method	Endpoint	Description	Access
POST	/create	Create a video-related resource (e.g., session, object, metadata).	Authenticated User
POST	/save	Save video details to database (Cloudinary URL, metadata).	Authenticated User
DELETE	/delete/:id	Delete a video from the system using its ID.	Authenticated User




📁 Final Project Structure
project-folder/
│
├── backend/
│   ├── .env
│   ├── package.json
│   └── src/
│       └── ...
│
├── frontend/
│   ├── package.json
│   └── src/
│       ├── index.html
│       └── ...
│
└── README.md