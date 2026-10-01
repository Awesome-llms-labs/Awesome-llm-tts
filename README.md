# Awesome LLM TTS

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Entries](https://img.shields.io/badge/entries-83-blue)](data/tts.json)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A curated list of **LLM-era text-to-speech** (speech synthesis): open neural TTS models, streaming/real-time engines, commercial TTS APIs, training toolkits, voice conversion, evaluation benchmarks, and TTS datasets.

> **Scope:** text-to-speech only. ASR/speech-to-text lives in the sibling [Awesome-llm-asr](https://github.com/Awesome-llms-labs/Awesome-llm-asr). Music generation and general audio generation are separate subdomains.
> **Honesty policy:** every entry was verified on an official source (project repo, LICENSE file, or official site) as of 2026-10-01 — **83/83 verified**. Proprietary APIs and models are explicitly labeled and never presented as open source. Non-commercial and research-only licenses (CC-BY-NC-*, custom research agreements) are flagged with their exact terms in the entry itself — never softened. Machine-readable data lives in [`data/tts.json`](data/tts.json).

## Contents

- [Neural TTS Models](#neural-tts-models) — 23 entries
- [Streaming & Real-Time TTS](#streaming--real-time-tts) — 7 entries
- [Commercial TTS APIs](#commercial-tts-apis) — 25 entries
- [Toolkits & Frameworks](#toolkits--frameworks) — 8 entries
- [Voice Conversion](#voice-conversion) — 3 entries
- [Benchmarks & Evals](#benchmarks--evals) — 6 entries
- [TTS Datasets](#tts-datasets) — 11 entries

## Choosing the right TTS

New here? Start with the [choosing-a-tts-tool](docs/choosing-a-tts-tool.md) guide (streaming vs. batch, open vs. API, licensing traps, voice-cloning ethics), the [glossary](docs/glossary.md), and [status-changes](docs/status-changes.md) (renames, archival notices, license gotchas).

## Neural TTS Models

Open and open-weight neural speech-synthesis models — the checkpoints and code behind modern TTS. (23 entries)

- [VALL-E](https://github.com/lifeiteng/vall-e) — Unofficial PyTorch reimplementation of Microsoft's VALL-E zero-shot TTS model, which frames text-to-speech as conditional language modeling over discrete neural audio codec codes. *(Apache-2.0 · ⭐ 2,220)*
- [Bark](https://github.com/suno-ai/bark) — Text-prompted generative audio model from Suno that synthesizes realistic multilingual speech from short prompts; the upstream repo has seen no commits since August 2024. *(MIT · ⭐ 39,274)*
- [Tortoise-TTS](https://github.com/neonbjb/tortoise-tts) — Multi-voice text-to-speech system trained with an emphasis on quality, supporting voice cloning from reference audio. *(Apache-2.0 · ⭐ 14,880)*
- [XTTS v2](https://github.com/coqui-ai/TTS) — Multilingual zero-shot voice-cloning TTS model shipped in the Coqui TTS toolkit, with streaming inference support; Coqui shut down in 2024 and the XTTS model weights remain under the non-commercial Coqui Public Model License. *(MPL-2.0 (code) / Coqui Public Model License 1.0.0 (model weights) · ⭐ 46,097)*
- [CosyVoice](https://github.com/QwenAudio/CosyVoice) — Multilingual zero-shot TTS model family from Alibaba's FunAudioLLM team (single repo now covers 1.0/2.0/3.0) with text-in/audio-out bi-streaming at about 150ms latency. *(Apache-2.0 · ⭐ 23,820)*
- [F5-TTS](https://github.com/SWivid/F5-TTS) — Flow-matching non-autoregressive TTS that synthesizes faithful speech from text plus a short reference clip, with official streaming variants. *(MIT · ⭐ 15,316)*
- [ChatTTS](https://github.com/2noise/ChatTTS) — Generative speech model optimized for conversational dialogue, with fine-grained control over laughter, pauses, and intonation. *(AGPL-3.0 · ⭐ 39,889)*
- [Fish Speech](https://github.com/fishaudio/fish-speech) — Open-weight multilingual TTS series from Fish Audio; research and non-commercial use is free while commercial use requires a separate license. *(FISH AUDIO RESEARCH LICENSE AGREEMENT (research/non-commercial use free; commercial use requires a separate license) · ⭐ 32,916)*
- [Kokoro](https://github.com/hexgrad/kokoro) — 82M-parameter TTS model that runs fast on CPU, supports streaming synthesis, and ships with dozens of voices. *(Apache-2.0 · ⭐ 9,105)*
- [Parler-TTS](https://github.com/huggingface/parler-tts) — Text-description-guided TTS library maintained by Hugging Face, where natural-language style descriptions steer the synthesized voice. *(Apache-2.0 · ⭐ 5,591)*
- [StyleTTS 2](https://github.com/yl4579/StyleTTS2) — Zero-shot voice-cloning TTS combining style diffusion with adversarial training on large speech language models. *(MIT · ⭐ 6,363)*
- [MetaVoice-1B](https://github.com/metavoiceio/metavoice-src) — 1.2B-parameter English TTS base model trained on 100K hours of speech, released under Apache 2.0 by MetaVoice. *(Apache-2.0 · ⭐ 4,205)*
- [Zonos](https://github.com/Zyphra/Zonos) — Open-weight multilingual zero-shot TTS model from Zyphra trained on over 200K hours of varied speech; the repo has seen no commits since March 2025. *(Apache-2.0 · ⭐ 7,234)*
- [Spark-TTS](https://github.com/SparkAudio/Spark-TTS) — LLM-based TTS using BiCodec tokens for coarse- and fine-grained voice control, supporting zero-shot voice cloning and voice creation. *(Apache-2.0 · ⭐ 10,996)*
- [Dia](https://github.com/nari-labs/dia) — 1.6B-parameter dialogue TTS model that generates ultra-realistic two-speaker conversations in a single pass. *(Apache-2.0 · ⭐ 19,393)*
- [IndexTTS](https://github.com/index-tts/index-tts) — Industrial-level controllable zero-shot TTS from Bilibili's IndexTeam with emotion, pronunciation, and speaking-speed control; model use is governed by the bilibili Model Use License Agreement. *(bilibili Model Use License Agreement · ⭐ 24,258)*
- [VoiceCraft](https://github.com/jasonppy/VoiceCraft) — Token-infilling neural codec language model for zero-shot TTS and speech editing; both code and model weights are non-commercial. *(CC BY-NC-SA 4.0 (code) / Coqui Public Model License 1.0.0 (model weights) · ⭐ 8,576)*
- [MaskGCT](https://github.com/open-mmlab/Amphion/blob/main/models/tts/maskgct/README.md) — Fully non-autoregressive zero-shot TTS using masked generative codec transformers, released inside the Amphion toolkit. *(MIT · ⭐ 10,304)*
- [FireRedTTS 3](https://github.com/FireRedTeam/FireRedTTS3) — Multilingual LLM-empowered foundation TTS from Xiaohongshu's FireRed team with instruction-guided voice design and semantic plus acoustic speech editing. *(Apache-2.0 · ⭐ 1,762)*
- [OuteTTS](https://github.com/edwko/OuteTTS) — Lightweight multilingual TTS interface with 0.5B/1B open models; the 1B variant is fine-tuned from Llama 3.2, so the Llama Community License also applies to those weights. *(Apache-2.0 · ⭐ 1,440)*
- [Sesame CSM](https://github.com/SesameAILabs/csm) — Conversational Speech Model from Sesame that generates RVQ audio tokens for natural dialogue speech. *(Apache-2.0 · ⭐ 14,729)*
- [Chatterbox](https://github.com/resemble-ai/chatterbox) — Open-source TTS from Resemble AI with emotion exaggeration control and multilingual zero-shot voice cloning. *(MIT · ⭐ 26,638)*
- [MARS5-TTS](https://github.com/Camb-ai/MARS5-TTS) — English TTS model from CAMB.AI with deep zero-shot voice cloning; last updated August 2024. *(AGPL-3.0 · ⭐ 2,822)*
## Streaming & Real-Time TTS

Models and engines built for low-latency, streaming synthesis — the stack voice agents run on. (7 entries)

- [Orpheus-TTS](https://github.com/canopyai/Orpheus-TTS) — Llama-based speech LLM for emotive TTS with roughly 200ms real-time streaming latency and emotion tags; the weights inherit the Llama 3.2 Community License via the base model. *(Apache-2.0 · ⭐ 6,346)*
- [Qwen3-TTS](https://github.com/QwenLM/Qwen3-TTS) — Open-source streaming TTS series from Alibaba's Qwen team supporting voice cloning, voice design, and low-latency generation. *(Apache-2.0 · ⭐ 13,607)*
- [MOSS-TTS](https://github.com/OpenMOSS/MOSS-TTS) — Open-source model family from the OpenMOSS team for long-form speech, dialogue synthesis, voice design, and real-time streaming TTS. *(Apache-2.0 · ⭐ 4,154)*
- [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) — On-device speech runtime built on ONNX with streaming-capable TTS for mobile and embedded targets, requiring no internet connection. *(Apache-2.0 · ⭐ 15,070)*
- [KittenTTS](https://github.com/KittenML/KittenTTS) — Sub-25MB TTS model that synthesizes speech in real time on CPU. *(Apache-2.0 · ⭐ 15,492)*
- [MeloTTS](https://github.com/myshell-ai/MeloTTS) — High-quality multilingual TTS library (English, Spanish, French, Chinese, Japanese, Korean) that runs in real time on CPU. *(MIT · ⭐ 7,650)*
- [Piper](https://github.com/OHF-Voice/piper1-gpl) — Fast local neural TTS engine running ONNX voices in many languages; the maintained Open Home Foundation fork (OHF-Voice/piper1-gpl) of the archived MIT original, widely used for on-device voice synthesis. *(GPL-3.0 · ⭐ 5,738)*
## Commercial TTS APIs

Hosted text-to-speech APIs and platforms. All proprietary with usage-based pricing — listed for completeness, never as open source. (25 entries)

- [ElevenLabs](https://elevenlabs.io/) — AI voice platform with multilingual text-to-speech, voice cloning, and AI dubbing across a library of expressive voices and Eleven v3 / Turbo-class models. *(proprietary)*
- [OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech) — OpenAI's text-to-speech API offering tts-1, tts-1-hd, and the steerable gpt-4o-mini-tts model with instructions-based voice control and real-time streaming. *(proprietary)*
- [Cartesia](https://docs.cartesia.ai) — Real-time voice AI platform built around the Sonic family of ultra-low-latency text-to-speech models (REST, SSE, and WebSocket), covering 40+ languages with voice cloning. *(proprietary)*
- [Deepgram Aura](https://deepgram.com/aura) — Deepgram's low-latency Aura-2 text-to-speech voices on the /v1/speak endpoint, designed for real-time conversational AI and voice agents. *(proprietary)*
- [Resemble AI](https://www.resemble.ai/) — Enterprise voice-cloning and TTS platform (Rapid and Professional cloning, streaming APIs) with the Resemble Detect deepfake-detection product; note its Chatterbox TTS model was open-sourced (MIT) but the platform itself is proprietary. *(proprietary)*
- [Murf](https://murf.ai/) — AI voiceover studio (murf.ai) with the Falcon engine, 200+ voices across 35 languages, aimed at creators, presentations, and video dubbing. *(proprietary)*
- [WellSaid Labs](https://docs.wellsaidlabs.com/reference/getting-started-with-your-api) — Studio-quality AI voice avatars for enterprise voiceover production (200+ avatars, AI Director pronunciation control) behind a documented REST API. *(proprietary)*
- [Lovo](https://lovo.ai/) — Genny AI voice platform (lovo.ai) offering 500+ realistic voices, voice cloning, and a developer API for voiceover generation. *(proprietary)*
- [Hume AI Octave](https://dev.hume.ai/docs/text-to-speech-tts/overview) — Hume AI's Octave text-to-speech — an LLM-driven expressive TTS model with dynamic emotional prosody across 11 languages. *(proprietary)*
- [Rime](https://docs.rime.ai/docs/introduction) — Real-time TTS API with sub-100ms latency, hundreds of voices, and voice cloning for conversational AI and voice agents. *(proprietary)*
- [MiniMax Audio](https://platform.minimax.io) — MiniMax's audio platform (platform.minimax.io) with the speech-2.5 TTS model covering 50+ languages, voice cloning, and streaming synthesis. *(proprietary)*
- [Descript Overdub](https://www.descript.com/blog/article/overdub-on-all-plans) — Descript's own-voice-only voice cloning built into its text-based audio/video editor — generate new speech by typing in your own cloned voice. *(proprietary)*
- [Speechify](https://speechify.com/blog/text-speech-app-for-windows/) — Leading consumer text-to-speech app (mobile, web, Chrome) with 1000+ natural voices in 60+ languages for listening to documents and articles; Speechify also advertises a SIMBA TTS API per its own 2026 blog. *(proprietary)*
- [ReadSpeaker](https://www.readspeaker.com/solutions/speech-production/readspeaker-speechcloud-api/) — Long-running TTS provider for web accessibility and enterprise: webReader/docReader embeds, TextAid, and the speechCloud REST API with 245 voices in 68 languages. *(proprietary)*
- [Acapela Group](https://www.acapela-group.com/voices/available-languages/) — European TTS company offering 30+ languages, characterful and child voices, expressive voice smileys, and accessibility/custom voice services. *(proprietary)*
- [CereProc](https://www.cereproc.com) — Edinburgh speech synthesis company with characterful regional-accents voices; CereVoice Cloud API plus the on-device CereWave AI neural engine. *(proprietary)*
- [Replica Studios](https://www.replicastudios.com/) — Ethical AI voice-actor platform for games and film: licensed actor voices, expressive character TTS, and a live game API (notable SAG-AFTRA agreement). *(proprietary)*
- [Respeecher](https://www.respeecher.com/) — High-fidelity voice cloning and TTS for film/TV advertising (used for young Luke Skywalker in The Mandalorian); exposes a Voice Marketplace API and a real-time streaming TTS API. *(proprietary)*
- [Amazon Polly](https://aws.amazon.com/polly/) — AWS cloud text-to-speech with generative, neural, and standard engines — 100+ voices across 41 languages with deep AWS integration. *(proprietary)*
- [Google Cloud TTS](https://cloud.google.com/text-to-speech) — Google Cloud's neural TTS API with hundreds of WaveNet/Chirp voices, SSML support, and streaming synthesis for real-time use. *(proprietary)*
- [Azure AI Speech](https://azure.microsoft.com/en-us/products/ai-services/ai-speech) — Microsoft's Azure AI Speech text-to-speech: 400+ neural voices, custom voice training, SSML prosody control, and a streaming Text Stream API. *(proprietary)*
- [IBM Watson TTS](https://cloud.ibm.com/apidocs/text-to-speech) — IBM's Watson Text-to-Speech on IBM Cloud — REST and WebSocket synthesis with SSML, custom prompts, and speaker models (release notes current to v5.3.1, 2026-02-27). *(proprietary)*
- [Voicemaker](https://voicemaker.in) — Web TTS platform with 1000+ voices in 130+ languages, SSML/pronunciation controls, voice cloning, and a REST API for developers. *(proprietary)*
- [NaturalReader](http://www.naturalreaders.com/webapp.html) — TTS reader app (web, mobile, Chrome) with 1000+ AI voices for personal listening and a separate commercial AI Voice Generator for voiceover work. *(proprietary)*
- [Dubverse](https://dubverse.ai/blog/6-reasons-why-youtubers-should-create-multilingual-content/) — AI video-dubbing and localization platform with standalone TTS voiceovers (SAY, 500+ voices), voice cloning, and a developer TTS API; team joined Exotel in April 2026 while the product continues independently. *(proprietary)*
## Toolkits & Frameworks

Training and inference toolkits for building TTS systems, from research recipes to production runtimes. (8 entries)

- [Coqui TTS](https://github.com/coqui-ai/TTS) — Community-maintained deep-learning TTS library with 100+ pretrained models (Tacotron, VITS, XTTS, Bark); the company Coqui shut down in January 2025 and commits are rare. *(MPL-2.0 · ⭐ 46,097)*
- [ESPnet](https://espnet.github.io/espnet/) — End-to-end speech processing toolkit with actively maintained TTS recipes (VITS, FastSpeech 2, Tacotron 2) and pretrained models. *(Apache-2.0 · ⭐ 9,976)*
- [NVIDIA NeMo](https://docs.nvidia.com/nemo/speech/nightly/index.html) — Conversational-AI toolkit with TTS modules (FastPitch, FastSpeech 2, Matcha, VITS) and LLM-era speech pipelines. *(Apache-2.0 · ⭐ 18,537)*
- [PaddleSpeech](https://paddlespeech.readthedocs.io) — PaddlePaddle-based speech toolkit with TTS models (FastSpeech 2, Tacotron 2, VITS) and streaming inference support. *(Apache-2.0 · ⭐ 12,690)*
- [Matcha-TTS](https://shivammehta25.github.io/Matcha-TTS/) — Fast, memory-efficient TTS acoustic model using optimal-transport conditional flow matching, with reference code from its authors. *(MIT · ⭐ 1,362)*
- [VITS](https://jaywalnut310.github.io/vits-demo/index.html) — Official reference implementation of VITS (conditional VAE with adversarial learning); stable with no commits since December 2023. *(MIT · ⭐ 7,894)*
- [Mimic 3](https://github.com/MycroftAI/mimic3) — Fast, local, offline neural TTS system (VITS-based) from Mycroft AI; repo is quiet since March 2025 after the company wound down. *(AGPL-3.0 · ⭐ 1,264)*
- [WEST](https://github.com/wenet-e2e/west) — LLM-based speech toolkit (understanding, generation, interaction) from the WeNet team, with TouchTTS recipes on LibriTTS and a C++ streaming runtime; young project (2025). *(Apache-2.0 · ⭐ 212)*
## Voice Conversion

Voice cloning and conversion tools that overlap speech synthesis. Pure music/singing tools are out of scope. (3 entries)

- [RVC (Retrieval-based Voice Conversion)](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI) — Retrieval-based voice conversion with a web UI for training and real-time inference; one of the most-starred open voice conversion projects. *(MIT · ⭐ 38,552)*
- [OpenVoice](https://research.myshell.ai/open-voice) — Instant voice cloning toolkit with base-speaker TTS and tone-converter voice conversion, supporting cross-lingual cloning. *(MIT · ⭐ 37,749)*
- [kNN-VC](https://bshall.github.io/knn-vc/) — Training-free any-to-any voice conversion by nearest-neighbor matching of WavLM self-supervised features. *(MIT · ⭐ 526)*
## Benchmarks & Evals

Leaderboards, MOS predictors, and evaluation toolkits for measuring TTS quality. (6 entries)

- [UTMOS](https://github.com/tarepan/SpeechMOS) — Official implementation of UTMOS, the VoiceMOS 2022 winning ensemble MOS predictor; the standard reference-free naturalness metric for TTS evaluation. *(MIT · ⭐ 367)*
- [NISQA](https://github.com/gabrielmittag/NISQA) — Deep-learning model for single-ended speech quality prediction (MOS plus noisiness, coloration, discontinuity, loudness dimensions). *(MIT · ⭐ 974)*
- [DNSMOS](https://github.com/microsoft/DNS-Challenge) — Microsoft's reference-free P.835 SIG/BAK/OVRL speech quality predictor, widely repurposed as a quick TTS quality proxy; hosted in the DNS-Challenge repo alongside PLCMOS. *(CC-BY-4.0 · ⭐ 1,469)*
- [TTSDS](https://ttsdsbenchmark.com) — Text-to-Speech Distribution Score: a reference-free metric plus toolkit benchmarking synthetic speech against real speech across prosody, speaker identity, and intelligibility factors. *(MIT · ⭐ 102)*
- [VERSA](https://github.com/shinjiwlab/versa) — Unified evaluation toolkit for synthesized speech and audio with 65+ metrics, dedicated TTS task configs, and reproducible recipes. *(Apache-2.0 · ⭐ 437)*
- [TTS Arena v2](https://huggingface.co/spaces/TTS-AGI/TTS-Arena-V2) — Community blind pairwise voting arena (TTS-AGI) with Elo-style ranking; the most referenced human-preference benchmark for TTS quality. *(N/A (hosted community leaderboard, no code license))*
## TTS Datasets

Speech corpora used to train and evaluate TTS. Dataset terms are quoted exactly — many are non-commercial. (11 entries)

- [LibriTTS](https://www.openslr.org/60/) — 585-hour, 2,456-speaker English TTS corpus at 24 kHz derived from LibriSpeech audiobooks. *(CC-BY-4.0)*
- [LibriTTS-R](https://www.openslr.org/141/) — Miipher-restored version of LibriTTS (585 h) with improved sound quality; drop-in compatible with LibriTTS pipelines. *(CC-BY-4.0)*
- [VCTK](https://datashare.ed.ac.uk/handle/10283/3443) — 109-speaker English multi-accent corpus (44 h, 48 kHz) built for the CSTR voice cloning toolkit. *(ODC-BY-1.0)*
- [Emilia](https://huggingface.co/datasets/amphion/Emilia) — 101k-hour multilingual in-the-wild speech dataset across six languages for large-scale speech generation; gated for non-commercial research and educational use only. *(CC-BY-NC-4.0)*
- [GigaSpeech](https://github.com/SpeechColab/GigaSpeech) — 10,000-hour multi-domain English corpus (audiobooks, podcasts, YouTube) suited to supervised speech training. *(Apache-2.0 (audio: non-commercial research/educational use only))*
- [Multilingual LibriSpeech (MLS)](https://www.openslr.org/94/) — Multilingual LibriSpeech: ~50k-hour ASR-derived corpus in eight languages, widely reused for multilingual TTS. *(CC-BY-4.0)*
- [HiFi-TTS](https://www.openslr.org/109/) — 292-hour English corpus of 10 speakers (17+ hours each) at 44.1 kHz, built for high-fidelity TTS. *(CC-BY-4.0)*
- [LJSpeech](https://keithito.com/LJ-Speech-Dataset/) — 24-hour single-speaker English dataset of public-domain non-fiction; the classic single-speaker TTS training set. *(Public domain (no restrictions))*
- [AISHELL-3](https://www.openslr.org/93/) — 85-hour Mandarin multi-speaker (218 speakers) TTS corpus recorded in studio conditions. *(Apache-2.0)*
- [WenetSpeech](https://www.openslr.org/121/) — 10,000+ hour multi-domain Mandarin corpus (ASR-origin, widely reused for TTS); official terms restrict it to non-commercial purposes. *(CC-BY-4.0 (non-commercial use only))*
- [Common Voice](https://commonvoice.mozilla.org/) — Mozilla's crowdsourced multilingual corpus (100+ languages, CC0 audio); usable for TTS only with heavy filtering due to variable quality. *(CC0-1.0)*

## Notable exclusions

Projects that look relevant but were deliberately left out, with evidence:

| Project | Why excluded |
|---|---|
| Play.ht / PlayAI | Platform shut down 2025-12-31 after a Meta acqui-hire (Bloomberg, 2025-07-12). |
| LMNT | Shut down — lmnt.com renders a shutdown notice as of 2026-10-01. |
| Coqui (company) | Shut down January 2025; the coqui-ai/TTS repo is community-maintained and listed as such. |
| Coqui STT | Not TTS; dormant since the company shutdown. |
| Papercup | IP acquired by RWS (June 2025); no longer an independent TTS product. |
| Modulate (ToxMod) | Real-time voice moderation for games, not text-to-speech. |
| Voicemod | Real-time voice changer (speech-to-speech), not text-to-speech. |
| Seed-TTS / Mega-TTS | No open code released; paper-only references. |
| E2 TTS | No official implementation released. |
| Plachtaa/VALL-E-X | Archived; superseded by lifeiteng/vall-e. |
| rhasspy/piper | Archived October 2025; the maintained OHF-Voice/piper1-gpl fork is listed instead (note: license changed MIT → GPL-3.0). |
| stepfun-ai/Step-Audio | Carries a "no longer maintained" notice. |
| fairseq | Archived (read-only); TTS coverage goes through live toolkits. |
| TensorFlowTTS / ming024/FastSpeech2 | Stale; superseded by maintained implementations. |
| so-vits-svc | Archived; forks unmaintained. |
| Seed-VC | Archived. |
| DiffVC | Stale unlicensed monorepo. |
| eSpeak-NG / Festival / Flite | Classical concatenative/formant synthesizers — out of the LLM-era scope. |
| Pure singing/music voice tools | Out of scope: only voice conversion overlapping speech synthesis is covered. |
| ASR / speech-to-text | Covered by the sibling Awesome-llm-asr list. |
| Music generation / general audio generation | Separate subdomain, out of scope. |
| LLM chatbots with incidental voice features | Not TTS products. |
| Phone-call automation platforms | Not TTS products unless they ship a standalone TTS API. |
| Apple Speech framework / platform TTS APIs as products | Platform APIs, not listable projects (cloud TTS services are listed). |

## Related

More curated lists from [Awesome-llms-labs](https://github.com/Awesome-llms-labs):

- [Awesome-llm-asr](https://github.com/Awesome-llms-labs/Awesome-llm-asr) — LLM-era speech-to-text, the sibling list (toolkits that do both, like sherpa-onnx, appear in both).
- [awesome-AI-agent-orchestration](https://github.com/Awesome-llms-labs/awesome-AI-agent-orchestration) — AI agent orchestration frameworks and platforms (voice agents build on TTS).
- [awesome-startup-credits](https://github.com/Awesome-llms-labs/awesome-startup-credits) — startup credit programs (many TTS APIs offer startup tiers).

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) — entries must be real, verified on official sources, and honestly licensed. No invented licenses, star counts, or benchmark numbers.

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This list is released under the [MIT License](LICENSE). The projects listed keep their own licenses, noted per entry.
