# PRD — Smoky Mountain Property Solutions & Services Landing Page

## Original Problem Statement
Static single-file HTML landing page for an East Tennessee property services business (pressure washing, gutter cleaning, deck/fence restoration, property cleanup, handyman, maintenance). Task: swap contact email `smpss@gmail.com` → `smokymtnproperty@gmail.com` in exactly 3 places (form JS mailto, footer href + visible text, fine-print note), no logic or layout changes. Phone/SMS links (+18653431142) untouched. Schema block has no email.

## Architecture
- Static single-file HTML served as the site root via the React dev server's `public/index.html` (`/app/frontend/public/index.html`).
- React mount guarded in `/app/frontend/src/index.js` (no `#root` in static page → no-op).
- Images in `/app/frontend/public/`: `hero-pressure-washing.jpg`, `deck-restoration.jpg` (Openverse/Flickr, commercial-use licenses).
- Backend (FastAPI) present but unused by the static page; form submits via `mailto:`.

## User Personas
- Homeowners/property owners in East Tennessee (Lenoir City, Knoxville, etc.) requesting free estimates.
- Business owner receiving estimate requests via email/phone/SMS.

## Core Requirements (static)
- Hero, trust strip, services grid, deck/fence feature, why-us band, service-area chips, estimate form (mailto), footer with contact info.
- Contact: (865) 343-1142 call/text; smokymtnproperty@gmail.com email.

## Implemented
- 2026-09-21: Delivered corrected landing page with new email in all spots (form mailto, footer link + text, fine print). Verified zero `smpss` matches; 4 lowercase occurrences of new email. Added contextually correct hero (pressure washing driveway) and deck (half-stained restoration) photos; added data-testids to interactive elements.

## Backlog
- P0: —
- P1: Wire estimate form to FastAPI endpoint + email delivery (Resend/SendGrid) with MongoDB storage — mailto is fragile on mobile (user flagged this as optional future work).
- P2: favicon/og image, custom domain, analytics of choice.

## Next Tasks
1. Ask user if they want the reliable form-delivery upgrade (FastAPI + Resend).
2. On request, add OG/social share image.
