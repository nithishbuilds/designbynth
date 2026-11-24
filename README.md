=====================================================================
  designbynth — PORTFOLIO WEBSITE
  Nithish · Graphic Designer · Video Editor · Web Developer
  Coimbatore, Tamil Nadu
=====================================================================

Dark theme with orange accents, separate pages, scrolling between pages,
freelance work galleries, the Pentacle New York company showcase, web
projects, and a WhatsApp enquiry form. Can connect to Firebase Firestore,
so items you upload show for every visitor.


---------------------------------------------------------------------
1. FILES
---------------------------------------------------------------------

  designbynth-portfolio/
    index.html          the whole website (HTML, CSS, JS, images inside)
    firestore.rules     security rules to paste into Firebase
    README.txt          this file
    videos/             video edits (kept separate, original quality)
        indian-dish-house-party.mp4
        thanal-indian-tavern.mp4
        thanal-express-favourite-foods.mp4
        knit-city-nagar-real-estate.mp4

  IMPORTANT: Always upload index.html AND the videos folder together,
  side by side. If the folder is missing, the videos will not play.


---------------------------------------------------------------------
2. PAGES
---------------------------------------------------------------------

  The site is one file, but each menu item opens its own page:

  Home       #home       Intro, photo, stats, Selected clients
  About      #about      About me, tools, counters, Services (#services)
  Work       #work       Poster row, logo row, video edits (#video)
  Pentacle   #pentacle   Pentacle New York company + product gallery
  Web Dev    #webdev     Web projects + GitHub
  Contact    #contact    Contact details, enquiry form, footer

  - Scrolling between pages: keep scrolling at the bottom of a page to
    go to the next one, or at the top to go back to the previous one.
  - Contact page: the footer and the "admin" login button appear only here.


---------------------------------------------------------------------
3. HOSTING
---------------------------------------------------------------------

  OPTION A: Netlify / Vercel / Cloudflare Pages / GitHub Pages
    1. Unzip the download.
    2. Drag the whole unzipped folder into the host
       (or push it to a GitHub repo).
    3. Done. The site is live at the URL they give you.

  OPTION B: cPanel / Hostinger / GoDaddy
    1. Open File Manager -> public_html
    2. Upload index.html AND the videos folder.
    3. Visit your domain.

  Requires internet: Tailwind CSS, Google Fonts and Firebase load
  from the internet (CDN).


---------------------------------------------------------------------
4. FIREBASE / FIRESTORE SETUP
---------------------------------------------------------------------

  Without a config, the site works on its own, but admin uploads are
  saved only in your own browser.

  With Firestore:
    - Uploads: anything added from Owner Login is saved online and
      visible to everyone.
    - Enquiries: each contact form submission is saved to the
      "enquiries" collection, and WhatsApp still opens.
    - Login: Owner Login uses secure Firebase email-and-password sign-in.

  STEPS
    1. Create a web app: in the Firebase console, open your project,
       go to Project settings -> General -> Your apps, and add a
       Web app (</>).

    2. Paste the config: open index.html, search for
          PASTE YOUR FIREBASE CONFIG HERE
       and fill in:
          apiKey, authDomain, projectId, storageBucket,
          messagingSenderId, appId

    3. Turn on login: go to Authentication -> Sign-in method ->
       Email/Password -> Enable

    4. Create your admin account: go to Authentication -> Users ->
       Add user, and use nithishvof@gmail.com with a strong password.
       (To use a different email, change it inside firestore.rules too.)

    5. Publish the rules: go to Firestore Database -> Rules, replace
       everything with the contents of firestore.rules, then click Publish.

    6. Upload the updated index.html.

  WHAT THE RULES ALLOW
    projects    visitors: read        owner: create / edit / delete
    settings    visitors: read        owner: edit
    enquiries   visitors: send only   owner: read / manage
    others      locked for everyone

  You can read enquiries in the Firebase console under
  Firestore Database -> enquiries.


---------------------------------------------------------------------
5. USING OWNER LOGIN (ADMIN)
---------------------------------------------------------------------

  1. Open the login: go to Contact, scroll to the footer, and click "admin".
  2. Sign in with your admin email (nithishvof@gmail.com) and password.
       - Without Firebase: the password is checked against a SHA-256
         hash inside index.html (the password itself is not stored).
       - With Firebase: use the same email/password you created in
         Authentication -> Users.
  3. Add work: go to Projects -> New Project.
       - Images: click "Upload image from device". It is shrunk
         automatically to under about 900 KB.
       - Videos: put the .mp4 file in the videos/ folder and enter
         videos/your-file.mp4 as the Media URL.
       - Category: choose "Logo Design" to show it in the logo row.
         Any other category goes to the poster row.
  4. Edit or delete items from the Projects table.


---------------------------------------------------------------------
6. EDITING CONTENT IN index.html
---------------------------------------------------------------------

  Open index.html in a text editor and search for these names:

  Web project links ................ WEB_PROJECTS  (fill in each url:'')
  About counters (13, 2 years) ..... label:'Projects Delivered'
  Hero stats ....................... id="heroStats"
  Selected clients ................. class="client"
  Posters .......................... const POSTERS
  Logos ............................ const LOGOS
  Burger House slider designs ...... GRAPHIC_SLIDES
  Pentacle products ................ PNY_PRODUCTS
  Video list ....................... VIDEO_WORKS
  Page titles / subtitles .......... class="ph-title" / class="ph-sub"
  Site assistant answers ........... AI_KB

  Contact details used on the site:
    Phone   : +91 93634 33837
    Email   : nithishvof@gmail.com
    GitHub  : github.com/nithishbuilds
  To change these, search and replace them throughout the file.


---------------------------------------------------------------------
7. NOTES
---------------------------------------------------------------------

  - Web Developer project cards show "Link coming soon" until you add
    their URLs in WEB_PROJECTS.
  - Videos must be hosted files (in videos/ or another URL).
    Firestore cannot store video.
  - Seeing an old version? Press Ctrl + Shift + R to clear the
    browser cache.


=====================================================================
  (c) designbynth · Nithish · Coimbatore, Tamil Nadu
=====================================================================
