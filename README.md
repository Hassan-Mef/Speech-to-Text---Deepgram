# ESP Voice Control Project

This project allows voice-controlled commands using an ESP32.  

## Project Structure

```
project-root/
│
├─ code/                  # Arduino project files
│   ├─ core.id
│   ├─ lib_audio_recording.ino
│   ├─ lib_audio_transcription.ino
│   └─ config.h           # Your local config file (ignored by Git)
│
├─ .gitignore
└─ README.md
```

## Configuration

All sensitive information such as Wi-Fi credentials and API keys are stored in `config.h`:

```cpp
// config.h
const char* WIFI_SSID = "YourSSID";
const char* WIFI_PASSWORD = "YourPassword";
const char* API_KEY = "YourPrivateAPIKey";
```

### Important Notes

- **Do not push `config.h` to GitHub**.  
  It is added to `.gitignore` to prevent leaking credentials.
- A template is provided for reference:

```cpp
// config_template.h
const char* WIFI_SSID = "YOUR_SSID";
const char* WIFI_PASSWORD = "YOUR_PASSWORD";
const char* API_KEY = "YOUR_API_KEY";
```

- To set up, copy `config_template.h` to `config.h` and fill in your information.

## Git Usage

If `config.h` was tracked before, stop tracking it with:

```bash
git rm --cached code/config.h
git commit -m "Stop tracking config.h"
```

This ensures that your credentials remain private.

## How to Run

1. Open the project in Arduino IDE.  
2. Make sure `config.h` exists with your credentials.  
3. Upload to your ESP32.  

Your ESP32 will connect to Wi-Fi and use your API key for voice commands.
