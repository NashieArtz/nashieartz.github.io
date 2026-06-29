# My Astuce — School Project Demo

A front-end-only recreation of the "My Astuce" mobile app's **My tickets** screen
(Ongoing + Wallet tabs), built as an installable web app (PWA).

## What works

- **Wallet tab**: shows the active "Jeune 10 voyages Astuce" ticket with a
  live countdown timer.
- **Ongoing tab**: static recreation of the mTicket / Park-and-ride screen.
- **Extra exercise feature**: the ticket timer counts down from `00:59:00`.
  Once it reaches `00:11:05`, instead of expiring it jumps back up to
  `00:59:00` and keeps counting down — so the ticket "renews" itself
  forever and never actually runs out during a demo.
- Bottom nav and other tabs (**Home, Info, Favorites, Mobility usage,
  Account**) are present visually but just show a placeholder message,
  as requested — only **My tickets** is functional.

## Files

```
index.html      - the entire app (HTML/CSS/JS, no build step needed)
manifest.json   - PWA manifest (lets you "install" it on a phone home screen)
sw.js           - service worker (basic offline caching)
icon-192.png    - app icon
icon-512.png    - app icon
```

## How to host it

You don't need anything fancy — this is a static site, just 5 files.

### Option A — Run it locally on your computer (easiest, free)

1. Make sure you have Python installed (most computers already do).
2. Open a terminal in this folder.
3. Run:
   ```
   python3 -m http.server 8000
   ```
4. Find your computer's local IP address:
   - Windows: `ipconfig` → look for "IPv4 Address"
   - Mac/Linux: `ifconfig` or `ip addr` → look for something like `192.168.x.x`
5. On your phone, **connect to the same Wi-Fi network** as your computer.
6. Open a browser on your phone and go to:
   ```
   http://YOUR_COMPUTER_IP:8000
   ```
   e.g. `http://192.168.1.42:8000`
7. Tap the browser's menu → **"Add to Home Screen"** (or "Install app")
   to install it like a real app.

Your computer needs to stay on and the server running for the app to load.

### Option B — A cheap server (works from anywhere, not just home Wi-Fi)

Any static hosting works. Cheapest/easiest options:

- **GitHub Pages** (free): push these files to a GitHub repo, enable Pages
  in the repo settings, and you'll get a public URL instantly.
- **Netlify / Vercel** (free tier): drag-and-drop this folder onto their
  website, get a public URL in seconds.
- **A $5/month VPS** (e.g. a small DigitalOcean/Linode droplet): copy the
  files over and serve them with any web server (nginx, or even
  `python3 -m http.server 80`).

Once hosted, open the URL on your phone and use "Add to Home Screen" the
same way as above.

## Notes for your presentation

- This is a static **front-end recreation** for educational purposes —
  no real ticket validation, GPS, or payment happens.
- The "self-renewing ticket" countdown is the custom feature added on top
  of the original app's design, as required by the assignment.
