# Alabai

A terminal for network engineers. SSH, Telnet and serial console in tabs, with the things a
SecureCRT or PuTTY session never had: warnings while you type a disruptive command, config
snapshots you can diff, runbooks, and an AI assistant that can look at a device but never
change one.

**[Download for Windows](https://github.com/timurkz/alabai/releases/latest)**

This repository holds the licence and the Windows releases.

## What it does

- **Sessions.** SSH (password, key, keyboard-interactive / 2FA), Telnet and serial, in tabs
  and split panes, with a device tree, saved credentials and Quick Connect (`Ctrl+T`).
- **Command warnings.** While you type, the status bar lights up on commands that are
  disruptive and easy to get wrong, on Cisco IOS/IOS-XE, NX-OS and Arista EOS.
- **Paste guard.** A multi-line paste opens a dialog showing exactly what will be sent before
  it reaches the device.
- **Snapshots.** Capture `show running-config` or another `show`, and diff any two captures.
- **Runbooks and templates.** Your own procedures and config templates.
- **Session logs.** Every session recorded, with a retention setting, or none at all.
- **AI assistant.** Ask about a connected device in plain language. It runs read-only
  commands (`show`, `ping`, `traceroute`, `dir`), each one shown to you, and asks before it runs
  them unless you say otherwise. It cannot send configuration: when a change is the answer, it
  writes the config out for you to review and paste yourself. The full list of what it may run
  is at [alabai.app/assistant](https://alabai.app/assistant).

## Privacy

- **No telemetry.** No analytics, no crash reports. The one connection Alabai makes on its own
  is the update check: a minute after start and every 4 hours it asks GitHub for the latest
  version number, and sends nothing about your devices or sessions. Settings → Updates turns it
  off.
- **The AI uses your own provider and key**: OpenAI, Anthropic, Azure (Microsoft Foundry),
  Amazon Bedrock, a local server (Ollama, LM Studio, llama.cpp, vLLM) or any OpenAI-compatible
  endpoint. With a local model, nothing leaves your machine. The assistant can be switched off
  entirely.
- **Secrets are masked** before device output reaches the model: enable secrets, SNMP
  communities, TACACS/RADIUS keys, password hashes. This is best-effort pattern matching; if
  that is not enough for your network, use a local model.

## Install

Alabai 1.0 is for 64-bit Windows 10 and 11. Download `alabai-setup.exe` from
[alabai.app](https://alabai.app) or the
[releases page](https://github.com/timurkz/alabai/releases/latest) and run it. It installs for
your user account and needs no administrator rights.

Because Alabai is new, Windows SmartScreen may show a warning. Choose **More info**, check that
the publisher is Timur Rakhimzhanov, then choose **Run anyway**.

When a new version is out, **Update** appears at the right of the status bar, at the bottom of
the window. Alabai installs it only if
Windows confirms it is signed by the same publisher. Settings and devices are kept across
updates.

## Feedback

**Feedback** in the status bar opens a short form at
[alabai.app/feedback](https://alabai.app/feedback) in your browser. Or write to
[feedback@alabai.app](mailto:feedback@alabai.app).

To report a vulnerability, write to [security@alabai.app](mailto:security@alabai.app). Please
don't open a public issue for it.

## Licence

Alabai is free to use, including at work, under the
[Business Source License 1.1](LICENSE.txt). This is not an open-source licence. You may not offer
Alabai, or a modified version of it, to others as a product or service, paid or free. Passing on
an unmodified official release, free of charge, is fine.

For other arrangements, write to [legal@alabai.app](mailto:legal@alabai.app). The open-source
components Alabai includes keep their own licences, listed in `THIRD_PARTY_NOTICES.txt` beside
the installed program.

## Disclaimer

You are responsible for your use of Alabai, including everything it sends to the systems you
connect to, whether you typed it or its AI assistant proposed it, and for being authorised to
access those systems. The AI assistant sends session content to the AI provider you choose,
under that provider's terms; its answers and its safeguards are not guaranteed. Alabai is
provided as is, without warranty of any kind.
