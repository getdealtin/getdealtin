# getdealtin.com — Site Structure

## File Organization

```
getdealtin.com/
├── index.html              ← MAIN HUB (welcome page, onboarding, card table)
├── homebuying.html         ← Home Buying tool
├── ben.png                 ← Ben Franklin image (required by both HTML files)
├── dealt_cards.png         ← Dealt cards image (required by index.html)
├── Casino_Card_Table_Wood.png ← Card table image (required by index.html)
└── README.md               ← This file
```

## External Tools (hosted separately on Render — DO NOT move)

| Tool | URL | Reason |
|------|-----|--------|
| Follow the Money | https://follow-the-money.onrender.com | Security isolation |
| Make It Stretch (Afford to Eat) | https://make-it-stretch.onrender.com | Security isolation |

## Navigation Map

```
index.html
  ├── → homebuying.html           (same domain)
  ├── → follow-the-money.onrender.com  (new tab)
  ├── → make-it-stretch.onrender.com   (new tab)
  └── → Card Table (coming soon)

homebuying.html
  ├── ← index.html               (back to platform)
  ├── → follow-the-money.onrender.com  (new tab)
  └── → make-it-stretch.onrender.com   (new tab)
```

## Deployment Checklist

### Before pushing to getdealtin.com:
- [ ] Get Census API key from api.census.gov/data/key_signup.html
- [ ] Replace DEMO_KEY in index.html (line search: "DEMO_KEY")
- [ ] Replace DEMO_KEY in homebuying.html (line search: "DEMO_KEY")
- [ ] Upload ben.png to your hosting root
- [ ] Upload dealt_cards.png to your hosting root  
- [ ] Upload Casino_Card_Table_Wood.png to your hosting root
- [ ] Test all navigation links
- [ ] Test Census data loads with real key
- [ ] Set up Google/Apple OAuth for profile saving

### How to deploy (simple static hosting):
The site is pure HTML/CSS/JS — no build step needed.
Upload index.html + homebuying.html + images to any static host:
- Netlify (drag and drop — recommended)
- Render static site
- GitHub Pages
- Vercel

### Legal / IP to discuss with lawyer:
- Trademark "Dealt" in fintech/consumer platform category
- Trademark the hand progression framework (High Card → Full House)
- Copyright the card table methodology as a proprietary framework
- GPO model licensing requirements by state
- Data consent language review

## Census API Key
Sign up free at: https://api.census.gov/data/key_signup.html
Takes ~24 hours to activate.
Replace both instances of DEMO_KEY in index.html and homebuying.html.

## Tools Still To Build
- Card Table (civic data visualization)
- OAuth (Google + Apple sign-in)
- User profile / progress tracker
- Subscription tier (Full House membership)
