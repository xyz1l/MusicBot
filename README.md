<div align="center">

# xyz — Discord Music Bot

A feature-rich Discord music bot built with **discord.js v14** and **Lavalink v4**, supporting YouTube and Spotify playback with beautiful rich embeds, real album artwork, and platform-specific buttons.

[![Discord.js](https://img.shields.io/badge/discord.js-v14-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.js.org)
[![Lavalink](https://img.shields.io/badge/Lavalink-v4-2F3136?style=for-the-badge)](https://github.com/lavalink-devs/Lavalink)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org)

[Invite Bot](#setup) · [Join Discord](https://discord.gg/vz7d6TsN2H) · [Report Bug](https://discord.gg/vz7d6TsN2H)

</div>

---

## ✨ Features

- 🎶 **YouTube & Spotify Support** — Play from YouTube URLs, Spotify links, or just search by name
- 🖼️ **Rich Embeds** — Beautiful now-playing embeds with real album art / video thumbnails
- 🎨 **Platform Colors** — Spotify green, YouTube red, or default blurple depending on the source
- 🔘 **Interactive Buttons** — Direct links to listen on Spotify or watch on YouTube
- ⏯️ **Full Playback Controls** — Play, pause, resume, skip, stop, disconnect, loop, and volume
- 📋 **Queue System** — View the current queue with the playing song's artwork
- 🔄 **Dual Presence** — Bot status alternates between Online and Idle with "Playing music"
- 🛡️ **Crash-Proof** — Graceful error handling for Lavalink disconnections and API failures

---

## 📜 Commands

| Command | Description |
|---|---|
| `/play <query>` | Play a song by name, YouTube URL, or Spotify link |
| `/pause` | Pause the current track |
| `/resume` | Resume playback |
| `/skip` | Skip to the next track in queue |
| `/queue` | View the current queue with artwork |
| `/volume <0–200>` | Adjust playback volume |
| `/loop <off\|track\|queue>` | Set repeat mode |
| `/stop` | Stop playback and leave voice |
| `/disconnect` | Disconnect from voice channel |

---

## 🚀 Setup

### Prerequisites

- [Node.js](https://nodejs.org) v18 or higher
- A [Discord Bot Application](https://discord.com/developers/applications)
- A Lavalink v4 server ([self-host](https://github.com/lavalink-devs/Lavalink) or use a [public node](https://lavalink.darrennathanael.com))

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/xyz1l/MusicBot.git
   cd musicbot_xyz
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment**

   Rename `.env.example` to `.env` and fill in your values:
   ```env
   DISCORD_TOKEN=your_bot_token_here
   CLIENT_ID=your_application_client_id
   DEV_GUILD_ID=your_test_server_id

LAVALINK_HOST=lavalink-v4.triniumhost.com
LAVALINK_PORT=443
LAVALINK_PASSWORD=free
LAVALINK_SECURE=true

   ```

4. **Deploy slash commands**
   ```bash
   npm run deploy
   ```

5. **Start the bot**
   ```bash
   npm start
   ```

---

## 📁 Project Structure

```
xyz-core-music-bot/
├── commands/
│   ├── play.js          # Play/queue tracks (YouTube & Spotify)
│   ├── pause.js         # Pause playback
│   ├── resume.js        # Resume playback
│   ├── skip.js          # Skip current track
│   ├── stop.js          # Stop & leave voice
│   ├── disconnect.js    # Disconnect from voice
│   ├── queue.js         # Display queue
│   ├── volume.js        # Adjust volume
│   └── loop.js          # Set repeat mode
├── events/
│   ├── ready.js         # Bot startup & presence
│   └── interactionCreate.js  # Command handler
├── config.js            # Environment config loader
├── imageUtils.js        # Thumbnail & platform detection
├── presence.js          # Dual status rotation
├── utils.js             # Shared helpers
├── index.js             # Entry point
└── deploy-commands.js   # Slash command registration
```

---

## 🎵 How Spotify Works

Since this bot uses a public Lavalink node without a Spotify plugin, Spotify links are handled with a smart fallback:

1. The bot scrapes the Spotify page to extract the **song title + artist name**
2. It searches YouTube for an exact match using that info
3. The embed still shows the **Spotify album artwork** and a **Spotify button** for the original link
4. The platform color stays **Spotify green** ✅

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| [discord.js v14](https://discord.js.org) | Discord API wrapper |
| [lavalink-client](https://www.npmjs.com/package/lavalink-client) | Lavalink v4 client |
| [axios](https://axios-http.com) | HTTP requests for thumbnails & Spotify scraping |
| [dotenv](https://www.npmjs.com/package/dotenv) | Environment variable management |

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

### Made by xyz

[![Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/vz7d6TsN2H)

**[discord.gg/vz7d6TsN2H](https://discord.gg/vz7d6TsN2H)**

</div>
