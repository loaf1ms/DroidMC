# DroidMC Patched

Minecraft server panel that runs directly on your Android phone via Termux. Control your server from any browser on the same WiFi.

Original by: Loaf1ms  
Fixes and maintenance by: Mik (wafflebyte8-hue)

[![Discord](https://img.shields.io/badge/Discord-Join-5865F2?style=flat&logo=discord&logoColor=white)](https://discord.gg/u6tE8DzS5V)

---

## First, update Termux packages:

```bash
pkg update && pkg upgrade -y
```

## Install

Paste this in Termux:

```bash
curl -fsSL https://raw.githubusercontent.com/wafflebyte8-hue/Droidmc-patched/main/setup.sh -o setup.sh
bash setup.sh
```

The script will walk you through setup and configure everything automatically.

Then start the panel:

```bash
~/start-mc.sh        # foreground (shows live logs in terminal)
~/start-mc-bg.sh     # background via tmux (recommended)
```

Open in your browser: `http://your_phones_ip:8080`  
Or on the same device: `http://localhost:8080`

---

## Features

- **Server control** â€” Start, stop, force kill
- **Live console** â€” Stream logs in real time, send commands
- **Version manager** â€” Download Paper, Vanilla, or Fabric directly from official sources
- **Player management** â€” Kick, ban, unban, OP, gamemode, teleport, heal, feed
- **Plugins & Mods** â€” Upload and delete `.jar` files
- **Properties editor** â€” Edit `server.properties` from the browser
- **System stats** â€” Live CPU(broken at the moment) and RAM usage with ring gauges
- **How to Connect card** â€” Shows your IP, port, server type and version at a glance

---

## Requirements

- Android device running Termux
- 2GB+ RAM recommended (4GB+ for a smooth experience)

The setup script automatically installs OpenJDK 21, Node.js, and tmux.

---

## Tips

- Keep your phone **plugged in** while the server runs â€” Java is heavy on battery
- Run `termux-wake-lock` (requires Termux:API from F-Droid) to prevent Android from killing the server
- Use **Paper** over Vanilla or fabric for much better performance on ARM
- Set `view-distance=6` in Properties if the server feels slow

---

## File Structure

```
~/DroidMC/
â”œâ”€â”€ server.js          â† Backend & API
â”œâ”€â”€ package.json       â† Node dependencies
â”œâ”€â”€ config.json        â† Saved settings
â”œâ”€â”€ node_modules/      â† Installed packages
â””â”€â”€ public/
    â”œâ”€â”€ index.html     â† UI layout
    â”œâ”€â”€ style.css      â† Styling
    â””â”€â”€ app.js         â† Client-side logic
```

---

## Security

The panel binds to `0.0.0.0` and is accessible on your local network. There is no authentication â€” do not port forward unless you know what you're doing.
