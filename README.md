🔮 AI Creator Studio

A full-stack, professional-grade image generation studio built using React, Firebase, and Cloudflare Workers.

This application provides a sleek, authenticated, dark-mode interface for generating high-quality images via Stable Diffusion XL, complete with user history and aspect ratio controls.

✨ Features

Level 100 UI: Highly polished, dark-mode interface with professional design aesthetics (similar to top-tier developer tools).

Full Authentication: Secure Sign In / Sign Up flow using Firebase Email/Password Authentication.

Persistent History: Real-time generation history saved to Google Firestore, displayed in a dedicated sidebar.

Cloudflare Backend: Leverages a custom Cloudflare Worker API for secure and scalable image generation (Stable Diffusion XL).

Aspect Ratio Controls: Dedicated buttons to easily switch between 1:1, 16:9, and 9:16 aspect ratios.

Single-File Architecture: The entire frontend application logic is contained in a single React component (src/ImageGeneratorApp.jsx).

🛠️ Technology Stack

Component

Technology

Purpose

Frontend

React, Vite

Modern, component-based UI.

Styling

Tailwind CSS

Utility-first, professional, responsive design.

Auth & DB

Firebase Authentication, Firestore

User management and real-time history persistence.

Image API

Cloudflare Workers AI

Secure, serverless image generation backend.

🚀 Getting Started (Local Development)

To run this project locally, you need Node.js and npm installed.

1. Project Setup

# Clone the repository
git clone [YOUR_REPOSITORY_URL]
cd [YOUR_REPOSITORY_NAME]

# Install project dependencies
npm install

# Install Tailwind CSS (if not already set up)
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p


(Note: Ensure your tailwind.config.js and src/index.css are set up to correctly compile Tailwind classes.)

2. Configure Firebase

This app relies on three global variables provided by your hosting environment (like the one you're working in) for Firebase initialization.

You must provide the Firebase configuration object and the App ID to the frontend.

Crucially: You need to enable Email/Password authentication in your Firebase console.

3. Link Cloudflare Worker

You must update the WORKER_URL constant inside src/ImageGeneratorApp.jsx to point to your live Cloudflare Worker endpoint:

// Inside src/ImageGeneratorApp.jsx
const WORKER_URL = "https://<your-worker-name>.<your-subdomain>.workers.dev"; 
// ^^^ REPLACE THIS LINE ^^^


4. Run the App

Start the local development server (Vite):

npm run dev


The app will open in your browser, usually at http://localhost:5173/.

🚢 Deployment (Go Live)

The recommended deployment method for this project is Cloudflare Pages due to its seamless integration with Cloudflare Workers.

Commit and Push: Ensure all changes are committed and pushed to your GitHub repository.

Connect to Cloudflare Pages:

Log in to the Cloudflare dashboard.

Go to Workers & Pages > Create application > Pages > Connect to Git.

Select your repository.

Use the following build settings:

Framework: Vite

Build command: npm run build

Build output directory: dist

Cloudflare will handle the rest, providing you with a live, global URL for your application!
