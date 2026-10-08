<p align="center">
  <img src="images/cover.png" alt="IO: your agents, right where you need them." width="720">
</p>

<p align="center">
  <b>A desktop app for working with AI agents</b><br>
  Claude Code, Codex and Antigravity on the plans you already pay for, and your own agents on your own API keys, in one place.
</p>

<p align="center">
  <a href="https://github.com/rapheal-sacr/io-releases/releases/latest"><b>Download the latest IO</b></a> ·
  Mac (Apple silicon) · Windows (x64) · Linux (x64)
</p>

---

![The new chat page](images/home.png)

## What IO is

IO is one window for all your agents. You describe a task; IO picks the agent (or you do), runs it, and puts what it makes (docs, tables, slides, web pages, images) on a canvas beside the chat. Agents can hand work to each other, run as a team on a project, follow a schedule, use their own browser, and remember what matters about you.

- **Your plans, not new bills.** Claude Code (Claude Pro/Max), Codex (ChatGPT plans) and Antigravity (Google AI Pro/Ultra) run through their official adapters on your own sign-ins. IO never sees your password or tokens.
- **Your keys for everything else.** Forge and the agents you create run on the **IO Runtime** (IO's fork of MiniMax Code) with your own Anthropic, OpenAI, Google or OpenRouter keys, stored in the system keychain and never written to disk in plain text.
- **You stay in charge.** Every agent asks before risky steps unless you let it run (Ask first, Full access or Read only, per chat). Approvals and results wait in one Inbox.

## A look around

| | |
|---|---|
| ![A chat with its canvas](images/chat-canvas.png) **Chat and canvas.** What the agent makes appears beside the chat as windows, a carousel or tiles, with the agent's own browser among them. | ![Agents](images/agents.png) **Agents.** Built-in plan agents, Forge on your keys, and agents you create with their own role, model, tools, skills and schedule. |
| ![A project](images/project.png) **Projects.** A group of agents with a shared context doc and canvas. Run the whole group (each agent passes its result to the next) or one agent at a time, on demand or on a schedule. | ![The Library](images/library.png) **Library.** Everything your agents made, from every chat, searchable and filterable. |
| ![Voice mode](images/voice.png) **Voice.** Talk to IO: it opens pages, checks on your agents, gives you a tour, and hands them work while you keep talking. | |

## Features

**Chats and agents**
- Auto picks the best agent for each message (with the Laya decision engine), or choose one yourself.
- Plan first: the agent writes a plan and waits for your OK.
- Move a chat to another agent mid-conversation (Claude Code ↔ Codex ↔ API keys) when one runs out of usage.
- Delegation: agents hand work to each other and get the result back; each hand-off shows as a card with its own chat.
- Slash commands, `@` mentions of skills, agents, chats and files, prompt suggestions, and dictation in every prompt box.

**The canvas and the browser**
- Docs, tables, slides, web pages, images, video and audio, each with version history, Publish, Download and Bookmark.
- The agent's own browser: watch it work, take over to sign in or click, and hand it back.
- Google Docs, Slides and Sheets: agents read and edit them through Google's APIs; decks show as Google draws them.

**Projects and schedules**
- Projects share a context doc and canvas across their chats; whole-group runs pass work from agent to agent.
- Go live: run a chat or project on a schedule, with results in the Inbox (or Slack).

**Memory and learning**
- Memories: what IO knows about you and your work, proposed by agents and approved by you, plus imports from ChatGPT, Claude and Manus.
- Learning: suggested improvements to prompts, memories, skills and rubrics from your finished chats.
- Rubrics: a judge agent scores chats against weighted criteria.
- Skills: reusable instructions agents load when they help.

**Teams, rooms and Slack**
- Teams sync agents, skills and memories between teammates' computers over Tailscale, with no server in between.
- Rooms: group chats where people and agents work together.
- Slack: give an API-key agent its own Slack bot, with approvals as buttons in the thread.

**Usage and benchmarks**
- Usage by agent, plan and key, with plan limits and real spend.
- Benchmarks: run one prompt across several agents and have a critic score the answers.

**Bring your history**
- Import chats from Codex and Claude Code on your computer (they continue in the same session), and from ChatGPT or Claude data exports.

## Install

Go to the [latest release](https://github.com/rapheal-sacr/io-releases/releases/latest) and, under **Assets**, download the file for your computer:

| System | Download |
|---|---|
| macOS 12 or later, Apple silicon (M1 or newer) | `IO-<version>-arm64.dmg` |
| Windows 10 or 11 (x64) | `IO-Setup-<version>.exe` |
| Linux (x64): Ubuntu 24.04, Debian 13, Fedora 40 or newer | `IO-<version>-x86_64.AppImage` |

The other files (`.zip`, `.blockmap`, `.yml`, `.json`) are for IO's self-update; you don't need them.

### macOS

1. Open the `.dmg` you downloaded.
2. Drag **IO** onto the **Applications** folder in that window, then eject the disk image (⏏ next to it in Finder's sidebar).
3. Open **IO** from Applications. IO isn't signed with an Apple Developer ID yet, so macOS says it can't verify it: click **Done** (not Move to Trash).
4. Open **System Settings › Privacy & Security**, scroll down to **Security**, and next to "IO was blocked to protect your Mac" click **Open Anyway**. Enter your Mac password and click **Open Anyway** again.

IO opens, and you won't be asked again. If you opened IO from Downloads or the disk image, it offers to move itself to Applications: say yes, as it can update itself only from there.

After an update, macOS may ask once or twice for your password to let IO use "IO Safe Storage" (where your API keys are kept), usually at your first message to an agent on an API key. Enter it and click **Always Allow**.

### Windows

1. Run `IO-Setup-<version>.exe`.
2. IO isn't code-signed yet, so SmartScreen may say "Windows protected your PC". Click **More info**, then **Run anyway**.
3. Follow the installer. It installs IO for your user only (no administrator rights needed); you can pick another folder if you like.
4. Open IO from the Start menu or the desktop shortcut.

### Linux

1. Make the AppImage runnable and start it:
   ```bash
   chmod +x IO-*-x86_64.AppImage
   ./IO-*-x86_64.AppImage
   ```
   Or in your file manager: right-click the file › Properties › Permissions › **Allow executing file as program**, then double-click it.
2. If it doesn't start and mentions FUSE, install it once: `sudo apt install libfuse2t64` on Ubuntu 24.04 and newer (`libfuse2` on Debian), or `sudo dnf install fuse-libs` on Fedora.
3. Keep the AppImage somewhere it can stay, such as `~/Applications`: IO updates itself in place.

### First launch, on every system

- **Choose your agents:** IO asks which plan agents to download (Claude Code, Codex, Antigravity). Pick any, all or none; you can change this later in **Settings › AI providers**.
- **Sign in to your plans** there with each app's own login (Claude, ChatGPT, Google). If you're already signed in to Claude Code or Codex on this computer, IO uses that sign-in.
- **Add API keys** (Anthropic, OpenAI, Google or OpenRouter) in the same place to use Forge and your own agents. Keys are encrypted with your system keychain.

### Updates

IO checks for updates by itself. When one is ready, **Update available** shows at the bottom of the sidebar: click **Restart to update**. IO checks that the update is a genuine IO release before installing it.

### Uninstalling

- **macOS:** drag IO from Applications to the Trash. To remove your chats, settings and keys too, delete `~/Library/Application Support/IO` and, in Keychain Access, "IO Safe Storage".
- **Windows:** Settings › Apps › Installed apps › **IO** › Uninstall. Your data is in `%APPDATA%\IO`.
- **Linux:** delete the AppImage. Your data is in `~/.config/IO`.

## Privacy and security

- API keys live in the system keychain (Electron safeStorage), never in config files, logs or commits.
- Plan sign-ins happen only through each provider's official app or adapter; IO doesn't handle subscription credentials.
- Agent output, files and web pages are treated as data, not instructions. The Laya guard flags text aimed at the agent, and risky steps ask first.
- Your chats, memories and canvas items stay on your computer unless you share them with a team or publish an item.

---

## Versions

The current public line started at **0.1.0**. Earlier development builds are kept on the Releases page as pre-releases named "IO dev 0.1.x". If you installed one of those, download the current version once; from then on IO updates itself.

## Feedback

Found a bug or have an idea? Use **Help › Send Feedback…** in IO (it opens a prefilled issue here), or [open an issue](https://github.com/rapheal-sacr/io-releases/issues). **Help › Export Diagnostics…** saves a zip with no keys, chat text or memories that you can attach.

<sub>Screenshots are from a development build with demo data.</sub>
