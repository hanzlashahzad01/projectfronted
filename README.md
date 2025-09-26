# SmartFix Frontend (CRA) for Vercel

This folder hosts the standalone React (Create React App) admin dashboard, ready for deployment to Vercel.

## Structure
- `src/` React source code
- `public/` static assets (including `index.html` and optional `firebase-messaging-sw.js`)
- `package.json` CRA scripts
- `tailwind.config.js` Tailwind config
- `postcss.config.js` PostCSS config
- `.env.example` Sample environment variables

## Environment Variables
Create a `.env` file (not committed) based on `.env.example`:

- `REACT_APP_API_URL` Backend API base, e.g. `https://your-backend.onrender.com/api`
- `REACT_APP_SOCKET_URL` WebSocket/Socket.IO URL, e.g. `https://your-backend.onrender.com`
- Optional Firebase Web SDK keys if using FCM in the browser:
  - `REACT_APP_FIREBASE_API_KEY`
  - `REACT_APP_FIREBASE_AUTH_DOMAIN`
  - `REACT_APP_FIREBASE_PROJECT_ID`
  - `REACT_APP_FIREBASE_STORAGE_BUCKET`
  - `REACT_APP_FIREBASE_MESSAGING_SENDER_ID`
  - `REACT_APP_FIREBASE_APP_ID`

## Vercel Deployment
- Framework Preset: Create React App
- Build Command: `npm run build`
- Output Directory: `build`
- Environment Variables: set the variables above in Vercel Project Settings

## Local Development
```bash
npm install
cp .env.example .env  # on Windows, copy manually
npm start
```

The app reads API base from `REACT_APP_API_URL`. WebSocket base reads from `REACT_APP_SOCKET_URL` or falls back to the API base without `/api`.
