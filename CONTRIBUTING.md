# Contributing to Awesome-llm-tts

Thanks for helping keep this list accurate. This repo has strict honesty rules — please read them before opening a PR.

## What belongs here

- LLM-era text-to-speech: open neural TTS models, streaming/real-time engines, commercial TTS APIs, toolkits/frameworks, voice conversion, benchmarks and evals, TTS datasets.
- ASR-only projects are out of scope (except toolkits that do both, e.g., sherpa-onnx). Music generation and general audio generation are out of scope.

## Entry requirements (all must hold)

1. **Real and verifiable.** The project must exist at the linked URL. `verified` is `true` only if you confirmed the entry on an official source (the project's repo or official site) — never from a blog roundup alone.
2. **Honest license.** Copy the SPDX identifier from the project's actual LICENSE file. Proprietary APIs are `"proprietary"` — never imply a paid API is open source. If the license can't be confirmed, set `"license": null`, `"verified": false`, and explain in `"unverified_reason"`.
3. **No invented facts.** No guessed star counts, WER numbers, or prices. If you can't verify it, leave it `null` and say why.
4. **One category each.** Pick the single best-fitting `category`.

## How to add an entry

1. Add the entry to `data/tts.json` (keep the file's existing ordering: grouped by category):
   ```json
   {
     "name": "Example TTS",
     "description": "One-line description, no hype.",
     "license": "Apache-2.0",
     "category": "foundation-models",
     "repo": "https://github.com/org/example-tts",
     "homepage": "https://github.com/org/example-tts",
     "official_site": null,
     "stars": 1234,
     "verified": true,
     "unverified_reason": null
   }
   ```
   Use `null` (not `""`) for unknown `repo`/`official_site`/`stars`/`unverified_reason`.
2. Add the matching bullet to the right section in `README.md`: `- [Example TTS](https://github.com/org/example-tts) — one-line description.`
3. Run the CI validation locally if you can (`python` 3.12+, see `.github/workflows/ci.yml`): it checks JSON validity, duplicate names/URLs, the README↔JSON cross-check, section counts, and TOC anchors.
4. Open a PR describing what you verified and where (link the official source).

## Link hygiene

- Prefer `https://` URLs; no URL shorteners.
- If a project renamed/moved, update to the canonical URL and note it in `docs/status-changes.md`.
- Commercial API links should point at official docs or pricing pages, not marketing landing pages, where possible.

## What gets rejected

- Entries with invented licenses, stars, or benchmark numbers.
- Proprietary products presented as open source.
- TTS-only tools, dead links, or projects you can't confirm exist.
