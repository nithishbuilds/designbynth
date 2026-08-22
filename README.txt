designbynth Portfolio — Hosting Guide
======================================

This site is a single self-contained file: index.html
It includes all HTML, CSS (via Tailwind CDN), JavaScript, fonts (Google Fonts CDN),
your personal photo, your NTH logo (nav bar + browser tab favicon), the Graphic
Design Portfolio slider images, and an on-site AI FAQ assistant — all embedded
directly in the file. There are no other files to upload.

HOW TO HOST IT
---------------
Option 1 — Any static host (easiest):
  Netlify / Vercel / GitHub Pages / Cloudflare Pages:
  1. Create a new site/project.
  2. Upload this index.html (or drag-and-drop the whole folder).
  3. Done — your site goes live at the URL they give you.

Option 2 — Your own domain + hosting (cPanel, Hostinger, GoDaddy, etc.):
  1. Log in to your hosting control panel / File Manager.
  2. Go to the public folder (usually called public_html or www).
  3. Upload index.html there.
  4. Visit your domain — the site will load automatically.

IMPORTANT — BEFORE GOING LIVE
-------------------------------
1. Change the admin password.
   Open index.html, search for:
       adminUser: 'nithish',
       adminPass: 'portfolio2026',
   Change 'portfolio2026' to a strong password of your choice, then re-upload the file.

2. Uploads through the Owner Login are stored in the browser (localStorage), not a
   real database. Items you add there only show up on the browser/device you added
   them from — not to other visitors.

3. Internet connection required.
   The page loads Tailwind CSS and Google Fonts from the internet (CDN).

4. The AI assistant (bottom-right chat button) is a built-in, rule-based FAQ helper
   — it answers from a fixed knowledge base about your services, pricing, portfolio,
   and contact info, and politely redirects anything off-topic. It runs entirely in
   the browser (no external AI API, no ongoing cost). If you'd like it upgraded to
   a true generative AI (more natural, handles more phrasing), that needs a small
   backend to safely call an AI API — ask if you'd like help setting that up.
   To edit its answers, search index.html for "AI_KB" and edit the keywords/answers.

WHAT'S ON THE SITE
--------------------
- Cinematic intro animation using your photo
- Your NTH logo in the nav bar AND browser tab (favicon)
- About / Services sections
- Graphic Design Portfolio — image slider with prev/next arrows, dots, and autoplay
- Professional Video Editing (upload-only placeholder until you add work)
- On-site AI assistant — answers site-related questions only
- Contact form with WhatsApp enquiry (categories + budget ranges)
- Password-protected Owner Login for adding portfolio items

CONTACT INFO ON SITE
---------------------
Phone: +91 93634 33837
Email: nithishvof@gmail.com
Location: Coimbatore, Tamil Nadu – 641001
