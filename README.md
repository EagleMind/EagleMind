# Hi, I'm Hassen Ben Mbarek (@EagleMind) And these are my personal for fun made projects.


---

## Projects


### [tokenbud](https://github.com/EagleMind/tokenbud) — lend your AI, keep your keys
Share your local model or paid API access with friends or a class using a 9-digit ID and a password. No key changes hands, and one click ends it.
- Seats and an hourly prompt reserve you control; sharing pauses itself when the budget runs out
- Works behind any router through a Cloudflare Worker relay (one Durable Object per host); you can self-host the relay in minutes
- Ollama, LM Studio, or your own key for Anthropic, OpenAI, Gemini, Mistral, Groq and more
- Guests need nothing installed (web client), and `tokenbud mcp` lets another agent prompt a shared one
- Relay stores only hashes; same answer for an unknown ID or a wrong password, so IDs can't be probed

`Rust` `Tauri 2` `React` `Cloudflare Workers` `Durable Objects` `MCP`


### [swarmproof](https://github.com/EagleMind/swarmproof) — prove a BitTorrent swarm is actually alive
Seeder counts are numbers nobody checks. swarmproof asks a real peer for the torrent's metadata and verifies its SHA1 against the infohash.
- Four verdicts (`verified`, `reachable`, `claimed`, `none`) so a working torrent is never written off and a dead one never gets a green badge
- Ranking across mirrors that doubles as a failover order
- A BEP 51 DHT crawler with a content filter in front of the index
- Usable as an HTTP service or a Node library; `npm run prove-it` demos it against the live network in ~15 seconds

`Node.js` `BitTorrent DHT` `SQLite` `Cloudflare Workers` `Durable Objects`


### [intelQ](https://github.com/EagleMind/intelQ) — query your database in plain English
A desktop client for MySQL, PostgreSQL and SQLite. Ask a question in English, review the generated SQL, then run it.
- Read-only lock on by default; any write or DDL needs explicit confirmation
- `@table` tags send only the relevant schema to the model, keeping prompts small on large databases
- Runs fully local with LM Studio, or through OpenRouter; credentials live in the OS keychain
- Schema annotations that can be written back as native PostgreSQL/MySQL comments

`Tauri 2` `Rust` `sqlx` `React 19` `TypeScript`


### [QueryLens](https://github.com/EagleMind/querylens) — find the database problems in what your app actually sends
Records every statement your ORM generates while you use the app or run its tests, then tells you what to fix, in your ORM's terms, with the file and line that issued it.
- Detects N+1s, writes in a loop, missing indexes, unbounded results and swallowed errors
- Re-plans captured queries with their real values and tests candidate indexes with HypoPG before recommending them, then hands you the migration
- A CI gate (GitHub Action + baseline) that fails a PR only on *new* problems
- A plan workbench for PostgreSQL, MySQL, MongoDB and DuckDB, with time per operator and every profile run read-only or rolled back
- An MCP server so coding agents can capture, compare and test fixes themselves

`Rust` `Tauri 2` `React 19` `PostgreSQL` `MCP`

### [flarecraft](https://github.com/EagleMind/flarecraft) — a topology tool for Cloudflare Workers
Open a folder and your whole Workers architecture is mapped onto a canvas; design a new one and it's scaffolded to disk.
- Reverse lookups the dashboard doesn't have: which Workers produce to and consume from a queue
- Every element configured in place from Cloudflare's own field reference, linted continuously
- Drift detection against the live account and deploys planned in dependency order
- Read-only MCP server so a coding agent can ask `who_binds` and `lint_topology`
- 180 unit tests, plus an emitter check that runs `wrangler deploy --dry-run` on every generated Worker

`TypeScript` `React Flow` `Hono` `Cloudflare Workers` `MCP`

### [scopekit](https://github.com/EagleMind/scopekit) — scoped, enforced context for AI coding assistants
Gives each module a short brief, derives ownership and dependencies from the real import graph, and uses a PreToolUse hook to make the assistant load that context *before* it edits anything.
- Context stays flat as the codebase grows: about 1.2k tokens versus 43k for a full dump in the benchmark (36×)
- Every invariant is anchored to a real symbol; `scopekit-cli verify` fails CI when a brief goes stale
- Two-command setup: `npm i -D scopekit-cli && npx scopekit-cli init`

`TypeScript` `MCP` `Claude Code hooks` `npm`


### [zlp-api](https://github.com/EagleMind/zlp-api) — Zebra labels without hand-writing ZPL
A fluent, typed API for designing Zebra printer labels in inches or millimetres instead of counting dots.
- DPI-aware conversion, 37+ ZPL commands, 10+ barcode types (Code 128, QR, Data Matrix, EAN, UPC…)
- Instant browser preview through Labelary
- Published on npm as [`zpl-fluent-api`](https://www.npmjs.com/package/zpl-fluent-api)

`TypeScript` `npm`


---

## What I work with

**Languages:** TypeScript, JavaScript, Rust
**Frontend & desktop:** React, Vite, Tailwind CSS, Tauri
**Backend & infra:** Node.js, Hono, Cloudflare Workers / KV / Durable Objects, PostgreSQL, MySQL, MongoDB, DuckDB, SQLite
**AI tooling:** MCP servers, Claude Code hooks, LM Studio, Ollama, OpenRouter

---

## Get in touch
- **Email:** hassen.ben.mbarek@gmail.com
