# Reliqia MVP — Partner Brief
**Date:** 2026-03-24
**Live:** [ice-garmendia.github.io/reliqia-mvp](https://ice-garmendia.github.io/reliqia-mvp)

---

## What it is

An interactive prototype of Reliqia — a global collector community powered by AI. No installation required. Opens directly in the browser, works on mobile and desktop. No backend, no real auth, no real payments — built to validate core product concepts with real collectors before any engineering investment.

---

## What's built

13 navigable screens covering the full active-collector flow — from discovering items to closing a trade with payment guarantee.

### Screens

| Screen | What it shows |
|---|---|
| **Home** | Collector's own catalog with tabs: All · Intocable · Open to trade or sell · Wishlist · My Orders |
| **Explore** | Search with autocomplete + default discovery content: Trending, Recently listed, Collectors nearby |
| **Swap match** | AI-generated trade proposal between two members |
| **Build your offer** | Batch swap builder — bundle multiple items per side + cash complement in USD or EUR |
| **Proposal summary** | Review before sending — items, cash, totals and balance state (Even / In your favor / You're offering less) |
| **Reel feed** | Full-screen vertical swipe feed — wishlist alerts, swap matches, counteroffers, sponsored card |
| **Alerts** | Unified inbox — color-coded by type (gold = swap, blue = wishlist, green = counteroffer) |
| **My Orders** | Active and completed transactions with escrow status tracker |
| **Order detail** | Step-by-step escrow flow: payment held → item shipped → delivery confirmed → funds released |
| **Sign up** | Google / Facebook or manual registration |
| **My profile** | Avatar, stats, bio, collecting categories, trade history |
| **Privacy settings** | 6 independent toggles for what other members can see |
| **Public profile** | Exactly how another member sees you — with "Propose a swap" and "Send message" CTAs |
| **Favorites** | Items saved from other collectors' collections |

---

## Key product decisions visible in the prototype

- **"Open to trade or sell"** — single unified item state replacing the previous split between "Open to trade" and "Spare"; removes friction at catalog time
- **Authenticity score** — simplified to "88% verified · from seller photos" with an explanatory tooltip; no technical jargon
- **Item location on every card** — "Item located in 📍 Madrid, Spain" — buyers and traders know shipping origin before engaging
- **Batch swap with cash complement** — 1-to-1, 1-to-N and N-to-N trades; live balance calculator updates in real time
- **Escrow model** — based on Stripe; payment held until buyer confirms receipt; foundation for trust at scale
- **Monetization concept** — sponsored card in the reel feed, same immersive format as organic content

---

## What's intentionally not here

| Not built | Why |
|---|---|
| Backend / database | All data is hardcoded for demo |
| Real authentication | Google / Facebook / email login are visual only |
| Real AI matching | Swap matches and alerts are simulated |
| Real payment / escrow | Stripe flow is a visual prototype |
| Push notifications | Alerts are shown in-app only |

---

## Where we are — 90-day plan

1. **Now** — validate with real collectors using this prototype as conversation starter
2. **Next** — define backend stack and data model (collections, items, states, matches)
3. **Then** — first real transactions with Stripe escrow
4. **Roadmap** — AI matching engine · iOS / Android app

---

*Reliqia — built for collectors, by a collector.*
