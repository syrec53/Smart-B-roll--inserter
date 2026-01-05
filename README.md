# Smart-B-roll--inserter
Smart B-Roll Inserter: Automatically generates a timeline plan for inserting B-roll clips into talking-head videos using semantic matching and optional final video rendering.

# Smart B-Roll Inserter for UGC Videos

## Overview
This project automatically plans how B-roll clips should be inserted into a talking-head (A-roll) video.  
It uses OpenAI embeddings to understand the content of both A-roll and B-roll clips and generates a **timeline plan** describing where each B-roll should appear. Optionally, it can render the final video using ffmpeg while keeping the A-roll audio intact.

---

## Features
- Sentence-level transcription of A-roll with timestamps
- Semantic understanding of B-roll clips
- Smart matching to decide where each B-roll fits best
- Timeline plan output in JSON format
- Optional final video rendering with ffmpeg
- Simple React frontend to upload videos and view the timeline

---

## Technologies Used
- **Python**: Backend logic, transcription, semantic matching
- **OpenAI API**: Embeddings for semantic matching
- **React + Vite**: Frontend interface
- **ffmpeg**: Optional video rendering

---

## Installation & Running

### Backend
```bash
cd backend
python -m venv venv
# activate virtual environment
pip install -r requirements.txt
export OPENAI_API_KEY="your_api_key_here"  # mac/linux
# start backend
uvicorn api:app --reload
Frontend
bash
Copy code
cd frontend
npm install
npm run dev
Open browser at http://localhost:5173

Usage
Upload A-roll and B-roll videos in the frontend.

Click Generate Timeline.

JSON plan is displayed and saved to output/timeline_plan.json.

Optionally, run python render.py to generate final_video.mp4.

Folder Structure
graphql
Copy code
smart-broll-inserter/
├── backend/       # Backend Python code
├── frontend/      # React frontend
├── input/         # A-roll and B-roll videos
└── output/        # Timeline JSON & final video
