# CLAUDE.md — LifeLine Project

> Self-healing, self-improving project memory. Every Claude session must read this file FIRST and update it BEFORE ending.

---

## 1. Project Snapshot

- **Name:** LifeLine — Digital Blood Donor & Emergency Help Network
- **Owner:** Aditya (aditya100704@gmail.com)
- **Purpose:** College/campus emergency platform that connects verified student blood donors with people who need blood urgently. Built for a college project on the problem statement: *"Digital Blood Donor & Emergency Help Network (S/W)"*.
- **Stack right now:** Single-file static frontend (`index.html`) + Supabase backend (Postgres + REST API + Realtime).
- **Live URL:** https://aditya100704.github.io/lifeline-blood/
- **Repo:** https://github.com/Aditya100704/lifeline-blood
- **Backend (Supabase):**
  - Project URL: `https://melqnfeslokxmlcgoqhw.supabase.co`
  - Project ID: `melqnfeslokxmlcgoqhw`
  - Dashboard: https://supabase.com/dashboard/project/melqnfeslokxmlcgoqhw
  - Publishable key (safe in client): `sb_publishable_zxWxT9zSTrp8dXdALZYcBQ_mVCOkTtB`
  - DB password is in the owner's password manager (not stored here).
- **Tables:** `donors`, `emergency_requests`, `donation_responses` — RLS enabled, public read+insert policies, no public update/delete.

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

**Frontend**
- Sticky glass navbar with pulsing emergency button
- Hero with animated heartbeat card, floating blood drops, live counters
- Interactive blood compatibility tool (all 8 groups mapped correctly)
- How-it-works 3-step section
- Animated impact stats (real DB counts)
- Testimonials, FAQ accordion, footer with hotline
- Fully responsive (phone, tablet, laptop)
- Hosted free on GitHub Pages, auto-deploys on push to `main`

**Backend (Supabase)**
- Three tables live: `donors`, `emergency_requests`, `donation_responses`
- Row Level Security enabled on every table
- Public read + insert policies (no anonymous update/delete possible)
- 12 seed donors inserted across all 8 blood groups
- Realtime subscription on `donors` table — page updates without refresh when a new donor joins

**Wired End-to-End (verified by E2E test 2026-05-14)**
- Emergency request form → inserts into `emergency_requests`, success toast tells requester how many compatible verified donors got pinged
- Donor signup form → inserts into `donors`, page refreshes the donor list immediately
- Find-a-donor section → fetches real donors from DB, filter chips work
- Donor cards show WhatsApp button (deep-links to `wa.me`) + Call button (`tel:` link)
- Live counters in hero & impact section pull real `count(*)` from DB

---

## 4. What's NOT Done (Backlog)

Ordered by what would improve the product most:

1. **Real SMS / push notifications** — emergency requests reach the DB but nobody is actually texted yet. Need Twilio (SMS) or OneSignal (push) wired via a Supabase Edge Function.
2. **Auth / login for donors** — currently anyone can submit a donor profile under any name. Need email/phone OTP via Supabase Auth so only the real donor can update their own row.
3. **Donor ID verification flow** — admin needs to flip `is_verified` after manual check. Right now everyone is auto-verified.
4. **Admin dashboard** — moderate requests, verify donors, see analytics. Build a `/admin` route gated by Supabase Auth.
5. **Map view** — donors shown as cards only; a Leaflet/Mapbox map with pins would help locate nearby donors.
6. **Geo-radius matching** — currently no distance filter. Need `lat/lng` columns on donors + a haversine RPC in Postgres.
7. **Anti-spam rate limit** — anyone can spam emergency_requests. Add IP-based rate limit via Edge Function or a `requests_per_hour` check.
8. **Multi-language** — site is English only; Hindi/Hinglish would expand reach.
9. **PWA / offline** — add manifest + service worker so it installs like an app.
10. **Real photos / avatars** instead of initials.
11. **SEO + Open Graph tags** for sharing.
12. **90-day donation cooldown enforcement** — `last_donation_date` is in schema but never checked on availability.

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
| 2026-05-14 | Supabase over Firebase | Postgres > NoSQL for relational donor/request data; generous free tier; simpler SQL; built-in REST API; realtime included |
| 2026-05-14 | Use `sb_publishable_*` key in client | Newer Supabase publishable keys are designed for client-side use; safe when RLS is configured correctly |
| 2026-05-14 | Public INSERT policy on `emergency_requests` and `donors` | MVP needs zero-friction signup; trade-off is spam vulnerability. Documented in backlog item #7 |
| 2026-05-14 | Replaced en-dash (−) with hyphen (-) for blood groups | DB stored hyphens; keeping both formats would require normalization on every query |
| 2026-05-14 | WhatsApp + Call buttons on donor cards instead of generic "Request" | India context — WhatsApp is the default messenger. Direct deep links are faster than a chat system that needs auth |

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
| 2026-05-14 | Backend wired: Supabase project provisioned, 3 tables + RLS policies + seed data, frontend rewritten to use live DB, realtime donor updates, WhatsApp/Call deep links on cards. E2E tested live — emergency insert + donor signup both verified end-to-end. |

---

## 9. Healing Log

_Auto-fixes Claude made without being explicitly asked. Each entry: what was broken, how it was fixed, lesson learned._

| 2026-05-14 | Discovered DB used hyphens (`A-`) but frontend used en-dashes (`A−`) — filter chips wouldn't match. Fixed by normalizing the whole frontend to hyphens. Lesson: pick one Unicode form for canonical data early and stick to it. |
| 2026-05-14 | First OAuth authorize attempt (Supabase via GitHub) was denied — my JavaScript click triggered the wrong button. Fixed by retrying with a real coordinate-based click instead of dispatching events programmatically. Lesson: for OAuth flows, prefer real clicks over scripted ones; GitHub treats suspicious form submits as denials. |

---

## 10. Self-Improvement Notes for This File

After every session, ask: "Did this file actually help me work better today? What was missing? What was noise?" Edit accordingly.

Rules of thumb:
- **Section 5 (preferences)** is the highest-leverage section. Keep it sharp.
- If a section hasn't been useful in 3 sessions, prune it.
- If you find yourself re-discovering the same fact every session, write it down here.
- Keep this file under 300 lines forever. If it grows past that, it has become noise.
