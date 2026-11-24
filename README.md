# designbynth — Portfolio Website

Portfolio of **Nithish (designbynth)**, a graphic designer, video editor and web developer based in Coimbatore, Tamil Nadu.

Dark theme with orange accents, separate pages, scrolling between pages, freelance work galleries, the Pentacle New York company showcase, web projects, and a WhatsApp enquiry form. Can connect to **Firebase Firestore**, so items you upload show for every visitor.

---

## 1. Files

```
designbynth-portfolio/
├── index.html          ← the whole website (HTML, CSS, JS, images all inside)
├── firestore.rules     ← security rules to paste into Firebase
├── README.md           ← this file
└── videos/             ← video edits (kept separate, original quality)
    ├── indian-dish-house-party.mp4
    ├── thanal-indian-tavern.mp4
    ├── thanal-express-favourite-foods.mp4
    └── knit-city-nagar-real-estate.mp4
```

> ⚠️ Always upload **`index.html` and the `videos` folder together**, side by side. If the folder is missing, the videos won't play.

---

## 2. Pages

The site is one file, but each menu item opens its own page:

| Page | Address | Content |
|---|---|---|
| Home | `#home` | Intro, photo, stats, Selected clients |
| About | `#about` | About me, tools, counters, Services (`#services`) |
| Work | `#work` | Poster row, logo row, video edits (`#video`) |
| Pentacle | `#pentacle` | Pentacle New York company + product gallery |
| Web Dev | `#webdev` | Web projects + GitHub |
| Contact | `#contact` | Contact details, enquiry form, footer |

- **Scrolling between pages:** keep scrolling at the bottom of a page to go to the next one, or at the top to go back to the previous one.
- **Contact page:** the footer and the **admin** login button appear only here.

---

## 3. Hosting

**Option A: Netlify / Vercel / Cloudflare Pages / GitHub Pages**
1. Unzip the download.
2. Drag the whole unzipped folder into the host (or push it to a GitHub repo).
3. Done. The site is live at the URL they give you.

**Option B: cPanel / Hostinger / GoDaddy**
1. Open **File Manager → `public_html`**.
2. Upload `index.html` **and** the `videos` folder.
3. Visit your domain.

**Requires internet:** Tailwind CSS, Google Fonts and Firebase load from CDNs.

---

## 4. Firebase / Firestore setup

Without a config, the site works on its own, but admin uploads are saved only in your own browser. With Firestore:

- **Uploads:** anything added from Owner Login is saved online and visible to everyone.
- **Enquiries:** each contact form submission is saved to the `enquiries` collection, and WhatsApp still opens.
- **Login:** Owner Login uses secure Firebase email-and-password sign-in.

### Steps
1. **Create a web app:** in the Firebase console, open your project, go to ⚙️ **Project settings → General → Your apps**, and add a Web app (`</>`).
2. **Paste the config:** open `index.html`, search for **`PASTE YOUR FIREBASE CONFIG HERE`**, and fill in:
   ```js
   window.FIREBASE_CONFIG = {
     apiKey: "...",
     authDomain: "...",
     projectId: "...",
     storageBucket: "...",
     messagingSenderId: "...",
     appId: "..."
   };
   ```
3. **Turn on login:** go to **Authentication → Sign-in method → Email/Password → Enable**.
4. **Create your admin account:** go to **Authentication → Users → Add user** and use **nithishvof@gmail.com** with a strong password.
   *(To use a different email, change it inside `firestore.rules` too.)*
5. **Publish the rules:** go to **Firestore Database → Rules**, replace everything with the contents of `firestore.rules`, then click **Publish**.
6. **Upload** the updated `index.html`.

### What the rules allow
| Collection | Visitors | Owner (logged in) |
|---|---|---|
| `projects` | read | create / edit / delete |
| `settings` | read | edit |
| `enquiries` | send only | read / manage |
| anything else | ✖ | ✖ |

You can read enquiries in the console under **Firestore Database → enquiries**.

---

## 5. Using Owner Login (admin)

1. **Open the login:** go to **Contact**, scroll to the footer, and click **admin**.
2. **Sign in** with your Firebase email and password.
3. **Add work:** go to **Projects → New Project**.
   - **Images:** click **Upload image from device**. It's shrunk automatically to under about 900 KB.
   - **Videos:** put the `.mp4` file in the `videos/` folder and enter `videos/your-file.mp4` as the Media URL.
   - **Category:** choose **Logo Design** to show it in the logo row. Any other category goes to the poster row.
4. **Edit or delete** items from the Projects table.

---

## 6. Editing content in `index.html`

Search for these names to change things quickly:

| What | Search for |
|---|---|
| Web project links | `WEB_PROJECTS` → fill in each `url:''` |
| About counters (13 projects, 2 years) | `label:'Projects Delivered'` |
| Hero stats | `id="heroStats"` |
| Selected clients | `class="client"` |
| Posters | `const POSTERS` |
| Logos | `const LOGOS` |
| Burger House slider designs | `GRAPHIC_SLIDES` |
| Pentacle products | `PNY_PRODUCTS` |
| Video list | `VIDEO_WORKS` |
| Page titles and subtitles | `class="ph-title"` / `class="ph-sub"` |
| Site assistant answers | `AI_KB` |

**Contact details:** phone +91 93634 33837, email nithishvof@gmail.com, GitHub github.com/nithishbuilds. To change these, search and replace them throughout the file.

---

## 7. Notes

- **Web Developer project cards:** they show "Link coming soon" until you add their URLs in `WEB_PROJECTS`.
- **Videos:** these must be hosted files (in `videos/` or another URL). Firestore can't store video.
- **Seeing an old version?** Press **Ctrl + Shift + R** to clear the browser cache.

---

© designbynth · Nithish · Coimbatore, Tamil Nadu
