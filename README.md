# Claude VPS Setup Prompt

A [Claude Code](https://claude.ai/claude-code) prompt that sets up a hardened Ubuntu 24.04 VPS on Hetzner from scratch.

Feed `hetzner-public.md` to Claude Code and it will walk you through the setup interactively, asking for your username, SSH key, and whether you want Tailscale.

## What it sets up

- Admin user with SSH key authentication
- Hardened `sshd_config` (no root login, no password auth)
- Fail2ban (bans after 3 failed SSH attempts for 24h)
- UFW firewall (deny all incoming except SSH)
- Unattended security upgrades
- Tailscale (optional, with Tailscale SSH)

## Usage

```bash
claude hetzner-public.md
```

> ⚠️ Always review the file before feeding it to Claude Code to make sure it hasn't been tampered with.
