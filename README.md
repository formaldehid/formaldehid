<img src="assets/banner.jpg" width="880" alt="Marko Sabec — Rust Engineer. Solana, Trading Systems, Distributed Infrastructure. Trusted by Rain, MetaWealth and BT Group. 18+ years of experience. Open-source creator of QuantForge." />

<div align="center">

<h2>Hi, I'm Marko 👋</h2>

<p>
  <a href="https://www.linkedin.com/in/markosabec/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&labelColor=0b0b23" alt="LinkedIn" /></a>
  <a href="mailto:marko@sabec.si"><img src="https://img.shields.io/badge/Email-6C3EF5?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0b0b23" alt="Email" /></a>
  <a href="https://crates.io/crates/quantforge"><img src="https://img.shields.io/badge/crates.io-6C3EF5?style=for-the-badge&logo=rust&logoColor=white&labelColor=0b0b23" alt="crates.io" /></a>
  <a href="https://piggygang.net"><img src="https://img.shields.io/badge/piggygang.net-ff5fa2?style=for-the-badge&logo=vercel&logoColor=white&labelColor=0b0b23" alt="piggygang.net" /></a>
  <a href="https://x.com/PiggySolGang"><img src="https://img.shields.io/badge/X-0b0b23?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
</p>

Rust engineer, 18+ years shipping production backends — trading systems, Solana infrastructure and distributed services — for teams including **Rain**, **MetaWealth** and **BT Group**. Creator of **QuantForge**, a deterministic CLI-first trading framework in Rust: `#![forbid(unsafe_code)]`, zero `unwrap()` in src *and* tests across ~10.6k lines of which roughly half are tests, decimal-only arithmetic with no `f64` anywhere, and a dry-run mode that is structural rather than a flag — the engine is constructed without a trading venue, so it physically cannot reach an order endpoint. Currently building the **Piggy Gang** stack: a Rust NFT indexer on actix-web and Postgres 17 behind a frozen OpenAPI 3.1 contract, plus five Next.js apps that ship green against that contract. I optimize for determinism, contract-first boundaries and the smallest dependency tree that can do the job — the wallet-facing apps reach Solana without `@solana/web3.js` or the wallet-adapter tree.

</div>

<hr/>

<h2 align="center">🦀 QuantForge</h2>

<div align="center">

<a href="https://github.com/quantforge-rs/quantforge"><img src="assets/quantforge-help.svg" width="840" alt="Terminal output of quantforge --help, listing the data, backtest, trade and monitor commands" /></a>

**Deterministic CLI-first market data ingestion, backtesting and controlled live trading in Rust. There is no UI — the CLI is the product.**

<p>
  <a href="https://crates.io/crates/quantforge"><img src="https://img.shields.io/crates/v/quantforge?style=for-the-badge&logo=rust&color=6C3EF5&labelColor=0b0b23" alt="crates.io version" /></a>
  <a href="https://docs.rs/quantforge"><img src="https://img.shields.io/docsrs/quantforge?style=for-the-badge&color=6C3EF5&labelColor=0b0b23&logo=docsdotrs&logoColor=white" alt="docs.rs" /></a>
  <a href="https://github.com/quantforge-rs/quantforge/blob/main/LICENSE"><img src="https://img.shields.io/crates/l/quantforge?style=for-the-badge&color=6C3EF5&labelColor=0b0b23" alt="License" /></a>
  <img src="https://img.shields.io/badge/MSRV-1.85-6C3EF5?style=for-the-badge&logo=rust&logoColor=white&labelColor=0b0b23" alt="MSRV 1.85" />
  <img src="https://img.shields.io/badge/edition-2024-7C3AED?style=for-the-badge&logo=rust&logoColor=white&labelColor=0b0b23" alt="Rust edition 2024" />
</p>
<p>
  <a href="https://github.com/quantforge-rs/quantforge"><img src="https://img.shields.io/github/stars/quantforge-rs/quantforge?style=for-the-badge&color=6C3EF5&labelColor=0b0b23&logo=github&logoColor=white" alt="Stars" /></a>
  <a href="https://github.com/quantforge-rs/quantforge/commits/main"><img src="https://img.shields.io/github/last-commit/quantforge-rs/quantforge?style=for-the-badge&color=7C3AED&labelColor=0b0b23&logo=git&logoColor=white" alt="Last commit" /></a>
  <a href="https://github.com/quantforge-rs/quantforge/actions/workflows/ci.yml"><img src="https://github.com/quantforge-rs/quantforge/actions/workflows/ci.yml/badge.svg" alt="CI" /></a>
  <a href="https://github.com/quantforge-rs/quantforge/actions/workflows/gitleaks.yml"><img src="https://github.com/quantforge-rs/quantforge/actions/workflows/gitleaks.yml/badge.svg?branch=main" alt="gitleaks" /></a>
