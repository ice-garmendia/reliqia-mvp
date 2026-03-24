# Reliqia MVP — Release Notes

---

## Version 0.2.0
**Date:** 2026-03-24
**Type:** Interactive prototype (HTML · no backend)
**Live:** [ice-garmendia.github.io/reliqia-mvp](https://ice-garmendia.github.io/reliqia-mvp)

### What's new in 0.2.0

#### Explore — new dedicated discovery screen
- **Explore tab (🔍)** added to the bottom nav as the second item; replaces the search bar that was embedded in the Home (collection) screen
- **Default content when not searching:** Trending now (horizontal scroll of popular artists/formats), Recently listed (items with location and time since posting), Collectors near you (horizontal scroll of member cards)
- **Search with autocomplete:** filters catalog by artist, title and format from the first character; dropdown shows up to 6 results with item status badge; discovery content hides during search and reappears on clear

#### Item status — simplified taxonomy
- **"Open to trade or sell"** now replaces the previous two separate states ("Open to trade" and "Spare"); removes the need for collectors to distinguish between them at catalog time
- Updated across all screens: collection tabs, item picker, stats chips, privacy settings, search results badges and all item cards

#### Item location
- Every item card and popup now shows **"Item located in 📍 [city, country]"** so buyers and traders immediately know where the item ships from
- Applied across: collection list, swap match, wishlist alerts, reel feed cards, favorites, batch proposal item picker

#### Trust & escrow — My Orders screen
- **My Orders tab** in the collection screen shows active and completed transactions with status indicators
- **Order detail** shows the full escrow flow step by step: payment held → item shipped → delivery confirmed → funds released; based on the Stripe escrow model defined in the product spec

---

### Screens added in 0.2.0

| Screen | Description |
|---|---|
| **Explore** | Search + discovery: trending, recently listed, collectors nearby |
| **My Orders** | Active and completed transactions with escrow status tracker |
| **Order detail** | Step-by-step escrow flow for a single transaction |

---

## Version 0.1.0
**Date:** 2026-03-22
**Type:** Interactive prototype (HTML · no backend)
**Live:** [ice-garmendia.github.io/reliqia-mvp](https://ice-garmendia.github.io/reliqia-mvp)

---

## What this prototype covers

A navigable, mobile-first prototype of the Reliqia collector community platform. Built to validate core product concepts with real collectors before any backend development. All screens are clickable and interactive — no installation required, opens directly in the browser.

---

## Screens included

| Screen | Description |
|---|---|
| **Home** | Landing page with value proposition, 3 key differentiators and CTAs |
| **Sign up** | Registration with Google / Facebook or email form |
| **My collection** | Item list with status tabs, search, swap and alert banners |
| **Swap match** | AI-generated trade proposal between two members |
| **Build your offer** | Batch swap proposal builder |
| **Proposal summary** | Review screen before sending a proposal |
| **Reel feed** | Full-screen swipe feed with alerts and swap matches |
| **Alerts** | Unified notification inbox (swap matches + wishlist alerts) |
| **My profile** | Collector identity with stats, trades and collection preview |
| **Sign up** | Registration form with social login |
| **Privacy settings** | Granular control over what other members can see |
| **Public profile** | How other members see your profile |
| **Favorites** | Items saved from other collectors' collections |

---

## Changes by feature

### Collection & navigation
- **Home tab** — bottom navigation label standardized to "Home" across all screens
- **Wishlist tab** — added as a fifth tab in the collection screen alongside All / Intocable / Open to trade / Spare; shows items actively being searched with estimated market prices
- **Search with autocomplete** — search bar at the top of the collection screen; filters by artist, title and format from the first character; shows up to 6 results with item status badge; clear button (✕) to reset

### Alerts & feed
- **Unified alerts bell (🔔)** — replaced the Swaps tab in the bottom nav; single inbox combining swap matches, wishlist alerts and counteroffers; each type color-coded (gold = swap, blue = wishlist, green = counteroffer) with timestamps
- **Reel feed (🎬)** — full-screen vertical swipe feed; each card occupies the full viewport; swipe up/down with finger (mobile) or arrow keys (desktop); dot indicators on the right show current position; card types: ⚡ Wishlist alert · 🔄 Swap match · ↩️ Counteroffer
- **Sponsored card in feed** — monetization concept: one ad card appears between organic content cards, visually differentiated with a purple background and "Sponsored" badge; same immersive format as content cards

### Swap & trade
- **Batch swap proposal** — "Build your offer" screen allows bundling multiple items on each side of a trade; supports 1-to-1, 1-to-N and N-to-N formats
- **Cash complement** — each side of the proposal can include a cash amount in USD or EUR (e.g. "2 items + 30 USD for your item X")
- **Live balance calculator** — the proposal builder updates the total value of each side and the balance in real time as items and cash are added
- **Item picker** — bottom sheet overlay to select items from your open-to-trade and spare collections when building an offer
- **Proposal summary** — review screen before sending; shows all items, cash amounts, totals and a balance card with three states: ⚖️ Even swap · 📈 In your favor · 💡 You're offering less

### Authenticity score
- **Simplified label** — replaced technical "Auth score · X/100" with "X% verified · from seller photos" across all screens (swap match, wishlist alert, reel feed cards)
- **Tooltip** — tapping the ⓘ icon explains what the percentage means in plain language: "Based on the photos the seller uploaded, our system checked that the item matches what's described"

### Favorites
- **Heart button (❤️)** — on every item card; tap to save/unsave; active state in red
- **Follow counter** — each item shows how many members have it saved ("12 people follow this")
- **Favorites screen** — dedicated screen showing all saved items from other collectors' collections; accessible from the profile

### Profile & identity
- **Sign up screen** — Continue with Google / Continue with Facebook + manual form (username, email, country, what you collect, password)
- **My profile** — avatar, name, handle, location, reputation badge, 4 stats (items / trades / open to trade / member since), bio, collecting categories, recent trade history
- **Privacy settings** — 6 independent toggles: collection, wishlist, open to trade items, trade history, country, bio; email and password always private (locked)
- **Public profile** — exactly how another member sees your profile based on your privacy settings; includes "Propose a swap" and "Send message" CTAs

---

## Bug fixes
- **Navigation crash** — fixed infinite recursion caused by a duplicate `goTo()` function definition introduced when the batch swap proposal was added; merged into a single function

---

## What's not in this prototype

- Backend / database — all data is hardcoded for demonstration
- Real authentication — Google / Facebook / email login are visual only
- Real AI matching — swap matches and wishlist alerts are simulated
- Real payment / escrow — Stripe integration not included
- Push notifications — alerts are shown in-app only

---

## Next steps (roadmap)

1. Validate with real collectors using this prototype as conversation starter
2. Define backend stack and data model (collections, items, states, matches)
3. Integrate Stripe escrow for the first real transactions
4. Build AI matching engine for swap suggestions and wishlist alerts
5. iOS / Android app from the validated prototype

---

*Reliqia — built for collectors, by a collector.*
