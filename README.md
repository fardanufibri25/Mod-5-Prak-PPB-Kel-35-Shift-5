# Bore & Barrel

A dummy gunshop storefront built as a Progressive Web App. It runs offline
with an app shell, a web app manifest, and a service worker, and uses React +
Vite with a RESTful API (Supabase) for data.

## Setup

```bash
cp .env.example .env   # Windows: copy .env.example .env
npm install
npm run dev            # dev server with HMR
```

Other scripts:

```bash
npm run build    # production build to dist/
npm run preview  # serve the production build
npm run lint     # oxlint
```

## Structure

```
.
├── index.html              # HTML shell
├── vite.config.js          # Vite + vite-plugin-pwa (manifest + service worker)
├── public/                 # static assets served at /
│   ├── icon-192.png / icon-512.png / icon.svg
│   └── guns/               # product images
└── src/
    ├── main.jsx            # entry, mounts <App/>
    ├── App.jsx             # app shell: tab state, header/nav/content/footer
    ├── App.css             # all styles
    ├── config/api.js       # axios instance + Supabase headers/errors
    ├── services/           # gun, review, favorite, upload, user API wrappers
    ├── hooks/              # useGuns, useReviews, useFavorites
    ├── components/         # Header, Footer, PWA badge, cards, modals, filter
    ├── pages/              # Catalog, Favorites, Profile, Create, Edit, About, Contact
    ├── data/guns.js        # local fallback catalog
    └── utils/              # helpers + localStorage draft storage
```