</p>

</div>

- **Dry-run is structural, not a flag.** In dry-run the engine is constructed with `None` as its `TradingVenue` — there is no code path to an order endpoint. Live requires `--mode live`, a typed confirmation and credentials from the environment, and production Binance hosts are marked `(PRODUCTION)` in both the prompt and the logs.
- **A backtest is a pure function of (config, candles, strategy)** — no clock, no RNG, no I/O, repeat runs bit-identical. Strategies see closed bars only, and intent fills at the *next* bar's open: the no-look-ahead rail.
- **Decimal arithmetic, no `f64` anywhere.** SQLite stores decimals as `TEXT`; "optimizing" that column to `REAL` silently corrupts PnL. `Option<Decimal>` means *the exchange did not report* — never a fabricated zero.
- **Resume-identity checks refuse to resume** when market, strategy, params or mode differ, so a dry-run position can never leak into live trading.
- **`#![forbid(unsafe_code)]`, zero `unwrap()` in src and tests**, a 3-OS CI matrix run `--locked`, CodeQL, full-history gitleaks scanning, 16 byte-locked CLI help snapshots, and a hand-written mock Binance server for a fully offline end-to-end tier.
- **The `Strategy` trait is deliberately FFI-friendly** — object-safe, no generics, plain data in and out, never calls back into the engine — so foreign-language strategies are a design target, not an afterthought.

<div align="center">

