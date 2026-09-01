<img src="assets/banner.jpg" width="880" alt="Marko Sabec — Rust Engineer. Solana, Trading Systems, Distributed Infrastructure. Trusted by Rain, MetaWealth and BT Group. 18+ years of experience. Open-source creator of QuantForge." />

<div align="center">

<h2>Hi, I'm Marko 👋</h2>

<p>
  <a href="https://www.linkedin.com/in/markosabec/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&labelColor=0b0b23" alt="LinkedIn" /></a>
  <a href="mailto:marko@sabec.si"><img src="https://img.shields.io/badge/Email-6C3EF5?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0b0b23" alt="Email" /></a>
  <a href="https://x.com/PiggySolGang"><img src="https://img.shields.io/badge/X-0b0b23?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
</p>

Rust engineer, 18+ years building backends — trading systems, Solana infrastructure and distributed services for **Rain**, **MetaWealth** and **BT Group**.

These days I build two things: **QuantForge**, a trading framework where a backtest gives you the same answer every single time you run it, and **Piggy Gang**, a Solana NFT ecosystem with a Rust indexer underneath. I like determinism, clean boundaries between the parts, and the shortest dependency list that does the job.

</div>

<hr/>

<h2 align="center">🦀 QuantForge</h2>

<div align="center">

<a href="https://github.com/quantforge-rs/quantforge"><img src="assets/quantforge-help.svg" width="840" alt="Terminal output of quantforge --help, listing the data, backtest, trade and monitor commands" /></a>

**A trading framework for Rust. Pull in market data, backtest a strategy, run it live — all from the terminal.**

<p>
  <a href="https://quantforge.rs"><img src="https://img.shields.io/badge/quantforge.rs-6C3EF5?style=for-the-badge&logo=rust&logoColor=white&labelColor=0b0b23" alt="quantforge.rs" /></a>
  <a href="https://github.com/quantforge-rs"><img src="https://img.shields.io/badge/quantforge--rs-181717?style=for-the-badge&logo=github&logoColor=white" alt="github.com/quantforge-rs" /></a>
</p>
<p>
  <img src="https://img.shields.io/crates/v/quantforge?style=for-the-badge&logo=rust&color=6C3EF5&labelColor=0b0b23" alt="Version 0.2.0" />
  <a href="https://docs.rs/quantforge"><img src="https://img.shields.io/docsrs/quantforge?style=for-the-badge&color=6C3EF5&labelColor=0b0b23&logo=docsdotrs&logoColor=white" alt="docs.rs" /></a>
  <a href="https://github.com/quantforge-rs/quantforge/blob/main/LICENSE"><img src="https://img.shields.io/crates/l/quantforge?style=for-the-badge&color=6C3EF5&labelColor=0b0b23" alt="License" /></a>
  <a href="https://github.com/quantforge-rs/quantforge"><img src="https://img.shields.io/github/stars/quantforge-rs/quantforge?style=for-the-badge&color=6C3EF5&labelColor=0b0b23&logo=github&logoColor=white" alt="Stars" /></a>
  <a href="https://github.com/quantforge-rs/quantforge/actions/workflows/ci.yml"><img src="https://github.com/quantforge-rs/quantforge/actions/workflows/ci.yml/badge.svg" alt="CI" /></a>
</p>

</div>

- **Dry-run can't trade, by construction.** It isn't a flag you might forget — in dry-run the engine has no exchange attached at all.
- **Backtests are reproducible.** The same data and settings give the same result every run. No clock, no randomness, no network.
- **No floating point for money.** Everything is decimal, because `f64` quietly loses cents.
- **It refuses the wrong resume.** Change the market, the strategy or the mode and it stops, so a paper position can never turn into a real one.
- **Built to be trusted with money.** No `unsafe`, no `unwrap()`, half the codebase is tests, CI on Linux, macOS and Windows.
- **Strategies don't have to be Rust.** The interface is plain data in and plain data out, so other languages can plug in.

<div align="center">

