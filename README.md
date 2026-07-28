# FusioniX'26

> **The Ultimate Sustainable Tech & IoT Innovation Hackathon**
> Organized by ECE & CSE (IoT), University of Engineering & Management (UEM), Kolkata

FusioniX'26 is the official interactive hub for the FusioniX hackathon — a 24-hour hardware and software competition where participants ideate, design, and prototype real-world sustainable tech and IoT solutions.

---

## Tech Stack

| Layer | Technology |
|---|---|
| UI Framework | [React 19](https://react.dev/) |
| Language | [TypeScript ~5.8](https://www.typescriptlang.org/) |
| Build Tool | [Vite 6](https://vitejs.dev/) |
| Styling | [Tailwind CSS 4](https://tailwindcss.com/) (via `@tailwindcss/vite`) |
| AI Integration | (Planned) [Google Gemini API](https://ai.google.dev/) (`@google/genai`) |
| Deployment | [Firebase Hosting](https://firebase.google.com/products/hosting) |

---

## Project Structure

```
FUSIONIX-26/
├── src/
│   ├── App.tsx          # Main single-page application component
│   ├── main.tsx         # React entry point
│   ├── index.css        # Global styles
│   └── assets/
│       └── images/      # Images, videos, and PDF assets
├── index.html           # HTML shell
├── vite.config.ts       # Vite configuration
├── tsconfig.json        # TypeScript configuration
├── firebase.json        # Firebase Hosting configuration
├── .firebaserc          # Firebase project binding
├── .nvmrc               # Node.js version pin (24)
├── .env.example         # Environment variable template
└── package.json
```

---

## Local Development

### Prerequisites

- **Node.js 24** — use [nvm](https://github.com/nvm-sh/nvm) and run `nvm use` in the project root to automatically pick up the correct version from `.nvmrc`.
- **npm** (comes bundled with Node.js)

### 1. Clone the repository

```bash
git clone https://github.com/iemaserver/FUSIONIX-26.git
cd FUSIONIX-26
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Copy the example file and fill in the required values:

```bash
cp .env.example .env
```

| Variable | Description |
|---|---|
| `GEMINI_API_KEY` | (Optional) Gemini API key — only needed if/when Gemini integration is enabled |
| `APP_URL` | (Optional) Base URL for self-referential links/callbacks (currently not used in the app) |
### 4. Start the development server

```bash
npm run dev
```

The app will be available at **http://localhost:3000** with hot-module replacement (HMR) enabled.

---

## Available Scripts

| Script | Description |
|---|---|
| `npm run dev` | Start the Vite dev server on port 3000 |
| `npm run build` | Bundle for production with Vite (output: `dist/`). Run `npm run lint` for TypeScript type-checking. |
| `npm run preview` | Serve the production build locally for final checks |
| `npm run lint` | Run TypeScript type-checking (`tsc --noEmit`) |
| `npm run clean` | Remove build artifacts (`dist/`, `server.js`) |

---

## Building for Production

```bash
npm run build
```

Static assets are emitted to the `dist/` directory and are ready to be served by any static host.

To preview the production bundle locally before deploying:

```bash
npm run preview
```

---

## Deployment

The project is deployed to **Firebase Hosting** via GitHub Actions.

| Event | Action |
|---|---|
| Push to `main` | Deploys to the production Firebase Hosting site |
| Pull request targeting `main` | Deploys a 30-day preview channel; the preview URL is posted as a PR comment |

### Required GitHub secrets / variables

| Name | Type | Description |
|---|---|---|
| `FIREBASE_TOKEN` | Secret | Firebase CI token (`firebase login:ci`) |
| `FIREBASE_PROJECT_ID` | Variable | Firebase project ID (e.g. `fusionix-26`) |

---

## Features

- **Intro experience** — Full-screen video splash with an embedded Tic-Tac-Toe mini-game and auto-bypass countdown
- **Hero section** — Animated landing with hackathon key details and a CTA
- **About** — Event overview and organizer information
- **Theme** — Hackathon theme reveal
- **Timeline** — Schedule of rounds and milestones
- **Prizes** — Prize pool breakdown
- **Rules** — Participation guidelines
- **Team** — Organising committee and volunteer credits
- **FAQ** — Frequently asked questions
- **Sponsors** — Sponsor showcase with detail modals
- **Contact / Footer** — Social links and contact information
- **Ambient audio** — Toggle-able background music with browser autoplay handling
- **Responsive design** — Optimised for both desktop and mobile viewports
