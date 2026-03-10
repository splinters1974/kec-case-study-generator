# KEC Case Study Generator

Three-format case study generator (LinkedIn carousel, Medium PDF, Long-form blog) with AI-powered prose generation.

## Setup

### Backend Proxy (Required)

The HTML app communicates with the Anthropic API through a Node.js proxy to avoid CORS issues and keep your API key secure.

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Create `.env` file:**
   ```bash
   cp .env.example .env
   ```

3. **Add your API key to `.env`:**
   ```
   ANTHROPIC_API_KEY=sk-ant-api03-YOUR_KEY_HERE
   PORT=3000
   ```

4. **Start the proxy server:**
   ```bash
   npm start
   ```
   The server runs on `http://localhost:3000`

### Frontend

1. Open `kec-case-study-generator.html` in your browser (or use VS Code Live Server)
2. The app will automatically connect to the proxy at `localhost:3000`
3. Fill in your project details and hit "Generate Case Studies"

## Features

- **Three output formats:**
  - LinkedIn carousel (5 slides with images)
  - Medium PDF (1-2 pages, downloadable)
  - Long-form blog (up to 1000 words, downloadable HTML)

- **Input to AI prose:**
  - Challenge & solution as bullet points → AI expands to prose
  - Results as narrative → AI refines for clarity
  - Quotes woven naturally into output

- **Browser storage:**
  - All inputs auto-save locally
  - Return and edit anytime

- **Metadata:**
  - Client name, project type, size, location
  - kWh generation, carbon savings, financial savings
  - Stakeholder names, roles, quotes

- **Image support:**
  - Up to 3 images
  - Auto-placed in carousel, PDF, and blog outputs

## Deployment

For production hosting, keep the API key in environment variables on your server. The proxy handles the API call securely server-side.

## Tech Stack

- **Frontend:** Vanilla HTML/CSS/JS, single-file app
- **Backend:** Node.js + Express
- **PDF generation:** html2pdf.js
- **AI:** Anthropic Claude API (claude-sonnet-4-20250514)
