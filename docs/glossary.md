# TTS Glossary

Terms you'll meet in text-to-speech, in one place. Last reviewed 2026-10-01.

- **TTS (text-to-speech)** — synthesis of spoken audio from text.
- **Neural TTS** — TTS built on neural networks (as opposed to concatenative or formant synthesis).
- **Autoregressive (AR) TTS** — generates audio token-by-token (e.g. VALL-E, Bark, Tortoise); high quality, higher latency.
- **Non-autoregressive (NAR) TTS** — generates audio in parallel (e.g. FastSpeech family, Matcha-TTS, E2-style flow models); faster, historically slightly lower prosody quality.
- **Zero-shot voice cloning** — reproducing a voice from a short reference clip with no fine-tuning (XTTS, CosyVoice, Chatterbox).
- **Speaker prompt / reference audio** — the short clip a zero-shot model copies the voice from.
- **Vocoder** — the component that turns acoustic features (mel-spectrograms, latent codes) into waveform audio (HiFi-GAN, BigVGAN).
- **Acoustic model** — the component that turns text/phonemes into acoustic features.
- **Codec language model** — TTS framed as language modeling over discrete audio tokens (VALL-E lineage).
- **Streaming TTS** — synthesis that emits audio chunks before the full text is processed; measured by time-to-first-audio.
- **RTF (real-time factor)** — synthesis time divided by audio duration; < 1.0 means faster than real time.
- **MOS (mean opinion score)** — human naturalness rating, typically 1–5. The gold standard, expensive to collect.
- **UTMOS / NISQA / DNSMOS** — neural MOS *predictors*: models that estimate MOS without human listeners.
- **SIM (speaker similarity)** — how close a cloned voice is to the reference, usually measured with speaker-embedding cosine similarity.
- **WER on synthesized speech** — intelligibility check: run the output through an ASR model and measure word error rate.
- **Diarization** — not TTS, but adjacent: labeling "who spoke when" in audio.
- **VC (voice conversion)** — changing the voice of existing speech (speech-to-speech), distinct from TTS (text-to-speech).
- **RVC** — Retrieval-based Voice Conversion, the popular open VC pipeline.
- **Fine-tuning / voice design** — adapting a TTS model to a new voice (fine-tuning) or describing one in words (voice design).
- **SSML** — Speech Synthesis Markup Language: XML for controlling pronunciation, pauses, and prosody in API calls.
- **Phonemization / G2P** — converting written words to phonemes before synthesis; a common failure point for names and jargon.
