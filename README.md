# 🎵 SONOS Sync Announcement for Home Assistant

> **Seamlessly synchronize audio announcements across all your Sonos speakers with full state restore!**

This blueprint/script provides a robust way to broadcast MP3 announcements (or TTS) on your Sonos system via Home Assistant—**without disrupting music or group configurations.**  
It snapshots all Sonos speakers, creates a synchronized group, plays your announcement, and restores everything—automatically.

---

## 🚦 Requirements

- **Sonos S2 compatible speakers only**  
  *Legacy S1 models (before 2019) are **not supported** for snapshot/restore features!*
- [Home Assistant](https://www.home-assistant.io/) with Sonos integration configured
- All Sonos speakers must be discovered and responsive in HA
- Your MP3 announcement files stored in `/config/www/`
- Both **START** and **STOP** scripts implemented for full state restore

---

## 🔄 How It Works

1. **Snapshot** all Sonos speakers (state, music, groups, volume, etc.)
2. **Pause** selected speakers to avoid conflicts
3. **Unjoin** all existing groups for a clean regroup
4. **Group** selected speakers for synchronized playback
5. **Set volume** for announcement (adjustable)
6. **Play** your chosen MP3 file
7. **Wait** for playback to finish
8. **Restore** all speakers to their original state

Delays/timing for each step can be adjusted for network or stability issues.

---

## 🏠 Use Cases

- Appliance notifications:  
  *"Washing machine finished"*, *"Dishwasher done"*
- Security & safety alerts:  
  *"Motion detected in garage"*, *"Front door opened"*
- Timers & reminders:  
  *"Pizza is ready"*, *"Time for medicine"*
- Smart doorbell:  
  *"Someone is at the front door"*
- Family messages:  
  *"Dinner is ready"*, *"School pickup in 10 minutes"*

---

## 📁 File Setup

Place your MP3 files in `/config/www/` on your Home Assistant server:

```plaintext
/config/www/
├── appliances/
│   └── washing_machine_done.mp3
├── security/
│   └── door_opened.mp3
├── custom/
│   └── dinner_ready.mp3
