# AI Wealth Creation — Opportunity Watch Pages

Static site hosted on Netlify, deployed automatically from GitHub.

```
/
├── index.html          → aiwealthcreation.com           (neutral holding page)
├── aurum/index.html    → aiwealthcreation.com/aurum      (AURUM watch page)
├── netlify.toml        → tells Netlify: no build, serve from root
└── README.md           → this file
```

ELYT later = add `/elyt/index.html` (duplicate aurum, swap brand + embed + booking).

---

## ONE-TIME SETUP

### 1. GitHub
- Create a new repo named `aiwealthcreation` (Private is fine).
- Upload everything in this folder to the repo root
  (GitHub web: "Add file → Upload files", drag the contents in — not the outer folder).

### 2. Netlify
- Add new site → **Import an existing project** → connect GitHub → pick the repo.
- Build command: **leave blank**
- Publish directory: **`.`** (root)
- Deploy. Done — every push to the repo now auto-deploys.

### 3. Domain (GoDaddy → Netlify)
- Netlify → Domain management → **Add a domain** → `aiwealthcreation.com`
- Easiest: set GoDaddy **nameservers** to the ones Netlify shows, let Netlify run DNS.
  (Or keep DNS at GoDaddy and add the apex A record + www CNAME Netlify gives you.)
- Use the EXACT values Netlify shows on the day. HTTPS turns on automatically.

Result:
- `aiwealthcreation.com/aurum` → AURUM watch page
- `aiwealthcreation.com` → holding page

---

## WEEKLY UPDATE (each Thursday)

The ONLY thing that changes each week is the StreamYard embed URL
(new webinar = new embed code).

1. In StreamYard, get this week's embed (⋮ → On-Air settings → Embed → Copy).
2. Open `aurum/index.html`. Find the line marked:
       `<!-- EMBED: AURUM live StreamYard player (swap this src each week ...) -->`
3. Replace the `src="https://streamyard.com/watch/XXXX?embed=true"` value with the new one.
4. Commit + push (VS Code, or edit in GitHub web → Commit).
5. Netlify auto-deploys in ~1 minute. Live.

That's it. Nothing else moves.

---

## BOOKING LINK
Currently Jeff's Calendly (`calendly.com/jefferyross/20-min-gps`) — solo, all bookings go to Jeff.
To swap to a round robin later: in `aurum/index.html` find the line marked
`<!-- BOOKING: ... -->` and replace the href.
