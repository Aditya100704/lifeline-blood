# CLAUDE.md — LifeLine Project

> Self-healing, self-improving project memory. Every Claude session must read this file FIRST and update it BEFORE ending.

---

## 1. Project Snapshot

- **Name:** LifeLine — Digital Blood Donor & Emergency Help Network
- **Owner:** Aditya (aditya100704@gmail.com)
- **Purpose:** College/campus emergency platform that connects verified student blood donors with people who need blood urgently. Built for a college project on the problem statement: *"Digital Blood Donor & Emergency Help Network (S/W)"*.
- **Stack right now:** Single-file static website (`index.html`) — pure HTML/CSS/JS, no backend yet.
- **Live URL:** _to be filled after deployment_
- **Repo:** _to be filled after GitHub push_

---

## 2. File Map

| File | Role |
|---|---|
| `index.html` | Entire website — markup, styles, and scripts all in one file |
| `CLAUDE.md` | This file. Project memory + self-improvement log |
| `README.md` | Public-facing project description for GitHub |

If new files get added, Claude must update this table.

---

## 3. What's Done

- Sticky glass navbar with pulsing emergency button
- Hero with animated heartbeat card, floating blood drops, live counters
- Emergency request form (front-end only — submissions show a toast, do not persist)
- Find-a-donor section with 12 dummy donors, blood-group filter chips, verified badges
- Interactive blood compatibility tool (all 8 groups mapped correctly)
- How-it-works 3-step section
- Animated impact stats
- Become-a-donor form (front-end only)
- Testimonials, FAQ accordion, footer with hotline
- Fully responsive (phone, tablet, laptop)

---

## 4. What's NOT Done (Backlog)

Ordered by what would improve the product most:

1. **Real backend** — donor signups + emergency requests currently vanish on refresh. Options discussed: Google Forms + Sheets (fastest), Supabase (recommended for real product), Firebase.
2. **Donor matching logic** — right now filter is by exact blood group, not by compatibility chart. Should match recipients to compatible donors automatically.
3. **Notifications** — when emergency request submitted, no real SMS/push goes out.
4. **Auth / login** — no user accounts yet.
5. **Map view** — donors shown as cards only; a map with pins would help locate nearby donors.
6. **Admin dashboard** — no way to verify donor IDs, moderate requests, or see analytics.
7. **Multi-language** — site is English only; Hindi/Hinglish would expand reach.
8. **PWA / offline** — add manifest + service worker so it installs like an app.
9. **Real photos / avatars** instead of initials.
10. **SEO + Open Graph tags** for sharing.

---

## 5. Owner Preferences (learned over sessions)

- **Communication style:** plain English, short and crisp, NO code jargon when explaining things. User said this explicitly.
- **Design taste:** likes premium / animated / "alive" feeling websites. Dark theme + red accents worked well here.
- **Decision-making:** prefers to be given 2-3 concrete options with a recommendation, not exhaustive lists.
- **Working environment:** Windows 11, project lives at `C:\Users\adity\OneDrive\Desktop\shruti`, primary browser is Chrome with GitHub already logged in.
- **Skill level on coding:** treats Claude as the builder — wants outcomes, not implementation details.

---

## 6. Important Decisions Made

| Date | Decision | Why |
|---|---|---|
| 2026-05-14 | Single-file HTML/CSS/JS instead of React/Next.js | User wanted instant preview, zero setup, runs anywhere |
| 2026-05-14 | Dark theme with red accents | Conveys urgency + trust, premium feel |
| 2026-05-14 | All forms front-end only at first | Faster to ship a working demo; backend is a separate decision |

---

## 7. Self-Healing Protocol

Every Claude session MUST follow this loop:

### At the START of every session:
1. **Read this entire file.**
2. **Verify the file map** — run `Glob *` in the project root; if files exist that aren't listed in Section 2, add them. If files listed are missing, flag it.
3. **Check if `index.html` still opens without errors** — open it mentally; look for broken script tags, unclosed elements, missing closing brackets.
4. **Read Section 5 (preferences)** — calibrate tone, response length, and recommendations to match.

### DURING the session:
- If the user corrects your approach → add it to Section 5 (Owner Preferences).
- If the user makes a major product decision → add a row to Section 6.
- If you complete a backlog item → move it from Section 4 to Section 3.
- If something breaks and you fix it → log it under Section 9 (Healing Log).

### At the END of every session:
1. **Update Section 3** (What's Done) and **Section 4** (Backlog) to reflect current state.
2. **Add an entry to Section 8** (Session Log) — one line: date + what shipped.
3. **Add to Section 9** (Healing Log) if you found and fixed any issue without being asked.
4. **Re-read this whole file once** to make sure it's still coherent and free of contradictions. Edit out anything stale.
5. **Suggest one improvement to this file itself.** Self-improvement: the file should get sharper, shorter, and more useful every session.

---

## 8. Session Log

| Date | Summary |
|---|---|
| 2026-05-14 | Initial build — full single-file site shipped. CLAUDE.md created. GitHub Pages deploy initiated. |

---

## 9. Healing Log

_Auto-fixes Claude made without being explicitly asked. Each entry: what was broken, how it was fixed, lesson learned._

_(empty — first session)_

---

## 10. Self-Improvement Notes for This File

After every session, ask: "Did this file actually help me work better today? What was missing? What was noise?" Edit accordingly.

Rules of thumb:
- **Section 5 (preferences)** is the highest-leverage section. Keep it sharp.
- If a section hasn't been useful in 3 sessions, prune it.
- If you find yourself re-discovering the same fact every session, write it down here.
- Keep this file under 300 lines forever. If it grows past that, it has become noise.
