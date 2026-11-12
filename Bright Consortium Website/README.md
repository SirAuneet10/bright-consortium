# Bright Consortium Ltd. – website

A fast, animated one-page website with a built-in editor. No build step, no framework.

```
index.html      the whole site + the editor (#admin)
content.json    ALL text, numbers, photos, links, colours and SEO
assets/         photos (assets/img), share image, icons
favicon.svg     browser tab icon
vercel.json     caching settings for Vercel
robots.txt      lets Google index the site
```

---

## 1. Put the site online (GitHub + Vercel, free)

**A. Create the GitHub repository**
1. Go to **github.com** and sign up / sign in.
2. Click **+** (top right) → **New repository**.
3. Name it, e.g. `bright-consortium-website`. Choose **Private** or **Public**. Click **Create repository**.
4. On the empty repository page, click the link **"uploading an existing file"**.
5. Open this `site` folder on your computer, select **everything inside it** (index.html, content.json, favicon.svg, vercel.json, robots.txt, README.md **and the `assets` folder**) and drag it into the browser window.
   - The `assets` folder must stay a folder. Chrome and Edge keep folders when you drag them.
6. Click the green **Commit changes** button.

**B. Connect Vercel**
1. Go to **vercel.com** → **Sign up** → **Continue with GitHub**.
2. Click **Add New… → Project**.
3. Find your repository and click **Import**.
4. Framework Preset: **Other**. Leave Build Command and Output Directory empty.
5. Click **Deploy**. After about a minute you get an address like `bright-consortium-website.vercel.app`.

From now on, **every change you commit on GitHub goes live automatically** within about a minute.

---

## 2. Edit the content (no code)

1. Open your site address and add **`#admin`** at the end, for example
   `https://bright-consortium-website.vercel.app/#admin`
2. **First visit:** create an ID and password (8+ characters).
   Only a salted PBKDF2 hash is stored, never the password.
   *Honest note:* this login only keeps casual visitors out of the editor. The real protection is that **only you can publish**, because publishing needs your GitHub account.
3. Edit anything with the tabs (Brand & colours, Hero & numbers, About, Media, Map, Showcase, Process, Terms, Leadership, Contact, Footer, SEO). The site behind the editor updates live.
   - `*word*` makes a word **gold italic**. `|` forces a line break in a heading.
   - Lists have **＋ Add, ↑ ↓ (reorder), ⧉ (duplicate) and ✕ (delete)**.
   - **Upload** buttons compress images automatically.
   - **Showcase** items have: category (create new ones from the Category drop-down), thumbnail, gallery photos, link, video link, company logo and a "Demo visual" switch.
4. Your edits are saved **on this device** as a draft until you publish.

### Publish your changes
1. In the editor, click **Download content.json**.
2. On **github.com**, open your repository → **Add file** → **Upload files**.
3. Drag in `content.json`. The name must be exactly **content.json**. If your computer saved it as `content (1).json`, rename it first.
4. Click **Commit changes**. The site updates in about a minute.

**From a phone:** do the same in Chrome or Safari at github.com. If you can't see **Add file**, open the browser menu and tick **Desktop site**.

### Built-in safety
- Before downloading, the editor compares your file with the live site. If anything would disappear, it lists the items and offers **Add items from live site**.
- It warns you if the live site changed since you started editing (for example from another device).
- The file size is shown at the top: green is fine, amber is getting large (over 1.5 MB), red is too large (over 4 MB).
- **⋯ menu:** Import / restore a content.json, Download backup of live site, Discard draft, Change login.
- Every content.json you downloaded is a backup. Keep them.

**Tip for many photos:** uploading in the editor stores photos inside content.json, which is fine for a few. For lots of photos, upload them on GitHub into `assets/img`, then type the path (for example `assets/img/new-site.webp`) into the image box instead.

---

## 3. Enquiry form (Formspree, free)

Without setup, "Send enquiry" opens the visitor's email app with the message filled in. To receive enquiries straight to your inbox:
1. Go to **formspree.io** → sign up → **New form** → enter the email address that should receive enquiries.
2. Copy the form endpoint. It looks like `https://formspree.io/f/abcdwxyz`.
3. Editor → **Contact** → **Form endpoint (Formspree)** → paste → Download and publish content.json.
4. Send a test enquiry and confirm it in the Formspree email.

---

## 4. Colours and fonts

Editor → **Brand & colours**:
- **Colours:** navy, darkest background, gold, light gold, light section background and dark text.
- **Fonts:** type any Google Fonts name exactly as written on fonts.google.com, for example `Bebas Neue`, `Playfair Display` or `Inter`.

The same values are in `content.json` under `"theme"`.

---

## 5. Custom domain (e.g. brightconsortium.com)

1. Vercel → your project → **Settings → Domains** → type your domain → **Add**.
2. Vercel shows the DNS records to add at the company where you bought the domain. Usually that's an **A** record `76.76.21.21` for the root domain and a **CNAME** `cname.vercel-dns.com` for `www`. Use exactly what Vercel shows.
3. Wait until Vercel shows "Valid Configuration". HTTPS is added automatically.
4. Editor → **SEO** → **Website address** → enter `https://yourdomain.com` → publish. This makes Google and WhatsApp previews use the right address.

---

## 6. Videos

Any **Video link** field (hero showreel or showcase item) accepts YouTube, Vimeo, Facebook or a direct `.mp4` link. Videos play inside the page, full screen on phones.

## 7. Check before launch
- **Logo:** the logo is redrawn from the proposal. To use your original file, upload a transparent PNG/SVG in Brand → Logo image.
- **Photos:** station, train and seat-cover photos are marked **"Demo visual"** because they show mock-up ads. The note under Showcase says ad creatives are for illustration only.
- **Numbers:** all numbers come from your proposal (10 stations, 50 station screens, 28 billboards + 16 light boxes, 2,000 seat covers). Edit them anytime in Hero & numbers.
- **Email:** the contact email is the Gmail address from the proposal. You can change it in Contact.

## 8. Preview on your own computer (optional)
The site loads `content.json`, which browsers block when you double-click `index.html`. Use a tiny local server instead: install Node.js, then run `npx serve` inside this folder and open the address it prints.
