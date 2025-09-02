# M5Stack Atom Echo ESPHome Configuration

This repository contains the ESPHome configuration for the M5Stack Atom Echo, a compact voice assistant device powered by ESP32.

## Features

- **Voice Assistant Integration**: Supports Home Assistant voice assistants with wake word detection.
- **On-Device Wake Words**: Includes models for "Okay Nabu", "Hey Mycroft", and "Hey Jarvis" with adjustable sensitivity.
- **Wake Sound**: Optional audio feedback when wake word is detected (before voice assistant starts).
- **LED Indicators**: Visual feedback for different states (listening, processing, errors).
- **Timer Functionality**: Built-in timer with audio alerts.
- **OTA Updates**: Over-the-air firmware updates via ESPHome or HTTP.
- **Home Assistant Integration**: Full API integration with encryption.

## Hardware Requirements

- M5Stack Atom Echo
- USB-C cable for flashing

## Installation

### Option 1: ESP Web Tools (Recommended)

1. Visit the [project website](https://doyouhost.github.io/M5Stack_Atom_Echo/) (built via GitHub Pages).
2. Connect your M5Stack Atom Echo via USB.
3. Click "Install" and follow the prompts.

### Option 2: ESPHome CLI

1. Install ESPHome: `pip install esphome`
2. Clone this repository: `git clone https://github.com/DoYouHost/M5Stack_Atom_Echo.git`
3. Navigate to the directory: `cd M5Stack_Atom_Echo`
4. Compile and upload:
   ```bash
   esphome run m5stack_atom_echo.yaml
   ```

## Configuration

### Wake Sound Setup

The device supports playing a wake sound when a wake word is detected:

1. **Enable Wake Sound**: In Home Assistant, toggle the "Use wake sound" switch.
2. **Customize Sound**: 
   - Export your audio file from Audacity as WAV:
     - Sample rate: 16000 Hz
     - Bit depth: 16-bit PCM
     - Channels: Mono (recommended)
   - Add the file to the `sounds/` directory.
   - Update the `m5stack_atom_echo.yaml` file to include your sound file in the `media_player` section.
   - Commit and push changes to trigger a firmware update.

### Wake Word Sensitivity

Adjust wake word sensitivity via the "Wake word sensitivity" select in Home Assistant:
- Slightly sensitive
- Moderately sensitive (default)
- Very sensitive

### Wake Word Engine Location

Choose where wake word processing occurs:
- **On device**: Local processing (default, more responsive)
- **In Home Assistant**: Server-side processing (requires Home Assistant setup)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues and questions:
- Check the [Issues](https://github.com/DoYouHost/M5Stack_Atom_Echo/issues) page
- ESPHome documentation: https://esphome.io/
- M5Stack documentation: https://docs.m5stack.com/en/atom/atomecho/
