# SubKit — Every subscription. One honest number.

Netflix, Spotify, Prime, ChatGPT — they all quietly renew. **SubKit** lines up every
subscription you pay for, works out what they really cost you a month, and tells you
which ones are worth keeping. One single self-contained HTML file — no backend, no
sign-up, everything saved on your device.

**Live:** https://abhiramunni.github.io/subkit/

## What it does

- **One honest monthly number** — monthly, quarterly and yearly plans are all converted
  to a single monthly figure, split fairly if flatmates share the bill. The hero card
  shows your monthly total, yearly total, next renewal and trials running, plus a ring
  showing how much of your monthly budget subscriptions eat.
- **Trials ending soon** — free trials that flip to paid within 7 days get a loud warning
  with the exact date and the price they become. One tap cancels the trial.
- **Renewal runway** — a 30-day timeline of everything renewing, soonest first, so no
  charge ever surprises you.
- **Your shelf** — every subscription as a membership card: price per billing cycle,
  your share, days left to renewal, and a cost-per-use figure. Tap **+ / −** to set how
  often you really use it; the verdict badge reads *Great value*, *Fair value* or
  *Rethink this one*. **Mark renewed** bumps the date by exactly one billing cycle.
- **Keep it, or cancel it?** — subscriptions ranked worst value first by cost per use,
  with the saving shown next to each one.
- **What-if simulator** — switch subscriptions off and watch the monthly and yearly
  saving add up live. Nothing is deleted until you say so.
- **Where the money goes** — an SVG donut of monthly spend by category (Video, Music,
  Cloud, AI tools, …).
- **Quick add** — tap a popular service (Netflix, Prime, JioHotstar, Spotify, YouTube
  Premium, iCloud+, Google One, ChatGPT Plus, Canva Pro, Apple TV+) to add it with its
  typical November 2026 price, then edit the price and renewal date to match your bill.
- **6 plain-language guides** — free-trial reminders, annual vs monthly, family plans,
  the ₹/use test, how to actually cancel, and one-in-one-out.
- **On-device only** — add / edit / delete subscriptions, copy a plain-text summary,
  remove the sample subscriptions, or erase everything (two taps). A 3-step onboarding
  tour runs on first visit, and a short cinematic intro plays once (tap to skip).

## Sample data (removable)

The shelf ships with 8 clearly-marked sample subscriptions totalling **₹2,828/month**
(₹33,935/year): Netflix ₹649/mo split 3 ways, Spotify ₹119/mo, YouTube Premium ₹139/mo,
Amazon Prime ₹1,499/yr, Google One ₹130/mo, ChatGPT Plus ₹1,999/mo (₹80/use — the
app's clearest "Rethink this one"), Apple TV+ on a free trial ending 22 Nov 2026, and
JioHotstar ₹299/quarter. Tap **Remove sample subscriptions** to start from an empty shelf.

## How the maths works

- **Monthly equivalent** = price ÷ people splitting ÷ months in the billing cycle
  (monthly 1, quarterly 3, yearly 12). A free trial counts as ₹0 until its end date.
- **Cost per use** = your monthly share ÷ times you use it in a month.
  ≤ ₹15/use is *Great value*, ≤ ₹50 is *Fair value*, above ₹50 is *Rethink this one*.
- **Renewal dates** use your device's local calendar — no timezone shifts.

## Tech

- Single `index.html` (~500 KB, two AI-generated warm-editorial photos embedded as
  base64, Ken Burns drift). Fraunces + Inter from Google Fonts; everything else is
  hand-written CSS/JS with inline SVG icons — no frameworks, no trackers.
- State lives in `localStorage` under `subkit-v1`. Nothing is sent anywhere.
- QA: 70/70 headless jsdom assertions, `node --check` clean, zero uncaught JS errors.

## Run it locally

Open `index.html` in any modern browser — no server needed.
