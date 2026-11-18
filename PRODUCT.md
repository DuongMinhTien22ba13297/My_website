# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

- **Primary — people Tiến sends the link to directly:** friends, acquaintances, and anyone who needs to pay him or reach him quickly. They open the link mid-conversation on a phone with a concrete intent: transfer money, or start a chat.
- **Public personal presence:** a wider audience (classmates, community) who land on the page as his public-facing personal identity.
- **Personal/friends use:** Tiến himself and close friends using it as a personal page.

## Product Purpose

A single-page personal link-and-transfer hub: it makes it possible to send money to Dương Minh Tiến (VietQR / BIDV) or start a conversation (Zalo, Telegram, Facebook, email) within seconds, while expressing who he is.

Success means: a visitor completes a payment or sends a message with zero friction, and leaves with a sense of who Tiến is.

## Positioning

Everything a contact needs to reach or pay him lives on one Vietnamese page that opens straight onto his social channels — Zalo, Telegram, Facebook, email — with the transfer QR one tap away behind the sticky tab, never buried. A neighboring link-aggregator page could not truthfully claim the same "arrive, tap, done" immediacy combined with a personal identity and a scan-ready VietQR.

## Operating Context

- Static front-end only: `index.html` plus `assets/`, no build step, no backend, no database. Opened directly (`file://`) or via static hosting.
- Visitors arrive predominantly on phones; the layout is built mobile-first.
- Zalo and Telegram are the practical messaging channels for this audience; bank transfer goes through Vietnamese banking apps that scan VietQR.
- Repo also holds one-off Python asset-prep scripts (QR cropping, audio extraction) and a `tasks/lessons.md` engineering log; these are working material, not product surface.

## Capabilities and Constraints

**Confirmed functionality (as shipped in `index.html`):**

- Sticky three-tab switcher: **Mạng Xã Hội** (default on load, owner decision 2026-11-16), **Chuyển Khoản**, **Giới Thiệu**.
- Banking tab: VietQR image display, copy account number, download QR image, transfer-detail table.
- Social tab: Zalo / Telegram / Facebook / email cards with QR viewer, open-chat links, copy-to-clipboard with toast confirmation.
- About tab: profile facts (name, birthday, zodiac sign, email).
- Header music player: play/pause, mute, thin in-flow seek bar. Music OFF by default on load; starts only via the play button.
- Share button, QR modal, ripple/tab-transition effects.

**Constraints:**

- No build tooling: Tailwind CDN, inline `<style>`/`<script>`, single file.
- **Vietnamese-only visitor-facing copy** (confirmed binding).
- **The background music player must remain** (confirmed binding). Music is OFF by default on page load and plays only through the explicit play control (owner decision 2026-11-16, superseding the earlier gesture-autoplay behavior). The seek bar sits in normal flow, 3px thin, never overlaying other content.
- Banking and social details are factual content already present in the code. They are real data, not confirmed as immutable: do not change, replace, or invent them without asking.
- Deploy target / hosting: undecided.

## Brand Commitments

- Name: **Dương Minh Tiến**; monogram "DT" with "TIẾN" sub-label; verified "chính chủ" badge.
- Voice: personal, warm, direct, Vietnamese.
- Confirmed track: **"Đã Lỡ Yêu Em Nhiều" — JustaTee** as the page's background music.
- Visual direction (owner-confirmed 2026-11-16): the **paper / airmail-envelope world** produced by the unslop run — warm paper ramp (#f7f4ee / #fdfbf7 / #efe9df), ink text, Be Vietnam Pro + IBM Plex Mono, the VietQR as a perforated postage stamp on an airmail envelope with an ink postmark. The owner explicitly rejected reverting to the old sky-blue glassmorphism look; do not switch visual worlds again without an explicit request. The round red "DT" seal was removed by owner decision 2026-11-16 and must not return (header, favicon, share cover).

## Evidence on Hand

- `index.html` — the incumbent implementation and the source of all visitor-facing copy and features.
- `index.backup.html` — gitignored safety copy of an earlier version.
- `assets/qr_bidv.jpg`, `assets/qr_zalo.png`, `assets/qr_telegram.png` — real QR images.
- `assets/da_lo_yeu_em_nhieu.mp3` (+ `.webm`) — the licensed-by-user background track.
- `tasks/lessons.md` — engineering lessons (autoplay policy, sticky header/tab fixes, CORS on `file://`, QR cropping).
- `design_references/`, `Screenshot*.png`, `My Documents [...].zip` — gitignored working material.

**Absences future work must not fabricate:** no testimonials, no customers, no press, no case studies, no benchmarks, no analytics, no standalone logo asset (the monogram is live text), no `DESIGN.md`.

## Product Principles

1. **Contact first, payment one tap away.** The social tab is the default view (owner decision 2026-11-16); the transfer path stays one tap behind the sticky tab and remains the fastest route inside it — never bury it deeper.
2. **One page, zero friction.** A visitor finishes their job — pay or message — without leaving the page or waiting on it.
3. **Real only.** Every fact shown is verifiable and present in this repo; no invented proof, claims, or social proof.
4. **Vietnamese-first.** All visitor-facing copy is Vietnamese.
5. **Personality stays.** The page should say who Tiến is, not merely list links.
