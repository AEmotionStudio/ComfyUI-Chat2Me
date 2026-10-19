# ComfyUI-Chat2Me

[![Sold Open](.github/sold-open-badge.svg)](https://soldopen.org/)

Chat with a character in ComfyUI; each reply is a directed MiniMax H3 video in that character's look and voice,
rendered on your own GPU.

This repo is the front door: this README and the issue tracker. There is no code here. Chat2Me's code is in a private
repo that sponsors get access to.

## What it does

- Make a character from a RefCap or from one photo of a face, and give them a voice.
- Type to them. A director LLM (Ollama, or the claude CLI) turns your message into up to three shots, and ComfyUI
  renders them as MiniMax H3 clips with speech.
- Keep a story: worlds with places, a cast, an editable story ledger, continuity between clips, branches and retakes.
- Publish a session as one film, with title cards, fades, credits and subtitles.

## Getting it

[Sponsor on GitHub](https://github.com/sponsors/AEmotionStudio) for US$5 a month. GitHub then invites you to the
private repo `aemotion-studio/ComfyUI-Chat2Me`; clone it into `ComfyUI/custom_nodes`.

## How Chat2Me is sold: Sold Open

Chat2Me is [Sold Open v0.2](https://soldopen.org/): you pay for access, not for permission.

- **What the price pays for:** access to the private repo that holds Chat2Me, every version as it is released, and
  direct support. Cancel any time.
- **Licence:** every version is GPL-3.0-or-later.
- **Source:** the code is the download, in the sponsors' private repo. It is not public.
- **Early access:** none. Every sponsor gets every version the day it is released.
- **Sharing:** you may share what you get. Nothing checks whether you paid, and when a sponsorship ends, what you
  downloaded stays yours.
- **Other terms:** the models below are not part of Chat2Me and carry their own licences.

## What it needs

- ComfyUI with its native MiniMax H3 nodes, and [ComfyUI-RefCap](https://github.com/AEmotionStudio/ComfyUI-RefCap)
  (free).
- The H3 files from [Comfy-Org/MiniMax-H3](https://huggingface.co/Comfy-Org/MiniMax-H3), which you download yourself
  under the MiniMax H3 Community License. As of October 2026 it does not cover the United States, the European Union,
  the United Kingdom or South Korea; read it before you download.
- A director: [Ollama](https://ollama.com) (`gemma4:12b` by default), or the `claude` CLI, which sends the story to
  Anthropic and bills your account.
- `ffmpeg`, for publishing a film.

Built and measured on one machine: an RTX 4070 12 GB with 31 GB of RAM, on Linux. There, on a community H3 turbo
fine-tune, a 10 s clip at Low quality took about 86 to 160 s. One turn or build runs at a time, and there is no access control, so keep it on your own
machine.

## Questions and bugs

Open an issue here.
