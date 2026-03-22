
```
  ╭─────────────────────────────────────────────────────────╮
  │                                                         │
  │       ✦  share-my-claude                                │
  │                                                         │
  │   share your claude code session with anyone via a link │
  │                                                         │
  ╰─────────────────────────────────────────────────────────╯
```

Share your [Claude Code](https://claude.ai/code) session with anyone. They can watch — or even control — your Claude session from their browser in real-time.

End-to-end encrypted. The server never sees your data.

## Install

```
curl -fsSL https://raw.githubusercontent.com/cs01/share-my-claude/main/install.sh | sh
```

## Usage

```
$ share-my-claude
```
```
  ╭──────────────────────────────────────────────────────────────╮
  │                                                              │
  │  ✦ sharing claude session                                    │
  │                                                              │
  │  share this link:                                            │
  │  http://localhost:8000/s/a3f9xK7m#xK7mN2pQ9vR1tY4w8bF3cA    │
  │                                                              │
  │  viewers: 0  │  access: read/write  │  encrypted: AES-128    │
  │                                                              │
  ╰──────────────────────────────────────────────────────────────╯

  ╭─ Claude Code ──────────────────────────────────────────────╮
  │                                                            │
  │  > help me refactor the auth module                        │
  │                                                            │
  │  I'll start by reading the current auth module...          │
  │                                                            │
  ╰────────────────────────────────────────────────────────────╯
```

That's it. A link is printed and opened in your browser. Share the link with anyone.

### Options

```
share-my-claude --read-only     # viewers can only watch, not type
share-my-claude --port 9000     # use a different port
share-my-claude --cmd "claude --allowedTools bash"  # pass args to claude
```

## How it works

1. Starts a local server
2. Launches `claude` in a shared, encrypted terminal
3. Gives you a link — anyone with it can view (or control) your session

All terminal data is **end-to-end encrypted** with AES-128-GCM. The server acts as a blind relay — it routes encrypted messages but never decrypts them. The encryption key lives in the URL hash fragment, which is never sent to the server.

## Security

- **End-to-end encrypted** — AES-128-GCM with key rotation
- **Zero-knowledge server** — never sees plaintext
- **Key in URL fragment** — never transmitted to server
- **`--read-only`** — lock it down so viewers can only watch

## Not just for Claude

share-my-claude is a wrapper around [termpair](https://github.com/cs01/termpair), which can share any terminal application. Want to share vim, htop, or a live coding session?

```
termpair share --cmd vim
termpair share --cmd "python3 -i"
termpair share  # shares your default shell
```

Check out [termpair](https://github.com/cs01/termpair) for more.

---

> **Note:** This project is not affiliated with or endorsed by Anthropic. Claude Code is a product of [Anthropic](https://anthropic.com). This is an independent, open-source tool that wraps Claude Code with encrypted terminal sharing.
