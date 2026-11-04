# Miyoo Audio Enhancement DSP Pack

## The Audio Problem on Miyoo Handhelds

Anyone who spends significant time gaming on Miyoo devices (especially the Miyoo Mini Flip) will quickly notice several inherent hardware and software audio limitations:

- **Low Headphone Output Volume:** When plugging in wired headphones or IEMs, the stock output volume is noticeably weak, even with the physical volume cranked to the maximum.
- **Flat, Lifeless Sound Signature:** Both the tiny built-in speaker and the unamplified headphone circuit produce a thin sound profile that lacks bass and dynamic depth.
- **Speaker Crackling & Digital Clipping:** Trying to compensate for the low volume by pushing RetroArch's digital Audio Gain too high (e.g., +10dB) immediately causes harsh digital clipping, distortion, and speaker rattling during loud gameplay moments.
- **Missing Stock Filters:** Many custom firmwares strip out the default RetroArch audio filters, or the stock presets themselves have flaws (for example, the default `BassBoost.dsp` cuts overall volume down to 30%, making the quiet audio issue even worse).

To solve these issues without sacrificing game performance, this repository provides **`Custom.dsp`**—a custom-tuned RetroArch DSP configuration that I created and tested—alongside three classic presets so you can easily upgrade your device's audio quality and volume.

> **Compatibility Note:** I have currently only tested these configurations on the **Miyoo Mini Flip**, but since they utilize standard RetroArch DSP modules, they should work seamlessly on other Miyoo models (Miyoo Mini, Miyoo Mini Plus, Miyoo A30) and other RetroArch-based handhelds.

---

## Included DSP Files

### 1. `Custom.dsp` (Recommended Main Preset)
Created and tuned specifically to fix the Miyoo Mini Flip's audio bottlenecks. It significantly boosts perceived loudness, brings out crisp sound effects, and adds a clean, punchy bass response while keeping audio peaks under control so your headphones or speaker do not crackle.

### 2. Alternative Presets (Included in Release)
Depending on your headphones, speaker setup, or personal taste, you can also choose from these three included filters:
- **`Crystalizer.dsp`**: Focuses purely on dynamic range expansion and high-frequency clarity. Great if you want a strong volume and detail boost without adding extra bass.
- **`BassBoost.dsp`**: Emphasizes low-end frequencies (`200Hz`) while reducing the overall mix gain to avoid clipping. Suitable if you want a warm, bass-heavy tone at lower volume levels.
- **`ChipTuneEnhance.dsp`**: Adds EQ adjustments, stereo crossfeed, and subtle reverb. Ideal for 8-bit chiptunes (GB, GBC, NES) when you want a wider, less fatiguing stereo image on headphones.

---

## Installation Guide

1. Go to the **Releases** section of this repository and download the `.dsp` files (`Custom.dsp`, `Crystalizer.dsp`, `BassBoost.dsp`, `ChipTuneEnhance.dsp`).
2. Connect your Miyoo SD card to your computer.
3. Copy all `.dsp` files into your RetroArch audio filter directory:
   - **Onion OS / RedOnion OS:** `/mnt/SDCARD/RetroArch/.retroarch/filters/audio/`
4. Safely eject the SD card and insert it back into your device.

---

## How to Configure and Save Globally in RetroArch

**Important:** To save these audio settings globally across all systems, you must configure them through the standalone **RetroArch app** from your main menu (not while running a game).

1. From your device's main menu, navigate to **Apps** and launch **RetroArch**.
2. *(Optional)* If the `.dsp` files do not show up later, go to **Settings -> Directory -> Audio Filter** and point it to `/mnt/SDCARD/RetroArch/.retroarch/filters/audio/`.
3. Go to **Settings -> Audio** and apply the following configuration:
   - **DSP Plugin:** Select **`Custom.dsp`** (or choose `Crystalizer.dsp`, `BassBoost.dsp`, or `ChipTuneEnhance.dsp` depending on your preference).
   - **Volume Gain (dB):** Set to **`3.0 dB`**. Pairing `Custom.dsp` with a `3.0 dB` gain hits the sweet spot for loud, full-bodied volume without introducing digital clipping.
   - **Audio Resampler:** Set to **`sinc`**.
   - **Resampler Quality:** Set to **`Highest`** *(Recommended if your CPU is overclocked to 1600MHz; uses virtually zero extra CPU overhead and keeps games running at full speed).*
   - **Audio Latency (ms):** Set to **`48`** or **`64`**.
4. **Save the Configuration:** Back out to the **RetroArch Main Menu**, select **Configuration File**, and click **Save Current Configuration**.
5. Select **Quit RetroArch**. Your audio settings are now permanently saved and will automatically apply to all games.

*(Note: If a specific system does not apply the settings, it means that system already has a custom override saved. Launch a game on that system, press `Menu + Select` to open the RetroArch Quick Menu, set the audio options above, and go to **Quick Menu -> Overrides -> Save Core Overrides**).*
