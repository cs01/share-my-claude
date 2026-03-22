# share-my-claude

Share your Claude Code session with a browser.

## Who is this for?

**Use Claude from your phone or tablet.** Start a session on your machine, open the link on your phone, and use Claude from anywhere.

**Let others watch your session.** Share the link so others can see what Claude is doing in real-time. Use `--read-only` so they can't type.

**Let others control your session.** Share the link and let someone else interact with Claude on your machine. This is the default.

## Install

```
curl -fsSL https://raw.githubusercontent.com/cs01/share-my-claude/main/install.sh | sh
```

This installs `termpair` (the server/client) and `share-my-claude` (a wrapper that runs `termpair share --cmd claude`).

## Quick Start

**1. Start the server**

```
termpair serve --port 8000
```

This is the relay that routes encrypted data between your terminal and the browser. It never sees your data — everything is end-to-end encrypted.

**2. Share your Claude session**

In another terminal:

```
share-my-claude --host http://localhost --port 8000
```

```
Connection is ready. Sharing terminal at:

  http://localhost:8000/s/a3f9xK7m#xK7mN2pQ9vR1tY4w8bF3cA

 ╭────────────────────────────────────────────────────────────╮
 │                                                            │
 │  ✦ Claude Code                                             │
 │                                                            │
 │  > _                                                       │
 │                                                            │
 ╰────────────────────────────────────────────────────────────╯
```

**3. Open the link** in any browser. Done.

To make the session accessible outside your local network, run the server on a machine with a public IP or use a tunnel (ngrok, cloudflare tunnel, etc).

## Options

`share-my-claude` passes all arguments through to `termpair share`:

```
share-my-claude --read-only                        # viewers can only watch
share-my-claude --host https://my-server.com --port 443  # use your own server
```

## Security

All data is end-to-end encrypted (AES-128-GCM). The server is a blind relay — it routes messages but never decrypts them. The encryption key lives in the URL fragment, which is never sent to the server.

## Want to share other terminal apps?

share-my-claude is built on [termpair](https://github.com/cs01/termpair), which can share any terminal app (vim, htop, your shell, etc).

---

> This project is not affiliated with or endorsed by Anthropic.
