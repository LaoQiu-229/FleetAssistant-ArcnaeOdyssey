# ⚓ Fleet Assistant

**Arcane Odyssey Fleet Management Automation Tool**

Fleet Assistant is an AutoHotkey v2.0 automation script designed to manage your fleet operations in Arcane Odyssey. It automates deck task assignments, repairs, recovery cycles, and restocking to optimize your fleet's efficiency while you're away from keyboard (AFK).

---

## 🔧 Requirements

### Software
- **AutoHotkey v2.0** (not compatible with v1.1)
  - Download from: https://www.autohotkey.com/
  - Make sure to get v2.0, not the legacy version

### Game
- **Arcane Odyssey** (Roblox)
- Game window should be in **fullscreen** or **maximized windowed mode**

---

## 📥 Installation

1. **Install AutoHotkey v2.0**
   - Download and install from https://www.autohotkey.com/

2. **Download Fleet Assistant**
   - Save `FleetAssistant.ahk` to a folder of your choice
   - Recommended: Create a dedicated folder (e.g., `C:\ArcaneOdysseyTools\FleetAssistant.ahk\`)

3. **Run the Script**
   - Double-click `FleetAssistant.ahk` to launch
   - The GUI will appear in the top-left corner of your screen

---

## 🚀 Quick Start

### First Time Setup

1. **Configure your settings** in the GUI:
   - Set your RavenKey (default: `1`)
   - Set your FleetKey (default: `y`)
   - Choose Fleet Risk mode
   - Select tasks for each deck
   - Adjust timers if needed
   - Increase the number of Repair Wait Time if you have bad connection ( 1s = 1000ms )

2. **Save your settings** by clicking the "💾 SAVE SETTINGS" button

3. **Little setup on Roblox** make sure UI Navigation Toggle is On

4. **Tool bar sorting** move all the stuff in your hotbar into inventory, and put ONLY Raven on your hotbar

5. **Focus on your Roblox** make sure focus on Roblox, if not sure then click on Roblox once before pressing `F1`
 
6. **Start automation** by pressing `F1`

7. **Let it run!** The script will handle everything automatically

## 🔄 How It Works

### Automation Cycle Overview

Fleet Assistant operates in three phases:

### Phase 1: Startup (When F1 is pressed)

```
1. Initial Setup
   ├─ Configure Deck 1 → Your selected task
   ├─ Configure Deck 2 → Your selected task
   ├─ Configure Deck 3 → Your selected task
   ├─ Configure Deck 4 → Your selected task
   └─ Set Fleet Risk mode

2. Initial Restock (Maximize Profit only)
   └─ Restock food & supplies immediately

3. Start Timers
   ├─ Recover & Restock Timer (e.g., every 1 hour)
   └─ Repair Timer (e.g., every 3 minutes)
```

### Phase 2: Main Loop (Continuous)

The script alternates between two cycles:

#### Cycle A: Recover & Restock (Triggers every X seconds)

```
1. Switch all decks to recovery:
   ├─ Deck 1 → Petrol/Plunder
   ├─ Deck 2 → Recover
   ├─ Deck 3 → Recover
   └─ Deck 4 → Recover

2. Restock (if Maximize Profit)
   └─ Restock food & supplies

3. Wait for Setting Back Timer (e.g., 20 minutes)
```

#### Cycle B: Setting Back Tasks (Triggers after recovery period)

```
1. Restore all decks to original tasks:
   ├─ Deck 1 → Your selected task
   ├─ Deck 2 → Your selected task
   ├─ Deck 3 → Your selected task
   └─ Deck 4 → Your selected task

2. Restock (if Maximize Profit)
   └─ Restock food & supplies

3. Wait for Recover & Restock Timer (e.g., 1 hour)
```

#### Independent: Repair Cycle (Triggers every X seconds)

```
Continuous repairs:
└─ Every 3 minutes (default):
   └─ Navigate to repair menu
   └─ Execute repairs
   └─ Return to operations
```

### Example Timeline (Default Settings)

```
00:00 - Start (F1 pressed)
        ├─ Set all decks to configured tasks
        └─ Initial restock (if Maximize Profit)

00:03 - First repair
00:06 - Second repair
00:09 - Third repair

01:00 - Recover & Restock Cycle
        ├─ Switch to recovery mode
        └─ Restock supplies

01:20 - Setting Back Cycle
        ├─ Restore original tasks
        └─ Restock supplies

02:20 - Recover & Restock Cycle (repeats)
```

---

## 🔍 Troubleshooting

### Script Not Working

**Problem**: Script doesn't do anything when F1 is pressed

**Solutions**:
- Ensure AutoHotkey v2.0 is installed (not v1.1)
- Make sure Arcane Odyssey is running and in focus
- Check that RavenKey and FleetKey match your in-game bindings

### Repairs Failing

**Problem**: Repair sequence doesn't complete

**Solutions**:
- Increase "Repair Wait Time" to 1500ms or 2000ms
- Check your internet connection, since bad connection make it show up more longer
- Verify FleetKey is correct for opening fleet menu

### Settings Not Saving

**Problem**: Settings reset when reopening script

**Solutions**:
- Click "💾 SAVE SETTINGS" button before closing
- Check if `Setting.txt` exists in the same folder as the .ahk file
- Verify you have write permissions in the folder

### Script Freezes or Hangs

**Solutions**:
- Press F2 to reload the entire script
- If F2 doesn't work, press F3 to exit and restart manually
- Restart the game if necessary

---

## ⚠️ Important Notes

### Game Requirements
- **Screen Position**: Script clicks at screen center, so game must be fullscreen
- **No Window Moving**: Don't resize or move the game window during operation
- **Stable Connection**: Internet lag can cause navigation errors

### Safety & Best Practices
- **Monitor First Run**: Watch the first cycle to ensure everything works correctly
- **Test Settings**: Start with short timers to verify configuration before long AFK sessions
- **Save Often**: Click "💾 SAVE SETTINGS" after any configuration changes
- **Fair Use**: Use responsibly and in accordance with game terms of service

### Performance Tips
- **Close Other Scripts**: Only run one instance of Fleet Assistant
- **Reduce Background Apps**: Free up system resources for smoother operation
- **Stable Internet**: Use wired connection if possible for consistent performance
- **Monitor Resources**: Check that your fleet has max supplies, strength, and food before starting

### File Information
- **Setting.txt**: Auto-generated when you click "SAVE SETTINGS"
- **Location**: Same folder as FleetAssistant.ahk
- **Format**: Plain text, manually editable (advanced users only)

---

## 📝 Settings File Format

The `Setting.txt` file uses a simple key=value format:

```
RavenKey=1
FleetKey=y
FleetRisk=Maximize Profit
Deck1Task=Trading
Deck2Task=Petrol/Plunder
Deck3Task=Recover
Deck4Task=Recover
RepairWaitTime=1000
RecoverRestockTimer=3600
RepairTimer=180
SettingBackTimer=1200
```

**Advanced users** can edit this file directly, but it's recommended to use the GUI.

---

## 🆘 Support & Feedback

If you encounter issues:

1. **Check this README** for solutions
2. **Verify your configuration** matches the examples
3. **Test with default settings** to rule out configuration issues
4. **Monitor the first few cycles** to see where it fails
5. **PLS DON'T SEND IS U DON'T NEED :sob:** reach me by sending email to eris421873@gmail.com

---

## 📜 Version Information

**Author**: Eris
**Script Version**: 1.1  
**AutoHotkey Version Required**: v2.0+  
**Game**: Arcane Odyssey (Roblox)  
**Last Updated**: February 2026

---

## ⚖️ Disclaimer

This automation tool is provided as-is for educational and convenience purposes. Users are responsible for ensuring their use complies with the game's terms of service. The developer is not responsible for any consequences resulting from the use of this script, including but not limited to account actions, game penalties, or data loss.

**Use at your own risk and discretion.**

---

⚓ **Good luck, Captain!** ⚓
