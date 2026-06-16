```
   ___      _               _                      _ _
  | _ \_  _| |_ _ _ __ _ __| |_____ _ _   ___   __| (_)
  |   / || |  _| '_/ _` / _| / / -_) '_| |___| / _| | |
  |_|_\\_,_|\__|_| \__,_\__|_\_\___|_|         \__|_|_|

```

# rutracker-cli

Node.js CLI for interacting with RuTracker. Built for downloading `.torrent` files directly from the terminal.

This fork fixes the long-standing "Authentication failed" errors and integrates real-time English translation for better accessibility.

![demo.gif](https://raw.githubusercontent.com/kuzzmi/rutracker-cli/master/public/demo.gif)

## Why this fork?

The original project was abandoned and stopped working due to changes in RuTracker's security (mandatory HTTPS, User-Agent filtering, and session cookie requirements). This version:
*   **Fixes Auth**: Modernized login flow that actually works.
*   **Translates Results**: Automatically converts Russian titles/categories to English via Google Translate API.
*   **Zero Bloat**: Removed broken native dependencies (`dbus`) for a smoother install.
*   **Inlined Logic**: Bundles a fixed version of the unmaintained `rutracker-api`.

## Installation

Clone and link it to your path:

```bash
git clone https://github.com/syu-toutousai/rutracker-cli.git
cd rutracker-cli
npm install
sudo npm link
```

## Usage

### Search for open-source mirrors (e.g., AOSP, Linux distros)
```bash
rutracker-cli -q "AOSP"
```

### Provide credentials via flags
```bash
rutracker-cli -u your_username -p your_password -q "LineageOS"
```

### Interactive mode
Just run it without arguments to enter the interactive prompt:
```bash
rutracker-cli
```

## Config
Your credentials and download path are stored at `~/.config/rutracker-cli/config.json`.

```json
{
	"downloadPath": "/home/user/Torrents",
	"username": "user",
	"password": "password"
}
```

## Workflow Tip: aria2
Chain it with `aria2c` for a full terminal-based download workflow:
```bash
rutracker-cli -q "Arch Linux" && aria2c *.torrent
```

## Contribution
Hack away. PRs are welcome on this fork.
