# Resse Angelo Badana — 3D Personal Portfolio

A futuristic, fully responsive 3D portfolio. No build step required — everything runs
from static files with libraries loaded via CDN (Three.js, GSAP + ScrollTrigger, Lenis).

## Live Website

[Visit My Portfolio](https://your-username.github.io/your-repository/)

## Technologies
- HTML
- CSS
- JavaScript
- Three.js

## Features
- 3D animations
- Responsive design
- Interactive elements
- Projects showcase

## Run it

Option A — just open `index.html` in a browser.
Option B (recommended, so the contact form & CV download work best):

npx serve .        # or: python -m http.server 8000

Then open http://localhost:8000 (or the port shown).

## What's inside

index.html                      all sections, semantic markup
css/style.css                   design system, dark/light themes, responsive
js/main.js                      navigation, typing, tilt, cards, modal, form, theme
js/three-scene.js               3D hero: particles, rotating core, floating shapes
assets/cv/                      downloadable CV (PDF)
assets/certificates/            certificate images (currently sample placeholders)

## Functionality map (every button works)

- Nav links / logo / footer arrow ......... smooth-scroll via Lenis (+ scroll-spy highlight)
- Theme toggle ............................ dark <-> light, saved to localStorage
- Mobile hamburger ........................ fullscreen menu, closes on link/Esc
- Download CV ............................. downloads the real PDF in assets/cv
- Explore My Projects ..................... smooth-scrolls to #projects
- Social icons ............................ toast tells you exactly where to add your URL
- Live Demo / GitHub buttons .............. honest placeholder toasts (no fake links)
- View Certificate ........................ opens image preview modal (Esc/backdrop closes)
- Contact form ............................ full frontend validation + real email delivery
via FormSubmit (see below)

## Make the contact form deliver to YOUR inbox

1. Open `js/main.js` and replace:

const EMAIL = "your.email@example.com";

with your real email address.

2. The first submission triggers a one-time confirmation email from FormSubmit —
click the confirmation link once, then all future messages arrive in your inbox.
3. If the service is unreachable, the form automatically falls back to opening the
visitor's email app with the message prefilled (mailto), so no message is ever lost.

## Add your own content

- Certificates: drop images in `assets/certificates/` and add an entry to the
`CERTS` array at the top of `js/main.js` (img, title, org, date).
- Projects: edit the `PROJECTS` array — when you have real URLs, replace the
toast handlers with `window.open("https://...")`.
- Social links: replace `href="#"` with your profile URLs in `index.html`.
- CV: overwrite `assets/cv/Resse-Angelo-Badana-CV.pdf` with your real CV
(keep the same filename, or update the download link in index.html).

## Performance notes

- 3D scene auto-pauses when off-screen or tab hidden
- Reduced particle/shape counts on mobile, capped devicePixelRatio
- `prefers-reduced-motion` respected (CSS + 3D animations)
- All animations are GPU-friendly transforms
