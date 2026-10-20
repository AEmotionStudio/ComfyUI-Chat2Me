# ComfyUI-Chat2Me

[![Sold Open](.github/sold-open-badge.svg)](https://soldopen.org/)

Chat with a character in ComfyUI; each reply is a directed MiniMax H3 video in that character's look and voice,
rendered on your own GPU.

![Chat2Me: a message holding up a picture of a glowing crystal, the reply card while its clip renders, and a frame of the reply: an elf ranger beside the crystal and two brass lanterns](https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_hero.png)

[<img src="https://img.youtube.com/vi/CTZ0_IHsflQ/maxresdefault.jpg" width="100%">](https://youtu.be/CTZ0_IHsflQ)
<p align="center"><i>How Chat2Me Works: From First Message to Film. (Click to watch on YouTube)</i></p>

This repo is the front door: this README and the issue tracker. There is no code here. Chat2Me's code is in a private
repo that sponsors get access to.

## What it does

- Make a character from a RefCap or from one photo of a face, and give them a voice.
- Type to them. A director LLM (Ollama, or the claude CLI) turns your message into up to three shots, and ComfyUI
  renders them as MiniMax H3 clips with speech.
- Keep a story: worlds with places, a cast, an editable story ledger, continuity between clips, branches and retakes.
- Publish a session as one film, with title cards, fades, credits and subtitles.

## Visual guide

One session, in the order it was made.

<table>
<tr>
<td width="50%"><img src="https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_two_voices.webp" alt="A silver-haired elf ranger and a red-bearded dwarf talk in a cavern of glowing violet crystals"><br><sub>Elowen and Brokk in one reply, each in their own voice.</sub></td>
<td width="50%"><img src="https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_vesper.webp" alt="A lavender-skinned sorceress with black horns talks at her desk in a candle-lit tower study"><br><sub>Vesper, made from one photo of her face, in her tower study.</sub></td>
</tr>
</table>

### 1. Make a character

A character is a RefCap's face views, or one photo of a face, plus a body RefCap that carries the outfit and a voice
reference. Vesper started from her photo; the director wrote her speech style.

![The character dialog for Vesper: a head photo read as one view, four full-body views, a voice reference, and her look, outfit, voice and persona written out](https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_character.png)

### 2. Give them a world

Hollowsong has two places with sets of their own, a crystal cavern and a tower study, and a start: the place, the
hour, a prop, an open thread and the first message.

![The world dialog for Hollowsong: its premise and rules, two places with their sets, and how a story there starts](https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_world.png)

### 3. Type, and watch the reply arrive

The director plans the shots, ComfyUI renders them, and the card shows how far it has got. Clips play back to back;
**Show words** lists what is said and done.

![A reply card while a clip samples: the stages, the step, the time so far and the usual time for the clip](https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_progress.png)

![The Chat2Me page mid-story: sessions and characters on the left, Elowen and Brokk in a reply in the middle, the story ledger on the right](https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_overview.png)

### 4. Show them something

**Take a picture** of a frame, crop the part you mean, name it, and put it on your next message. The reply holds it.

![Take a picture: a frame of the cavern with a box round one crystal, named the singing crystal](https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_take_picture.png)

### 5. Publish the story as one film

![The Publish dialog set to Chapters: the title and your messages on cards, subtitles, a card for each new place, fades between turns, and The End](https://github.com/AEmotionStudio/ComfyUI-Chat2Me/releases/download/assets-v1/chat2me_publish.png)

> All of it comes from one session at Medium quality (960x544) on an RTX 4070 12 GB, rendered with a community
> MiniMax H3 turbo fine-tune and directed by a Gemma 4 12B variant in Ollama. The characters and places are made up:
> faces from a community Krea 2 fine-tune, bodies and sets rendered with H3, voices designed with VoxCPM2; no one's
> face or voice was used. They are free to download as [RefCaps on Hugging Face](https://huggingface.co/AEmotionStudio/H3-RefCap).

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
