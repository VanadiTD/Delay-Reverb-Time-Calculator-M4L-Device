# Delay-Reverb-Time-Calculator-M4L-Device
A Max for Live device that displays BPM-synced delay and reverb times inside Ableton Live.

To download, click the 'Download raw file' button.

Overview
Stop switching between your DAW and a browser calculator. This device syncs to Live's transport via plugsync~ and shows you the exact millisecond values you need — right in your device chain.

Reverb: Choose from 4 room sizes and instantly see Pre-Delay, Decay Time, and Total Reverb Time
Delay: Choose from 10 note values and see Normal, Dotted, and Triplet times in both ms and Hz

All values update in real time when you change the BPM.

┌─────────────────────────────────────────────────────┐
│  DELAY & REVERB CALCULATOR              BPM: 120.0  │
├─────────────────────────────────────────────────────┤
│  REVERB  Hall (2 Bars)                         1/4  │
│  PRE-DELAY    │  DECAY TIME    │  TOTAL REVERB TIME │
│  62.5 ms      │  3937.5 ms    │  4000 ms           │
├─────────────────────────────────────────────────────┤
│  DELAY  1/4 (1 Beat)                          3/10  │
│  NORMAL       │  DOTTED (×1.5) │  TRIPLET (×2/3)   │
│  500 ms       │  750 ms        │  333.33 ms         │
│  2 Hz         │  1.33 Hz       │  3 Hz              │
└─────────────────────────────────────────────────────┘

Requirements

Ableton Live 11 or later (with Max for Live)
Max 8 or later


Installation

Download DelayReverbCalc.amxd from the Releases page
Drag and drop it onto any track in Ableton Live

That's it. No additional files needed.

Usage
BPM Sync
The device automatically syncs to Live's BPM via plugsync~. No setup required — just load and play.
Selecting Reverb Size
Send an integer to Inlet 1 to select the reverb size:
ValueSize0Hall (2 Bars)1Large Room (1 Bar)2Small Room (1/2 Note)3Tight Ambience (1/4 Note)
Selecting Delay Note Value
Send an integer to Inlet 2 to select the note value:
ValueNote01/1 (1 Bar)11/2 (2 Beats)21/4 (1 Beat)31/841/1651/3261/6471/12881/25691/512
Number boxes for both selections are included in the device view, so you can also click directly without any patching.

How the Values Are Calculated
Reverb Pre-Delay
Each room size uses a musically meaningful note value as its pre-delay:
SizePre-Delay NoteFormulaHall (2 Bars)1/32 notebar ÷ 32Large Room (1 Bar)1/64 notebar ÷ 64Small Room (1/2 Note)1/128 notebar ÷ 128Tight Ambience (1/4 Note)1/512 notebar ÷ 512
Decay Time = Total Reverb Time − Pre-Delay
Delay

Normal = bar ÷ note division
Dotted = Normal × 1.5
Triplet = Normal × 2/3
Hz = 1000 ÷ ms


Technical Details

Built with jsui and the mgraphics API for all rendering
BPM is retrieved from Live's transport via plugsync~
Designed to fit within Live's fixed device height of 169px
Audio pass-through via plugin~ → plugout~


License
MIT License — free to use, modify, and distribute.

Credits
Developed with the assistance of Claude (Anthropic).
