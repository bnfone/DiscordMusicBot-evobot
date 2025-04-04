<!-- Could please someone explain this spaghetti code? -->

<p align="center">
  <img src="/.github/_images/EylDUyX0gcxJI8MusicBotLogo.png" height="90px" />
</p>

<h1 align="center"> EvoMusic - A Discord Music Bot</h1>

> This is a fork of the original [EvoBot](https://github.com/eritislami/evobot), a Discord Music Bot built with TypeScript, discord.js & uses Command Handler from [discordjs.guide](https://discordjs.guide). This version includes enhancements and additional features to improve user experience and functionality.

[![Publish Docker Image](https://github.com/EylDUyX0gcxJI8/discord-bot-evomusic/actions/workflows/publish-docker.yml/badge.svg)](https://github.com/EylDUyX0gcxJI8/discord-bot-evomusic/actions/workflows/publish-docker.yml)


## 🌟 Quickstart & Support

Thank you for your interest in EvoMusic and for helping us keep the project thriving. Your feedback, tips, and recognition mean a lot to us.

If you enjoy this project, please consider leaving a small tip as a token of appreciation. Every contribution, no matter how modest, is truly valued.

[![Donate](https://img.shields.io/badge/Donate-Click%20Here-blue)](https://bnf.one/devdonations)

For a **live demo** (please note: uptime is not 100%!), check out my [Discord Server](https://discord.gg/pyWFwFwbuq).

## 📝 Features & Commands

- 🎶 **Multi-Platform Playback:** Stream music from YouTube, Spotify, and Apple Music.
- 🔎 **Comprehensive Search:** Easily search for songs using queries and choose from multiple results.
- 🎧 **Playlist Support:** Play full playlists from YouTube, Spotify, and Apple Music.
- 📋 **Advanced Queue Management:** Skip, loop, shuffle, and remove songs from the queue with intuitive commands.
- 🔊 **Dynamic Volume Control:** Adjust volume via commands or interactive button controls.
- ⏯️ **Media Control Buttons:** Use on-screen buttons for play/pause, skip, stop, mute, and more.
- 🌍 **Multi-Locale Support:** Enjoy the bot in your preferred language.
- ⚙️ **Clear Configuration Options:** Easily customize settings such as maximum playlist size, default volume, and more.
- 🌐 **Updated Discord Intents:** Uses only the necessary intents (Guilds, GuildMembers, GuildVoiceStates, GuildMessages, GuildMessageReactions, MessageContent, and DirectMessages) to match its functionality.
- 💾 **Flexible Deployment:** Start the bot using npm or Docker with straightforward startup instructions.
- 🔄 **Piped API Fallback**: If the primary YouTube stream retrieval fails (using ytdl‑core), the bot can now automatically fall back to a Piped API instance—if enabled in your configuration—to ensure continuous playback without consuming disk space.
- 🥲 **Integrated Issue Reporting:** Submit feature requests and bug reports via our GitHub issue templates.


**Alternative Option:** For a lightweight music experience, check out our alternative [Alastor - The Radio Daemon](https://github.com/EylDUyX0gcxJI8/discord-bot-alastor).



![Preview](/.github/_images/bot-chat.png)

> **Note:** For Spotify and Apple Music integration, the bot converts the provided links to YouTube links before playing, ensuring compatibility and a broader range of music availability. The [Odesli.co API](https://odesli.co) is used for that. 
> This is absolutely not the most efficient solution, but it works...


## 📋 Requirements

- **Node.js**: v18.x or later
- **Discord Bot Token**: Make sure your bot’s token is valid and that you have enabled the required intents in the [Discord Developer Portal](https://discord.dev).
- **Spotify Credentials**: A Spotify Client ID and Client Secret (obtainable via the S[potify Developer Dashboard](https://developer.spotify.com/dashboard)).
- Additional Dependencies:
  - FFmpeg (for audio streaming)
  - Properly configured environment for Docker if you plan to run the bot using Docker


## 🛠️ Getting Started

```sh
git clone https://github.com/EylDUyX0gcxJI8/discord-bot-evomusic
cd discord-bot-evomusic
npm install
```


## ⚙️ Configuration

Copy or Rename `config.json.example` to `config.json` and fill out the values.

```bash
cp config.json.example config.json
```

Open `config.json` and update the following fields (or `.env` / `docker-compose.yml` if you're using Docker):


- `TOKEN`: Your Discord bot token.
- `SPOTIFY_CLIENT_ID` and `SPOTIFY_CLIENT_SECRET`: Your Spotify credentials.
- `MAX_PLAYLIST_SIZE`, `PRUNING`, `STAY_TIME`, `DEFAULT_VOLUME`, and `LOCALE`: Adjust these settings as desired.
- `DEBUG` and `ADVERTISEMENT_INTERVAL` can be set to control debugging output and advertisement playback frequency.
- `PIPED_API_URL`: Set this to the base URL of your chosen Piped API instance (e.g., "https://pipedapi.example.com").
- `PIPED_FALLBACK`: Set this to true to enable fallback to the Piped API for stream retrieval if the primary method fails.

⚠️ **Note**: Never commit or share your token or api keys publicly


Then run `npm run start` to start the bot.

## 🐳 Docker Configuration

For those who would prefer to use our Docker container, you may provide values from `config.json` as environment variables.

```shell
docker run -d \
  --env TOKEN=your_discord_bot_token \
  --env SPOTIFY_CLIENT_ID=your_spotify_client_id \
  --env SPOTIFY_CLIENT_SECRET=your_spotify_client_secret \
  --env MAX_PLAYLIST_SIZE=100 \
  --env PRUNING=false \
  --env STAY_TIME=30 \
  --env DEFAULT_VOLUME=100 \
  --env LOCALE=en \
  --env PIPED_API_URL=https://pipedapi.example.com \
  --env PIPED_FALLBACK=true \
  ghcr.io/EylDUyX0gcxJI8/discord-bot-evomusic:latest
```

Alternatively, use the provided docker-compose.yml for a simplified setup.

#### 🐳 Docker Compose

```yml
services:
  discord_music_bot:
    image: ghcr.io/EylDUyX0gcxJI8/discord-bot-evomusic:latest
    container_name: discord_music_bot
    environment:
      - TOKEN=your_discord_bot_token
      - SPOTIFY_CLIENT_ID=your_spotify_client_id
      - SPOTIFY_CLIENT_SECRET=your_spotify_client_secret
      - MAX_PLAYLIST_SIZE=100
      - PRUNING=false
      - STAY_TIME=30
      - DEFAULT_VOLUME=100
      - LOCALE=en
      - PIPED_API_URL=https://pipedapi.example.com
      - PIPED_FALLBACK=true
    restart: always
```

## ☁️ Host EvoMusic on Hetzner Cloud – with €20 Free Credit!

Want to run EvoMusic on your own powerful server?
Hetzner Cloud offers high-performance virtual machines at a very affordable price—perfect for hosting a music bot like EvoMusic.

By using my affiliate link below, **new customers** will receive **€20 in free cloud credits** to get started:

👉 [Get €20 Hetzner Cloud Credit](https://hetzner.cloud/?ref=bQjCoKHBYVXI)

💡 With just the smallest Hetzner instance (CX11), you can reliably run EvoMusic 24/7—ideal for communities and music lovers alike (but make sure you rotate your IPv6).

📘 **Tutorial Link _(beginner friendly)_**: (Coming soon – stay tuned!)

## 😬 Reporting Issues and Feature Requests
- **Feature Requests**: Please submit feature requests as a GitHub issue via our [feature request template](https://github.com/EylDUyX0gcxJI8/discord-bot-evomusic/issues/new?assignees=&labels=feature&template=---feature-request.md&title=).
- **Bug Reports**: Found an error? Report bugs as GitHub issues with clear reproduction steps via our [bug report template](https://github.com/EylDUyX0gcxJI8/discord-bot-evomusic/issues/new?assignees=&labels=feature&template=---bug-report.md&title=).

Your feedback is vital to improve EvoMusic!


## ⚠️ Known Issues & Alternative Solution

EvoMusic relies on several external dependencies to function correctly, and occasionally, these dependencies may cause issues that temporarily disrupt the bot's functionality. While we actively work to resolve these issues, we understand the inconvenience this may cause.

#### 🛠️ Alternative Music Bot Solution

As an alternative, we recommend trying our lightweight music bot, [Alastor](https://github.com/EylDUyX0gcxJI8/discord-bot-alastor/pkgs/container/discord-bot-alastor). This bot streams music directly from public web-radio streams, ensuring reliable playback without the need for additional integrations.

You can find more details and usage instructions here: [Alastor on GitHub](https://github.com/EylDUyX0gcxJI8/discord-bot-alastor/pkgs/container/discord-bot-alastor).

Feel free to switch between EvoMusic and Alastor depending on your needs!


## 🫣 My Motivation

I started using the original [EvoBot](https://github.com/eritislami/evobot) a few years ago and tried several YouTube music bots along the way. But over time, none of them really met my needs. What I was truly looking for was support for Spotify and Apple Music songs and playlists. Most bots that offered that either stopped working or required payment (and yes, I know—this one also breaks from time to time… sorry about that!).

So I thought: *Why not build my own music bot?* But that felt a bit too exhausting from scratch. Instead, I decided to fork [EvoBot](https://github.com/eritislami/evobot), which already had a great foundation and a modern Discord interface using slash commands.

At the time, I only had basic Python knowledge, so I used AI to help me customize the bot to fit my needs. Along the way, I even learned some JavaScript and TypeScript. In that sense, this project is a little bit [“vibe coded”](https://en.wikipedia.org/wiki/Vibe_coding?ref=evomusic) - check it out, it’s a cool concept!

What I’m trying to say is: if you have a dream (like a cool feature you want in a Discord bot), use the tools around you and just go for it. You might be surprised by what you can build.

Even though AI helped a lot, this project still takes a good amount of time and effort. So if you find it useful or fun, I’d really appreciate it if you could **star the repo** or consider [supporting the project here](#-quickstart--support). ✨


---

> [!NOTE] 
> **🎵 Disclaimer & Support Notice**
>
> This bot downloads music from YouTube, which means the artists, record labels, and rights holders don’t earn anything from the music played here. We truly encourage you to show your love for the musicians—whether by buying their music, streaming on licensed platforms, or following them on social media. Independent artists rely on your support, especially in an industry where every bit of help counts!
> 
> Please keep in mind:
> - **YouTube Terms of Service**: Downloading and using YouTube content in this way might go against YouTube’s rules. This project is meant only for learning and non-commercial purposes. We do not promote copyright infringement—it’s your responsibility to make sure your use of this bot stays within YouTube’s policies.
> - **Copyright & GEMA**: The music you access through this bot isn’t covered by any licensing or royalty payments (such as those collected by GEMA or similar organizations). If you’re in a region where these rules apply, you need to make sure you have the proper licenses if you plan to use the music publicly or commercially. The developer isn’t liable for any legal issues that might arise from using this bot.
> 
> **By using this bot, you confirm that you understand these points and agree to support artists through proper channels.**

--- 
**Note:** This fork is maintained separately from the original  [EvoBot](https://github.com/eritislami/evobot). For changes specific to this fork, ensure to target the correct repository when submitting pull requests or issues.

