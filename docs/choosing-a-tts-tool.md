# Choosing a TTS Tool

A decision guide for picking text-to-speech in the LLM era. Last reviewed 2026-10-01.

## Start with your constraints

1. **Live or batch?** If audio must start while the user is still interacting (voice agents, live dubbing), you need a streaming architecture — see [Streaming & Real-Time TTS](../README.md#streaming--real-time-tts). Batch models (plain Bark, Tortoise) add seconds of latency before the first chunk.
2. **Budget: $0 or usage-based?** Hosted APIs ([Commercial TTS APIs](../README.md#commercial-tts-apis)) win on time-to-value; open models ([Neural TTS Models](../README.md#neural-tts-models)) win on marginal cost and data control.
3. **Whose voice?** Stock voices are easy. Cloning a specific voice raises consent and legal questions — see the ethics note below — and the best zero-shot cloners (XTTS v2, CosyVoice, Chatterbox, OpenVoice) differ sharply in license terms.
4. **Which languages?** Multilingual coverage varies wildly: check the model's supported-language list, not the marketing page. For low-resource languages, [TTS Datasets](../README.md#tts-datasets) like Emilia and WenetSpeech matter more than any single model.
5. **Where does the text live?** Regulated or private text points to self-hosted open models; sending text to an API is a data-flow decision, not just a cost one.

## Latency vs. quality vs. cost

- **Best open quality (batch):** the frontier moves fast — check the [TTS Arena v2](https://huggingface.co/spaces/TTS-AGI/TTS-Arena-V2) human-preference Elo rather than trusting release hype.
- **Lowest latency:** purpose-built streaming models (Orpheus-TTS, Qwen3-TTS, MOSS-TTS) or streaming-first APIs (Cartesia Sonic, Deepgram Aura, ElevenLabs).
- **Cheapest at scale:** self-hosted open model on your own GPUs; hosted APIs charge per character/audio-minute and the crossover favors self-hosting quickly at volume.
- **Best on-device:** small-footprint engines (Piper, KittenTTS, MeloTTS) run on CPU with no network.

## Open vs. API: the honest trade-offs

| | Open models | Hosted APIs |
|---|---|---|
| Data control | Text/audio never leaves your infra | Text sent to vendor |
| Cost shape | Fixed GPU cost, ~$0 marginal | Per-character/minute, scales linearly |
| Customization | Fine-tune, swap vocoders, control prosody | Limited to vendor options |
| Ops burden | You serve, scale, monitor | Vendor handles it |
| Voice cloning | DIY, license-dependent | Usually bundled, consent-gated |

## Licensing traps (read before you ship)

- **Research/non-commercial weights** (Fish Speech's "FISH AUDIO RESEARCH LICENSE AGREEMENT", IndexTTS's bilibili Model Use License with its 100M-MAU / RMB 1B revenue clause, VoiceCraft's CC BY-NC-SA + Coqui Public Model License): free to experiment, not free to ship commercially. Read the actual text.
- **Coqui Public Model License 1.0.0** (XTTS v2 weights, VoiceCraft models): non-commercial. The code around them (MPL-2.0) does not relicense the weights.
- **Llama-derived weights** (Orpheus-TTS, OuteTTS): code is Apache-2.0, but weights fine-tuned from Llama 3.2 inherit the Llama Community License in practice.
- **AGPL-3.0 / GPL-3.0** (ChatTTS, MARS5-TTS, Piper's maintained fork): network/service use counts as distribution — strong copyleft. Note Piper's fork changed the license from the original's MIT to GPL-3.0.
- **CC-BY-NC-4.0 datasets** (Emilia): research-only. Training a commercial model on them is a license violation, not a gray area.
- **ODC-BY-1.0** (VCTK): attribution required; commonly mislabeled as CC-BY-4.0 in third-party docs.

## Voice-cloning ethics (non-negotiable)

Clone only voices you own or have explicit consent to reproduce. Several entries in this list (Resemble AI, ElevenLabs, Respeecher) gate cloning behind consent verification — that is a feature, not friction. Impersonation without consent is fraud in most jurisdictions, and several model licenses explicitly prohibit deceptive use.

## Multilingual notes

- English-first models often degrade on tonal or low-resource languages; check per-language samples, not aggregate MOS.
- AISHELL-3 (Mandarin, multi-speaker) and WenetSpeech (Mandarin, CC-BY-4.0 with gated non-commercial terms) are the standard open Mandarin TTS corpora; MLS covers 8 European languages at LibriTTS quality.
