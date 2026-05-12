# Embodied AI for Elder Care: Pilot Study with Pepper and LLM

## Overview
A fully local, privacy-preserving voice interaction system enabling emotionally 
supportive, structured dialogue between the Pepper humanoid robot and older adults 
with Mild Cognitive Impairment (MCI). Built as part of an IRB-approved pilot study 
at NC State University's NeuroComputational Ethics Research Group.

## Research Context
**Institution:** NC State University — Departments of ECE, Philosophy, Computer 
Science, Psychology, and Business Management  
**Target Population:** Adults 60+ with MCI and their care partners (10 dyads)

## System Architecture
A fully offline pipeline running on a Jetson AGX Orin edge device:
→ User Speaks
→ Voice Activity Detection (Jetson)
→ Transcribe Audio via Whisper ASR (Jetson)
→ Sentiment Classification (Jetson)
→ LLM Response Generation via Ollama / Phi-3.5 (Jetson)
→ SSH to Pepper Robot
→ Pepper speaks response + synced gestures
All processing is local — no cloud dependency, no data leaving the device.

## Tech Stack
- **Robot:** SoftBank Robotics Pepper
- **Edge Hardware:** NVIDIA Jetson AGX Orin
- **ASR:** OpenAI Whisper (on-device)
- **LLM:** Phi-3.5 via Ollama (fully offline)
- **Languages:** Python
- **Communication:** SSH (Jetson ↔ Pepper)
- **Input:** External USB microphone

## Key Features
- Real-time speech recognition with low-latency (~4.2s end-to-end)
- Sentiment-aware dialogue management with structured persona prompts
- Emotionally attuned gesture output synced with conversational intent
- Fully offline — privacy-preserving by design, no internet required
- LLM outputs constrained to reliable 2–3 sentence responses

## Performance
| Metric | Result |
|---|---|
| Average total latency | ~4.2 seconds |
| ASR accuracy | High for clear speech; minor drops in noisy environments |
| LLM consistency | Reliable short outputs via structured prompting |
| Dialogue quality | Favorable emotional tone and pacing (observer-rated) |

## Research Objectives
- Develop an ethically attuned socially assistive robot for MCI engagement
- Integrate AI ethics, robotics, psychogeriatrics, and human factors
- Measure effectiveness via self-reports and physiological biomarkers
- Develop VR-based ethical simulation tools from real interaction data

## Data Collected
- Interaction logs and transcripts
- Self-report surveys (wellbeing, engagement)
- Observer notes (nonverbal cues, rapport)
- Screening via Short Blessed Test

## Next Steps
- Integrate robot movement and navigation
- Refine LLM responses for contextual sensitivity
- Adapt system for diverse populations and cognitive profiles
- Build immersive VR ethical simulation scenarios (ADC framework)

