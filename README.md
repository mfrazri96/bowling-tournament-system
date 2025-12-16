# bowling-tournament-system
A web based bowling tournament system that assigns lanes automatically, tracks live scores, and ranks players across multiple games.

🎳 Strike Zone Selector
A lightweight, real time bowling lane assignment and scoring web app built with HTML, Tailwind CSS, and Supabase.
Designed for events to fairly assign lanes, prevent duplicates, and manage live scores across multiple games.
________________________________________
📌 Purpose
Strike Zone Selector helps event organizers:
•	Automatically assign participants to bowling lanes
•	Prevent the same person from registering twice
•	Balance participants evenly across lanes
•	Enter scores across multiple games and keep cumulative totals
•	Display a live leaderboard for award selection
No backend server setup required. Everything runs client side using Supabase.
________________________________________
🚀 Features
🎯 Lane Assignment
•	Users enter their name and are randomly assigned to an available lane
•	Each lane has a maximum capacity (default: 4 people per lane)
•	Returning users are automatically recognized and kept on the same lane
🏆 Live Scoring System
•	Admin view allows score entry per game
•	Scores are accumulated into a total score per player
•	Supports multiple games without overwriting previous scores
📊 Leaderboard
•	Automatically ranks players by total score
•	Displays the top 6 scorers across all lanes
•	Used to determine award winners
🔐 Admin View
•	View all lane groupings
•	Enter scores per player
•	Save scores directly to Supabase
•	View total participants and lane distribution
🎨 Modern UI
•	Fully responsive design
•	Built with Tailwind CSS
•	Clean animations and loading states
•	Mobile friendly
________________________________________
🛠 Tech Stack
Technology	Purpose
HTML	App structure
Tailwind CSS	Styling and responsive design
JavaScript (Vanilla)	App logic
Supabase	Database and API
Supabase JS SDK	Database interaction
________________________________________
🗄 Database Structure (Supabase)
Table: lane_assignments
Column	Type	Description
id	integer (PK)	Auto generated ID
name	text	Player name
lane	integer	Assigned lane number
score	integer	Total accumulated score
________________________________________
⚙️ Setup Instructions
1️⃣ Create Supabase Project
1.	Go to https://supabase.com
2.	Create a new project
3.	Create the lane_assignments table with the columns above
2️⃣ Configure API Keys
Replace the following values in the script:
const SUPABASE_URL = 'YOUR_SUPABASE_URL';
const SUPABASE_KEY = 'YOUR_PUBLIC_ANON_KEY';
⚠️ Use anon public key only, never the service role key.
________________________________________
▶️ How to Use
User Flow
1.	Open the page
2.	Enter name
3.	Click Pick My Lane
4.	Lane assignment is shown
5.	Returning users keep their lane
Admin Flow
1.	Click Scores and groups
2.	Enter score for each player under "This game"
3.	Click Save scores
4.	Leaderboard updates automatically
________________________________________
🧠 Scoring Logic
•	Each game score is added to the existing total
•	Empty score inputs are ignored
•	Scores are validated as numbers
•	Maximum score per game can be adjusted in input settings
________________________________________
🏅 Awards Logic
•	Awards are given to the Top 6 scorers overall
•	Lane does not matter
•	Ranking is based on cumulative score
________________________________________
🔄 Resetting Data
To reset for a new event:
•	Delete rows in lane_assignments table
•	Or create a new Supabase project
________________________________________
🔒 Security Notes
•	This app is intended for internal or event use
•	Supabase Row Level Security (RLS) is recommended if deployed publicly
•	Admin view is not password protected by default
________________________________________
📦 Deployment Options
•	GitHub Pages
•	Vercel
•	Netlify
•	Any static hosting service
No server required.
________________________________________
✨ Possible Enhancements
•	Admin password protection
•	Export scores to CSV
•	Multiple event support
•	Editable lane capacities
•	Game history per player
•	QR code registration
________________________________________
📄 License
This project is free to use and modify for internal or event purposes.
