# Wanderly – Travel Booking Website

A modern, responsive travel booking front-end built with **React 18, Vite, React Router, Lucide icons and custom CSS**.

> **Demo project.** All destinations, prices, reviews and testimonials are sample data. Booking uses local state only: no payment is taken and no real reservation is made.

## Features

- Home page with hero, search bar, popular destinations, featured packages, offers, testimonials, FAQ
- Destination search, filters (category, budget, duration), sorting and a "clear filters" option (state lives in the URL)
- Destination details: gallery with lightbox, overview, attractions, packages, accommodation, pricing, reviews
- 3-step booking flow (details → review → confirmation) with validation and live price calculation
- Working promo codes: `WELCOME10`, `FAMILY12` (4+ travellers), `CITY8` (city destinations)
- Gallery with category filter and lightbox (arrow keys and Esc supported)
- About, Packages, FAQ, Contact pages, mobile navigation, loading skeletons and empty states

---

## Windows: beginner-friendly setup

### Step 1: Install Node.js (one time)

1. Go to **https://nodejs.org** and download the **LTS** version (the green button).
2. Run the installer and keep clicking **Next** with the default options.
3. Restart your computer if the installer asks you to.
4. Check it worked: press the **Windows key**, type **cmd**, press **Enter**, then run:

   ```
   node -v
   npm -v
   ```

   Both commands should print version numbers (Node 18 or newer is required).

### Step 2: Unzip the project

1. Right-click `wanderly.zip` → **Extract All…**
2. Choose a simple location such as `C:\Projects` and click **Extract**.
3. You should now have a folder like `C:\Projects\wanderly`.

### Step 3: Open a terminal in the project folder

Easiest way: open the `wanderly` folder in File Explorer, click the address bar, type `cmd` and press **Enter**.

Or use Command Prompt and type:

```
cd C:\Projects\wanderly
```

### Step 4: Install dependencies (one time, needs internet)

```
npm install
```

Wait until it finishes (about a minute). Warnings are normal; red `npm ERR!` lines are not.

### Step 5: Start the website

```
npm run dev
```

Your browser should open at **http://localhost:5173**. If it doesn't, open that address manually. Press **Ctrl + C** in the terminal to stop the server.

### Step 6 (optional): Make a production build

```
npm run build
npm run preview
```

---

## Deploy to Vercel

1. Create a free account at https://vercel.com and push this folder to a GitHub repository.
2. In Vercel click **Add New → Project**, import the repository.
3. Vercel auto-detects **Vite**. Leave the defaults (Build: `npm run build`, Output: `dist`) and click **Deploy**.

`vercel.json` already contains the rewrite that makes React Router links work after a page refresh.

(Alternative: run `npx vercel` in the project folder and follow the prompts.)

---

## Troubleshooting (Windows)

| Problem | Fix |
| --- | --- |
| `'node' is not recognized` | Close and reopen the terminal, or restart the PC after installing Node.js. |
| `npm : File ... cannot be loaded because running scripts is disabled` (PowerShell) | Use **Command Prompt (cmd)** instead, or run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` in PowerShell. |
| `Port 5173 is already in use` | Close the other terminal running the site, or run `npm run dev -- --port 3000`. |
| Photos show a coloured gradient | Images load from Unsplash and need internet. A gradient is shown if a photo link fails; swap URLs in `src/data/destinations.js`. |
| Page is blank after `npm install` errors | Delete the `node_modules` folder and run `npm install` again. |

## Project structure

```
src/
  components/   reusable UI (Navbar, cards, Lightbox, Accordion, …)
  pages/        route pages (Home, Destinations, DestinationDetails, Booking, …)
  data/         sample destinations and marketing content
  services/     mock API layer (replace with fetch() for a real backend)
  hooks/        useAsync data-loading hook
  utils/        pricing and date helpers
  styles/       base.css, components.css, pages.css
  App.jsx       routes
  main.jsx      entry point
```

## Customising

- **Destinations and prices:** `src/data/destinations.js`
- **Offers, FAQs, testimonials:** `src/data/content.js`
- **Colours:** CSS variables at the top of `src/styles/base.css`
- **Real backend:** edit `src/services/api.js`
