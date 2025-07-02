# Airbnb Auto Reviewer 🐚

**Hands-free guest reviews in under 5 seconds.**  
A Tampermonkey userscript (and Chrome-extension starter kit) that clicks through Airbnb’s 7-step host-review wizard, leaves 5-star ratings, selects “what went well” tags, and fills public + private notes with your reusable templates. You manually press **Submit** at the end.

---

## Features

| Step | What the script does |
|------|----------------------|
| 1    | Waits for you to hit **Get started**. |
| 2-4  | Sets ⭐⭐⭐⭐⭐ for Cleanliness, House Rules, Communication & optionally selects the first 3 compliment chips. |
| 5    | Prefills a public review template, inserting the guest’s first name. |
| 6    | Clicks **Yes** to recommend the guest. |
| 7    | Prefills a private note template, then stops so you can proof-read and click **Submit**. |
| Everywhere | Skips hidden elements, dismisses Airbnb’s “Are you sure you want to leave?” overlay, waits for each **Next** button to enable. |

---

## Quick Start (Tampermonkey)

1. **Install Tampermonkey** for Chrome/Edge/Firefox.  
2. Click **_Create a new script…_** → paste `airbnb-auto-reviewer.user.js` → **Save**.  
3. Open any review page  
   `https://www.airbnb.com/hosting/reviews/<id>/edit`  
   and press **Get started**.  
4. Watch the wizard complete itself; press **Submit** on step 7.

---

## Configuration

Edit the top of the userscript to tune:

```js
const CHIPS_TO_SELECT = 3;      // 0-3 “what went well” tags
const HUMAN_DELAY     = 400;    // ms between major clicks
const PUBLIC_TEMPLATE  = name => `${name} was a great guest! …`;
const PRIVATE_TEMPLATE = name => `Thanks ${name} for supporting …`;
