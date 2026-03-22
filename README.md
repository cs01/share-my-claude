# share-my-claude

Share your Claude Code session with a browser.

## Install

```
curl -fsSL https://raw.githubusercontent.com/cs01/share-my-claude/main/install.sh | sh
```

## Usage

By default, share-my-claude uses a free public server so you don't have to set anything up.

```
$ share-my-claude
```

```
Connection is ready. Sharing terminal at:

  https://chadsmith.dev/termpair/s/a3f9xK7m#xK7mN2pQ9vR1tY4w8bF3cA

 ╭────────────────────────────────────────────────────────────╮
 │                                                            │
 │  ✦ Claude Code                                             │
 │                                                            │
 │  > _                                                       │
 │                                                            │
 ╰────────────────────────────────────────────────────────────╯
```

Open the link in any browser. That's it.

## Who is this for?

**Use Claude from your phone or tablet.** Start a session on your machine, open the link on your phone, and use Claude from anywhere. Great for when you're away from your desk but want to check on a long-running task or fire off a quick prompt.

**Let others watch your session.** Share the link with a friend or coworker so they can see what Claude is doing in real-time. Use `--read-only` so they can't type.

```
share-my-claude --read-only
```

**Let others watch *and control* your session.** For the bold — share the link and let someone else type prompts and interact with Claude on your machine. This is the default.

```
share-my-claude
```

## Self-hosting

Don't want to use the public server? Run your own:

```
termpair serve --port 8000
```

Then point share-my-claude at it:

```
share-my-claude --host http://your-server.com --port 8000
```

The server is a blind relay — it routes encrypted messages but never decrypts them. Still, if you want full control, self-hosting is easy. See [termpair](https://github.com/cs01/termpair) for details.

## Security

All data is end-to-end encrypted (AES-128-GCM). The server is a blind relay and never sees your data. The encryption key is in the URL fragment, which is never sent to the server.

## Want to share other terminal apps?

share-my-claude is built on [termpair](https://github.com/cs01/termpair), which can share any terminal app (vim, htop, your shell, etc).

---

> This project is not affiliated with or endorsed by Anthropic.
