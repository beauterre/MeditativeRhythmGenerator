# MeditativeRhythmGenerator
Tala maker, wavy performance.

# 🧘 Meditative Tala Generator

An algorithmic percussion engine designed to create hypnotic, evolving rhythms. Instead of static loops, this system uses polyrhythmic cycles and slow-wave sample morphing to simulate the organic feel of a human percussionist.

## 🌟 The Concept

The goal of this generator is to move away from the mechanical "grid" of Western electronic music and embrace the fluid, cyclical nature of Indian **Tala** (rhythmic cycles). 

The system generates a rhythmic tapestry where multiple time signatures coexist, creating a sense of "drifting" while remaining anchored to a central pulse.

## 🛠️ Technical Architecture

### 1. Algorithmic Polyrhythms
The engine utilizes a multi-layered sequencer where different instrument groups operate on different cycle lengths:
- **The Anchor:** Bass and Snare provide the structural grounding (the *Sam*), ensuring the listener doesn't lose their place in the meditative flow.
- **The Pulse:** High-hats provide a steady, shimmering 8/8 energy.
- **The Tala Cycle:** Ornamented percussion triggers on a non-standard cycle (e.g., 7/7 or 5/5). Because this cycle length differs from the anchor, the accents shift relative to the downbeat in every measure, creating a hypnotic, evolving pattern.

### 2. Sample Morphing (The "Breath")
To avoid the "machine-gun effect" of repeated samples, the system implements **LFO-based Cross-fading**:
- Every instrument group consists of two distinct samples (e.g., `BD1` and `BD2`).
- A slow-frequency Sine-wave LFO oscillates between them.
- The volume is interpolated so that Vol1+Vol2=100%\text{Vol}_1 + \text{Vol}_2 = 100\%Vol1​+Vol2​=100%.
- This creates a "breathing" texture where the timbre of the rhythm slowly evolves over several minutes.

### 3. Deterministic Randomness
The patterns are not purely random, but **pseudorandom**. 
- The system uses a custom `sfc32` (Small Fast Chaotic) PRNG.
- Users can input a **Seed**. This allows a specific "mood" or rhythmic "composition" to be saved and shared; the same seed will always produce the exact same rhythmic arrangement.

### 4. Organic Humanization
To prevent mathematical rigidity, the system introduces **Micro-timing Offsets**. Each trigger is shifted by a few milliseconds (±10ms\pm 10\text{ms}±10ms), mimicking the natural imperfection of a human drummer.

## 🚀 Implementation Details
- **Web Audio API:** Used for sample-accurate scheduling and low-latency playback.
- **Zero Dependencies:** Built with vanilla JavaScript, HTML5, and CSS3.
- **Linear Interpolation:** Used for smooth volume transitions between morphing samples.

## 🎧 How to Use
1. Open the HTML file in any modern web browser.
2. (Optional) Enter a unique word or number in the **Seed** field to generate a specific rhythmic identity.
3. Click **Start Ritme**.
4. Close your eyes and focus on the shifting accents.


