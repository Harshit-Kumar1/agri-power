# AgriPower Deployment Guide (Free Platforms)

This guide provides instructions for deploying the **AgriPower** project using free hosting services.

## Backend Deployment (Render - FREE)

1.  **Create a Render account**: Go to [render.com](https://render.com) and sign up.
2.  **Create a New Web Service**:
    *   Connect your GitHub repository.
    *   **Root Directory**: `backend`
    *   **Build Command**: `npm install`
    *   **Start Command**: `node server.js`
3.  **Environment Variables**:
    *   `MONGODB_URI`: `mongodb+srv://kumarharshit4458_db_user:Mypassword123@cluster0.mckf1ct.mongodb.net/agripower?appName=Cluster0`
    *   `JWT_SECRET`: (Set a strong secret, e.g., `your_jwt_secret_here`)
    *   `NODE_ENV`: `production`
    *   `PORT`: `5000` (Render will override this, but it's good for documentation)
4.  **Backend URL**: Once deployed, copy the backend URL (e.g., `https://agripower-backend.onrender.com`).

## Frontend Deployment (Vercel or Netlify - FREE)

### Option A: Vercel
1.  **Create a Vercel account**: Go to [vercel.com](https://vercel.com) and sign up.
2.  **Project Setup**:
    *   Import your GitHub repository.
    *   **Root Directory**: `frontend`
    *   **Framework Preset**: Vite
3.  **Environment Variables**:
    *   `VITE_API_URL`: `https://your-backend-url.onrender.com/api` (Replace with your Render URL)
4.  **Deploy**: Click Deploy.

### Option B: Netlify
1.  **Create a Netlify account**: Go to [netlify.com](https://app.netlify.com/signup) and sign up.
2.  **Project Setup**:
    *   Click "Add new site" -> "Import an existing project".
    *   Connect your GitHub repository.
    *   **Base Directory**: `frontend`
    *   **Build Command**: `npm run build`
    *   **Publish Directory**: `dist`
3.  **Environment Variables**:
    *   Go to **Site settings** -> **Environment variables**.
    *   Add `VITE_API_URL`.
4.  **Deploy**: Trigger a manual deploy if needed.

## Database Access

Ensure your MongoDB Atlas cluster allows connections from outside (Render IPs). In MongoDB Atlas:
*   Go to **Network Access**.
*   Add `0.0.0.0/0` (Allow access from anywhere) if you can't get specific IPs.

## Testing Your Deployment

1.  Open your Vercel URL.
2.  Try logging in and interacting with the system.
3.  Check the browser console for any API errors.