**[quantforge.rs](https://quantforge.rs)** · **[github.com/quantforge-rs](https://github.com/quantforge-rs)** · `cargo install quantforge`

<sub>Engineering software. Not investment advice, and no promise of profit.</sub>

</div>

<hr/>

<h2 align="center">🐷 Piggy Gang</h2>

<div align="center">

<img src="assets/piggy-sol-gang.png" width="240" alt="Piggy SOL Gang collection cover" />
<img src="assets/piggy-girl-gang.png" width="240" alt="Piggy Girl Gang collection cover" />
<img src="assets/piggy-token.png" width="180" alt="$PIGGY token logo" />

**Four NFT collections on Solana, a Rust indexer, and five web apps — all built in the open.**

<p>
  <a href="https://piggygang.net"><img src="https://img.shields.io/badge/piggygang.net-ff5fa2?style=for-the-badge&logo=vercel&logoColor=white&labelColor=0b0710" alt="piggygang.net" /></a>
  <a href="https://github.com/piggygang"><img src="https://img.shields.io/badge/piggygang-181717?style=for-the-badge&logo=github&logoColor=white" alt="github.com/piggygang" /></a>
  <a href="https://discord.gg/8SjGR8Srvz"><img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white&labelColor=0b0710" alt="Discord" /></a>
</p>
<p>
  <img src="https://img.shields.io/badge/Rust-0b0710?style=for-the-badge&logo=rust&logoColor=white" alt="Rust" />
  <img src="https://img.shields.io/badge/Solana-9945FF?style=for-the-badge&logo=solana&logoColor=white&labelColor=0b0710" alt="Solana" />
  <img src="https://img.shields.io/badge/Postgres%2017-4169E1?style=for-the-badge&logo=postgresql&logoColor=white&labelColor=0b0710" alt="Postgres 17" />
  <img src="https://img.shields.io/badge/Next.js-0b0710?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js" />
</p>

</div>

- **One spec runs the whole stack.** The indexer's OpenAPI file is the source of truth; the explorer generates its client from it, and CI fails if the two drift apart.
- **The frontend shipped before the backend.** It runs against a mock built from that same spec — one environment variable switches it to the real API.
- **The database enforces the rules.** A Postgres constraint makes it impossible for one NFT to have two owners at the same time.
- **Search is quick.** Filtering by traits across 10,000 NFTs comes back in about 35 ms.
- **Three dependencies talk to Solana.** No web3.js, no wallet-adapter. Keys never reach a server — the browser signs, the app just watches.
- **We kept the art.** The collections' original image host went dark; these repos hold what may be the only complete copy left.

| Repo | Lang | What it does | Live |
|---|---|---|---|
| [`indexer`](https://github.com/piggygang/indexer) | Rust | Indexes every Piggy NFT — traits, owners and full history — and serves them over a REST API | — |
| [`explorer`](https://github.com/piggygang/explorer) | TypeScript | Search the collections by trait, look up a wallet, read an NFT's history | [explorer.piggygang.net](https://explorer.piggygang.net) |
| [`dressme`](https://github.com/piggygang/dressme) | TypeScript | Dress your piggy up in any traits you like and download the picture | [dressme.piggygang.net](https://dressme.piggygang.net) |
| [`raffles`](https://github.com/piggygang/raffles) | TypeScript | Free raffles for holders — nobody ever pays to enter | [raffles.piggygang.net](https://raffles.piggygang.net) |
| [`alpha-art`](https://github.com/piggygang/alpha-art) | TypeScript | alpha.art coming back as an open-source Solana marketplace | [alpha.art](https://alpha.art) |
| [`website`](https://github.com/piggygang/website) | TypeScript | The hub — every app and collection in one place | [piggygang.net](https://piggygang.net) |

<div align="center">

**[piggygang.net](https://piggygang.net)** · **[github.com/piggygang](https://github.com/piggygang)**

<sub>Piggy SOL Gang (10,000) · Piggy Girl Gang (5,000) · Piggy Gang (10,000 — same piggies, meaner art) · Pig Mud (2,073) · $PIGGY</sub>

</div>

<hr/>

<h2 align="center">About me 🦀</h2>

<div align="center"><b>🌍 Slovenia — CET/CEST, <code>Europe/Ljubljana</code></b></div>

🔸 **Right now:** [QuantForge](https://github.com/quantforge-rs) — Binance and SQLite today, Bybit and Postgres next — and the [Piggy Gang](https://github.com/piggygang) stack.<br/>
🔸 **Good at:** backends that behave predictably — exact arithmetic, no look-ahead, and safety you can't switch off by accident.<br/>
🔸 **Solana:** Token Metadata and Core, Helius backfill and live streaming, wallets that sign in the browser and nowhere else.<br/>
🔸 **Infrastructure:** small hardened containers, one Dockerfile for a whole workspace, config kept as code.<br/>
🔸 **Ask me about:** why a backtest should be a pure function, and why changing an API contract is always two commits.

<hr/>

<h2 align="center">⚒️ Languages · Frameworks · Tools ⚒️</h2>

<div align="center">
  <img src="https://go-skill-icons.vercel.app/api/icons?i=rust,actix,solana,postgres,sqlite,redis,docker&perline=7" alt="Rust, Actix, Solana, Postgres, SQLite, Redis, Docker" />
  <br/>
  <img src="https://go-skill-icons.vercel.app/api/icons?i=typescript,nextjs,react,tailwind,githubactions,linux,grafana&perline=7" alt="TypeScript, Next.js, React, Tailwind, GitHub Actions, Linux, Grafana" />
</div>

<hr/>

<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)"  srcset="https://raw.githubusercontent.com/formaldehid/formaldehid/output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/formaldehid/formaldehid/output/github-snake.svg" />
  <img alt="Contribution graph being eaten by a snake" src="https://raw.githubusercontent.com/formaldehid/formaldehid/output/github-snake.svg" />
</picture>
</div>

<hr/>

<div align="center">
  <img src="https://streak-stats.demolab.com/?user=formaldehid&background=0b0b23&border=6C3EF5&stroke=6C3EF5&ring=7C3AED&fire=7C3AED&currStreakNum=ffffff&sideNums=ffffff&currStreakLabel=7C3AED&sideLabels=a5a3c0&dates=6f6c9e&disable_animations=true" alt="Contribution streak" />
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=formaldehid&theme=nord_dark" alt="Most-used languages by commit" />
</div>

<hr/>

<div align="center"><sub>More repos are being opened up as they stabilize.</sub></div>
