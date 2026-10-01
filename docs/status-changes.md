# Status Changes

Renames, shutdowns, archival notices, and license gotchas affecting this list. Last reviewed 2026-10-01.

## Shutdowns and deaths

- **Play.ht / PlayAI** — platform shut down 2025-12-31 after a Meta acqui-hire (2025-07-12). Excluded.
- **LMNT** — shut down; lmnt.com renders a shutdown notice as of 2026-10-01. Excluded.
- **Coqui (company)** — shut down January 2025. The `coqui-ai/TTS` repo is community-maintained; commits are rare and the XTTS weights line is frozen. Listed with this caveat.
- **Papercup** — IP acquired by RWS (June 2025). Excluded as an independent product.
- **stepfun-ai/Step-Audio** — carries a "no longer maintained" notice. Excluded.
- **rhasspy/piper** — archived October 2025. The maintained successor is `OHF-Voice/piper1-gpl` (listed); note the license changed from MIT to GPL-3.0.
- **Replica Studios** — shut down 2025-06-30 (MultiLingual); site offline. Removed from the live list 2026-10-01.

## Renames and org moves

- **CosyVoice** — FunAudioLLM org moved to **QwenAudio** (`FunAudioLLM/CosyVoice` → `QwenAudio/CosyVoice`); one repo now covers CosyVoice 1.0/2.0/3.0.
- **Parler-TTS** — moved from `descriptinc` to the `huggingface` org; maintained by Hugging Face.
- **FireRedTTS** — the active line is **FireRedTTS3** (`FireRedTeam/FireRedTTS3`); v1 (`FireRedTeam/FireRedTTS`) is stale.
- **Rime** — flagship model rebranded to "Coda" (~2026-09); entry describes the platform generically to resist drift.

## Post-publish link fixes (2026-10-01, CI run 36902917604)

- **TTSDS** — ttsdsbenchmark.com unresolvable from multiple networks; entry now links the live project repo `ttsds/ttsds`.
- **VERSA** — repo moved `shinjiwlab/versa` → `wavlab-speech/versa`.
- **CereProc** — acquired by Capacity (Jul 2024); entry now links the current "CereProc by Capacity" product page.
- Canonical URL updates from CI-observed redirects: ReadSpeaker, Azure AI Speech, IBM Watson TTS, VCTK, NaturalReader (http→https), MiniMax Audio, PaddleSpeech.
- Lychee exclusion added: `lovo.ai` (serves 402 to automated traffic; site is live for browsers).

## Stale but listed (functional research/product artifacts)

Bark, Zonos, Spark-TTS, StyleTTS 2, Tortoise-TTS, MARS5-TTS, MetaVoice-1B, MeloTTS, Kokoro — no commits for 14–26 months, but complete and functional. Kept with this caveat; they graduate to the exclusions table if archived.

## License gotchas

- Fish Speech: verbatim "FISH AUDIO RESEARCH LICENSE AGREEMENT" — research/non-commercial free; commercial use needs a separate Fish Audio license.
- IndexTTS: verbatim "bilibili Model Use License Agreement" — entities over 100M MAU or RMB 1B annual revenue need a separate license.
- XTTS v2 weights: Coqui Public Model License 1.0.0 (non-commercial); the surrounding code is MPL-2.0.
- VoiceCraft: CC BY-NC-SA 4.0 (code) + Coqui Public Model License 1.0.0 (weights).
- Orpheus-TTS / OuteTTS: Apache-2.0 code, but weights fine-tuned from Llama 3.2 inherit the Llama Community License in practice.
- Piper fork (OHF-Voice/piper1-gpl): GPL-3.0, changed from the original's MIT.
- Emilia dataset: CC-BY-NC-4.0 (research-only). WenetSpeech: CC-BY-4.0 with gated non-commercial terms. GigaSpeech: repo tagged Apache-2.0 but audio access gated to non-commercial research/educational use. VCTK: ODC-BY-1.0 (commonly mislabeled CC-BY-4.0).
- ChatTTS and MARS5-TTS: AGPL-3.0 — strong copyleft for network-service use.
