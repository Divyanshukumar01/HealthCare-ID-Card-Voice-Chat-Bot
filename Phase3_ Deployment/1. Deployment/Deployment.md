# 🚀 Deployment

This project is deployed using **Vercel** forming an actual CI/CD pipeline from **GitHub**.


<img width="1440" height="900" alt="Screenshot 2026-07-15 at 01 27 25" src="https://github.com/user-attachments/assets/acb8aec0-c989-4725-b381-60f039c27ce3" />

<img width="1440" height="900" alt="Screenshot 2026-07-15 at 01 28 49" src="https://github.com/user-attachments/assets/ae6ea84e-f775-4824-bb48-490c707578ef" />


## Deployment Workflow

1. Push the latest code to the GitHub repository.
2. Vercel automatically detects changes on the connected branch.
3. A new build is triggered automatically.
4. If the build succeeds, the latest version is deployed and made available through the live URL.

This CI/CD workflow ensures every code update is automatically reflected in the production deployment without requiring manual uploads.

## Tech Stack

* **Frontend:** React.js + Vite
* **Styling:** Tailwind CSS
* **Hosting:** Vercel
* **Version Control:** Git & GitHub
* **Conversational AI:** Google Cloud CX Agent Studio

## Environment Variables

Create a `.env` file (or configure the variables in the Vercel dashboard) and add the required environment variables.

```env
VITE_AGENT_ENDPOINT=your_agent_endpoint
VITE_API_BASE_URL=your_api_base_url
```

> Replace the values above with your actual deployed API endpoints.

## Local Development

Clone the repository and install dependencies:

```bash
git clone <repository-url>
cd <project-folder>
npm install
npm run dev
```

The application will start on:

```
http://localhost:5173
```

## Production Build

To generate an optimized production build:

```bash
npm run build
```

To preview the production build locally:

```bash
npm run preview
```

## Automatic Deployment

Every push to the connected GitHub branch automatically:

* Builds the application
* Deploys the latest version on Vercel
* Generates a production deployment URL
* Updates the live website if the build is successful