**→ [github.com/quantforge-rs/quantforge](https://github.com/quantforge-rs/quantforge)** · `cargo install quantforge`

<sub>Engineering software. Not investment advice, does not recommend trades, does not promise profitability.</sub>

</div>

<hr/>

<h2 align="center">🐷 Piggy Gang</h2>

<div align="center">

<img src="assets/piggy-sol-gang.png" width="240" alt="Piggy SOL Gang collection cover" />
<img src="assets/piggy-girl-gang.png" width="240" alt="Piggy Girl Gang collection cover" />
<img src="assets/piggy-token.png" width="180" alt="$PIGGY token logo" />

**A Solana NFT ecosystem: four collections, a Rust indexer, and five Next.js apps behind one frozen contract.**

<p>
  <a href="https://github.com/piggygang/indexer"><img src="https://img.shields.io/badge/Rust-0b0710?style=for-the-badge&logo=rust&logoColor=white" alt="Rust" /></a>
  <img src="https://img.shields.io/badge/Solana-9945FF?style=for-the-badge&logo=solana&logoColor=white&labelColor=0b0710" alt="Solana" />
  <img src="https://img.shields.io/badge/Postgres%2017-4169E1?style=for-the-badge&logo=postgresql&logoColor=white&labelColor=0b0710" alt="Postgres 17" />
  <img src="https://img.shields.io/badge/Next.js-0b0710?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <a href="https://piggygang.net"><img src="https://img.shields.io/badge/piggygang.net-ff5fa2?style=for-the-badge&logo=vercel&logoColor=white&labelColor=0b0710" alt="piggygang.net" /></a>
  <a href="https://discord.gg/8SjGR8Srvz"><img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white&labelColor=0b0710" alt="Discord" /></a>
</p>

</div>

- **Contract-first across repo boundaries.** The indexer's frozen `openapi/v1.yaml` (OpenAPI 3.1, 11 operations) is the contract of record; the explorer vendors it, generates its typed client from it, and CI fails the build on drift between spec and committed types. A contract change is always two commits — indexer first, then `pnpm sync:spec`.
- **The frontend ships and deploys green before its backend exists** — the explorer runs against a compile-checked in-process mock served through the same generated client, with a Prism container as the spec-faithful second opinion. One env var flips it to the real API.
- **Ownership correctness is enforced by the database, not by application code.** A GiST `EXCLUDE` constraint on `ownership_history` makes two open ownership intervals for one asset structurally impossible. Keyset cursors throughout, never offset; weak `ETag` + `If-None-Match` → `304`.
- **Facet queries benchmark at p50 ≤ 40 ms** against a < 100 ms acceptance target — three active trait types over 10k assets at 33 ms, text search at 5 ms — on synthetic Piggy-scale data, with the scaling model written down rather than assumed.
- **Radical dependency minimalism as a security posture.** DressMe and Raffles reach Solana through `@wallet-standard/app` alone — no `@solana/web3.js`, no wallet-adapter tree, no Buffer polyfill in the bundle. No user key or user-signed transaction ever touches a server: the browser builds, the wallet signs and broadcasts, the app only watches the signature.
- **Trust boundaries drawn on purpose.** DressMe asks the RPC only *which* tokens a wallet holds, never what they are — traits and rarity always come from committed files. Raffles was re-scoped to free-entry after review against Slovenia's Games of Chance Act, with three named invariants: no consideration ever, published rules per raffle enforced by a required `rules_uri`, and 18+ with prize taxes.
- **Digital preservation.** The collections' original art host `shdw-drive.genesysgo.net` no longer resolves; this org holds what may be the only surviving copy of the official art, re-hosted to R2 and Vercel Blob.

| Repo | Lang | What it is | Live |
|---|---|---|---|
| [`indexer`](https://github.com/piggygang/indexer) | Rust | NFT indexer + REST API — DAS backfill and live streaming into attributes, owners and full transaction history; registry-driven, so any collection can be added later | — |
| [`explorer`](https://github.com/piggygang/explorer) | TypeScript | Public explorer — faceted attribute search, owner lookup, per-NFT transaction history | [explorer.piggygang.net](https://explorer.piggygang.net) |
| [`dressme`](https://github.com/piggygang/dressme) | TypeScript | Dress-up app — holders customize their collectible with layered traits and download the result | [dressme.piggygang.net](https://dressme.piggygang.net) |
| [`raffles`](https://github.com/piggygang/raffles) | TypeScript | Free raffles for holders of the three Piggy collections — nobody ever pays to enter | [raffles.piggygang.net](https://raffles.piggygang.net) |
| [`alpha-art`](https://github.com/piggygang/alpha-art) | TypeScript | alpha.art returning as an open-source Solana NFT exchange | [alpha.art](https://alpha.art) |
| [`website`](https://github.com/piggygang/website) | TypeScript | The hub — apps and art for the whole gang, start anywhere | [piggygang.net](https://piggygang.net) |

<div align="center">

**→ [github.com/piggygang](https://github.com/piggygang)**

<sub>Piggy SOL Gang (10,000, Metaplex Token Metadata) · Piggy Girl Gang (5,000) · Piggy Gang (10,000, Metaplex Core — same piggies, meaner art) · Pig Mud (2,073) · $PIGGY</sub>

</div>

<hr/>

<h2 align="center">About me 🦀</h2>

<div align="center"><b>🌍 Slovenia — CET/CEST, <code>Europe/Ljubljana</code></b></div>

🔸 **Currently maintaining:** [QuantForge](https://github.com/quantforge-rs/quantforge) — deterministic, CLI-first trading systems framework in Rust. Binance Spot and SQLite today; Bybit, restart reconciliation, Postgres and parameter sweeps on the roadmap.<br/>
🔸 **Currently building:** the [Piggy Gang](https://github.com/piggygang) stack — a Rust indexer on actix-web + sqlx + Postgres 17, and five Next.js apps behind one frozen OpenAPI contract.<br/>
🔸 **Specialty:** deterministic backends — decimal-only arithmetic, no-look-ahead execution, structural safety rails, and tests that are half the codebase rather than an afterthought.<br/>
🔸 **Blockchain:** Solana — Metaplex Token Metadata and Metaplex Core, Helius DAS backfill and live streaming, Wallet Standard in the browser with no key ever leaving it.<br/>
🔸 **Infrastructure:** rustls everywhere so no `libssl` reaches the runtime image, multi-stage `cargo-chef` builds onto `debian:bookworm-slim` running non-root, one Dockerfile that builds any workspace binary via `ARG BIN`, project config as code.<br/>
🔸 **Ask me about:** why a backtest must be a pure function, why `Option<Decimal>` beats a zero, why the RPC should never be asked what you own, and why a contract change is always two commits.

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
