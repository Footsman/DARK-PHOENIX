# Dark Phoenix — Claude Project Context

## What We Are Building
LunarTech fellowship assignment. Two projects:
1. Dark Phoenix — AI video clipping platform (deployment + YouTube ingestion + watermark)
2. Babel — Chinese/Russian OCR + translation pipeline (not started yet)

## Current Status

### COMPLETED
- Both GitHub repos created (private)
  - https://github.com/Footsman/dark-phoenix-submission
  - https://github.com/Footsman/babel-submission
- Collaborator vahekaren@gmail.com added to both repos
- Cursor set up with both projects and .cursorrules files
- main.py updated with:
  - yt-dlp added to Modal image apt_install
  - unartch watermark via ffmpeg drawtext filter
  - process_youtube endpoint added
  - ProcessYouTubeRequest model added
  - output files renamed to include _unartch
- AWS S3 bucket: dark-phoenix-footsman (us-east-2)
- AWS IAM user: dark-phoenix-app (S3FullAccess)
- Supabase database created (us-east-2)
- Inngest account created, both keys saved
- Modal installed and authenticated (footsman workspace)
- .npmrc with legacy-peer-deps=true added
- .node-version with 20.11.0 added
- Next.js reverted to 15.3.2

### IN PROGRESS
- Render deployment failing on prisma generate in postinstall
- Fix needed: change postinstall in package.json from:
  "postinstall": "prisma generate"
  to:
  "postinstall": "npx prisma generate"

### STILL TO DO
- Fix Render deployment
- Set BASE_URL in Render environment to https://dark-phoenix.onrender.com
- Deploy Modal backend (modal deploy main.py)
- Create Modal secret named ai-podcast-clipper-secret with these keys:
  GEMINI_API_KEY, AUTH_TOKEN, AWS_ACCESS_KEY_ID, 
  AWS_SECRET_ACCESS_KEY, AWS_REGION, S3_BUCKET_NAME
- Push Prisma schema to Supabase (npx prisma db push)
- Create test user in database with credits
- Connect Inngest to deployed Render app
- Update PROCESS_VIDEO_ENDPOINT in Render with real Modal URL
- Create admin script scripts/run-youtube-assignment.ts
- Run YouTube video YRvf00NooN8 through pipeline
- Download clips from S3
- Upload clips to Google Drive
- Share Google Drive folder with tk.lunartech@gmail.com and vahekaren@gmail.com
- Write DEPLOYMENT.md and WRITE_UP.md
- Tag commit as submitted
- Send submission email to tk.lunartech@gmail.com

## Key Details

### File Paths
- Backend: C:\Users\Footsman\OneDrive\Documents\GitHub\projects\DARK-PHOENIX\ai-podcast-clipper-backend
- Frontend: C:\Users\Footsman\OneDrive\Documents\GitHub\projects\DARK-PHOENIX\ai-podcast-clipper-frontend
- Babel: C:\Users\Footsman\OneDrive\Documents\GitHub\projects\BABEL-EXTREME-X-OPEN

### Environment Variables (already configured in Render)
- AUTH_SECRET: generated via openssl
- DATABASE_URL: Supabase connection string
- AWS_ACCESS_KEY_ID: saved
- AWS_SECRET_ACCESS_KEY: saved
- AWS_REGION: us-east-2
- S3_BUCKET_NAME: dark-phoenix-footsman
- INNGEST_EVENT_KEY: saved
- INNGEST_SIGNING_KEY: saved
- PROCESS_VIDEO_ENDPOINT_AUTH: dark-phoenix-auth-token-2024
- STRIPE keys: all set to placeholder values
- BASE_URL: https://dark-phoenix.onrender.com
- NODE_VERSION: 20.11.0

### Deployment Targets
- Frontend: Render (https://dark-phoenix.onrender.com)
- Backend: Modal (footsman workspace)
- Database: Supabase
- Storage: AWS S3 (us-east-2, bucket: dark-phoenix-footsman)
- Queue: Inngest Cloud

### Assignment Video
- URL: https://www.youtube.com/watch?v=YRvf00NooN8
- Duration: 1hr 6min
- Video ID: YRvf00NooN8

### Watermark Details
- Text: unartch
- Font: Anton (already in Modal image)
- Position: top-right
- Size: 48px
- Opacity: 80%
- Implementation: ffmpeg drawtext filter in create_subtitles_with_ffmpeg()

### Submission Requirements
- Email to: tk.lunartech@gmail.com
- GitHub access: vahekaren@gmail.com
- Google Drive shared with: tk.lunartech@gmail.com and vahekaren@gmail.com
- Clip naming: dark-phoenix_YRvf00NooN8_clip_01_unartch.mp4
- Required files: clips_manifest.json, DEPLOYMENT.md, WRITE_UP.md
- Git tag: submitted