```
   ___      _               _                      _ _
  | _ \_  |_   _| _ __ _ __| |_____ _ _   ___   __| (_)
  |   / || |  _| '_/ _` / _| / / -_) '_| |___| / _| | |
  |_|_\\_,_||_||_| \__,_\__|_\_\___|_|         \__|_|_|

```

# rutracker-cli (Modernized & Fixed)

Node.js command line interface to RuTracker for downloading `.torrent` files. 

This is a maintained fork that fixes the critical "Authentication failed" issues and adds features for non-Russian speakers.

![demo.gif](https://raw.githubusercontent.com/kuzzmi/rutracker-cli/master/public/demo.gif)

# Features
0. **Fixed Authentication**: Fully working login flow using modern HTTPS and session management.
1. **English Translation**: Automatically translates search result categories and titles from Russian to English.
2. **Multiple Downloads**: Download one or multiple .torrent files in one go.
3. **Session Persistence**: Saves authentication data locally for seamless subsequent uses.
4. **Sorted Results**: Search results are automatically sorted by size and seeder count.
5. **Color Coded Stats**: Instant visual feedback on torrent health (Seeders/Leechers).
6. **Semi-interactive Mode**: Support for CLI arguments (username, password, query).

# Recent Improvements (2026)
*   **Security**: Switched all API calls to mandatory HTTPS.
*   **Compatibility**: Added browser-mimicking `User-Agent` headers to prevent server blocks.
*   **Stability**: Inlined and fixed the core `rutracker-api` logic to resolve dependency abandonment.
*   **Cleanup**: Removed failing native dependencies (`dbus`) to ensure smooth installation on modern Node.js versions.

# Configuration

The tool creates a default configuration file at:
`~/.config/rutracker-cli/config.json`

```json
{
	"downloadPath": "/home/%user%/Torrents",
	"username": "your_username",
	"password": "your_password"
}
```

# Installation

To run this version, clone the repository and link it locally:

```bash
git clone https://github.com/syu-toutousai/rutracker-cli.git
cd rutracker-cli
npm install
sudo npm link
```

# Usage

### Interactive Mode
```bash
rutracker-cli
```

### Search Immediately
```bash
rutracker-cli -q "Interstellar"
# or
rutracker-cli --query="Interstellar"
```

### Provide Credentials via CLI
```bash
rutracker-cli -u my_user -p my_password -q "Search Query"
```

# Contributions

Feel free to open issues or pull requests on this fork!
