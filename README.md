# Choicer Voicer — Play the Free Online Dubbing Game in Your Browser

![Price: free](https://img.shields.io/badge/price-%240-f2c84b) ![Platform: any browser](https://img.shields.io/badge/platform-any%20modern%20browser-35b8b3) ![Download: none](https://img.shields.io/badge/download-none%20needed-e85b46) ![Watermark: never](https://img.shields.io/badge/watermark-never-121311) ![Built with Astro](https://img.shields.io/badge/built%20with-Astro%205-ff5d01)

![Choicer Voicer poster of a voice actor at a microphone under night-arcade neon lights](https://choicervoicer.co/images/home/choicer-voicer-voice-actor-poster.webp)

[Choicer Voicer](https://choicervoicer.co/) is a free, browser-based dubbing game. You watch a short scene with its dialogue stripped out, record every line in your own voice, and get scored on how closely your timing and delivery match the original performance. When the round ends, you export the finished dub as a clean MP4 — no download, no account, no watermark, and no ads. Open the site, allow your microphone, and you are on stage in seconds.

This repository is the home of the web app behind that experience. This introduction explains what the game is, how a round works, and why the project is built the way it is.

## What Is Choicer Voicer?

*The Choicer Voicer* is a beloved indie dubbing game by [YeahMaybe](https://yeahmaybe.itch.io/the-choicer-voicer): a game-show studio where you listen to a reference voice line, perform it back into your microphone, and face a panel of judges. Around it, a busy community on [GameBanana](https://gamebanana.com/games/20674) publishes hundreds of "dub packs" — scenes from shows, films, and memes prepared for dubbing practice.

The desktop original is a paid Windows and Linux game, which leaves a lot of players out: anyone on a phone, a school Chromebook, or a Mac, and anyone who simply wants to try dubbing before buying a full game. Choicer Voicer online exists for exactly those players. It is an independent, fan-made web version that brings the core loop — listen, perform, get judged — to any modern browser, free of charge, while crediting every pack creator and pointing fans back to the original game.

## How a Round Works

![Choicer Voicer gameplay loop banner showing the listen, record, and score stages](https://choicervoicer.co/images/home/choicer-voicer-loop-banner.webp)

A Choicer Voicer session is one tight loop, repeated until you are proud of the take — or crying with laughter at it:

1. **Pick a scene.** Choose one of the curated dub packs — each one is a real community creation with its own page, poster, and credits.
2. **Listen to the line.** The scene plays with original dialogue intact so you can study the rhythm, pacing, and attitude of each line.
3. **Perform it back.** The dialogue drops out, the caption stays up, and your microphone captures your take. Re-record any line until it feels right.
4. **Get scored and export.** A scoring engine compares your delivery against the reference and rates every line. One click renders your full dub — your voice mixed over the scene — as an MP4 you can post anywhere.

The whole loop runs inside the page. There is no install step, no render queue, and no "sign up to continue" wall between you and your first take.

## Key Features

- **Genuinely free.** Every scene, the scoring, and the video export cost nothing. There is no credit system, no premium tier, and no watermark on what you make.
- **Zero download.** The entire Choicer Voicer experience — playback, recording, mixing, encoding — runs in the browser tab.
- **Instant-loading packs.** Scenes are pre-processed server-side and stream in seconds, instead of arriving as huge ZIP archives you must download and unpack.
- **Real scoring.** Lines are rated on timing and rhythm against the original performance, so every retake teaches you something concrete about delivery.
- **Private by design.** Your microphone audio is processed on your own device and never uploaded. No ads, no trackers, no account.
- **Works on phones.** Recording and scoring behave the same on mobile and tablet as on desktop — the first time this style of game has been playable on a phone at all.
- **Creators credited.** Every pack page names its author and links to the original upload, and the site links back to the paid desktop game it celebrates.
- **Clean MP4 export.** Share your dub straight to TikTok, YouTube, or a group chat with no branding stamped over your work.

## A Pack Library Built for Browsing

![Choicer Voicer pack workbench showing dub pack cards with posters, line counts, and difficulty](https://choicervoicer.co/images/packs/choicer-voicer-pack-workbench.webp)

The current library holds **10 curated scenes and 192 voice lines** of dubbing material, hand-picked from the GameBanana community and growing steadily. Instead of burying everything in one endless list, every Choicer Voicer pack gets a dedicated page with its poster, duration, line count, pacing stats, creator credits, and a one-click way to start playing. You can [browse the full pack library](https://choicervoicer.co/choicer-voicer-packs/) to see what is on stage right now.

That structure is deliberate. Each scene page is fully pre-rendered and indexable, which makes the library useful in two directions: players can find a specific scene from a search engine, and pack creators get a permanent, linkable home for their work that a JavaScript-only site could never give them.

## Scoring That Actually Teaches Timing

Dubbing well is mostly a rhythm skill, and the score reflects that. The engine measures how your take lines up with the reference — where you came in, how long you held, where the beats landed — rather than how expensive your microphone is. A laptop mic or earbuds are all you need; what improves your Choicer Voicer score is listening closely and matching the cadence, which is precisely the skill voice actors drill. Scores are shown per line as well as for the whole scene, so you can see exactly which beat you rushed and which one you nailed, then jump straight back to the line that needs another take. The result is a game that is funny with friends and quietly useful as practice.

## Choicer Voicer Online vs. the Desktop Original

This project is a companion to the desktop game, not a replacement for it. The honest comparison:

| | Choicer Voicer online (this project) | *The Choicer Voicer* (desktop) |
|---|---|---|
| Price | Free | About $5 on itch.io |
| Platforms | Any modern browser, including phones | Windows and Linux |
| Install | None | Download and install |
| Content | Curated community dub packs, instant loading | Full studio: judges, voice packs, Twitch modes, local multiplayer, pack tooling |
| Best for | Trying dubbing right now, quick sessions, mobile play | The complete game-show experience |

If the browser version makes you laugh, buy the original — it is the reason any of this exists, and its creator deserves the support.

## Under the Hood

The site is intentionally boring in the best way: **Astro 5** static pages with small interactive islands, served from the edge on Cloudflare Pages, with pack media pre-processed and delivered from object storage. All the interesting work happens client-side — the Web Audio API drives playback and mixing, the browser's own encoder renders the final video faster than real time, and nothing about your recording session ever touches a server.

That architecture is why Choicer Voicer feels the way it does. Static pages mean the library is fast and indexable; client-side processing means the whole product can stay free, private, and ad-free, because there is no per-player server bill to recover.

## Getting Started

1. Open [choicer voicer](https://choicervoicer.co/) in any recent browser.
2. Allow microphone access when prompted — the [mic help page](https://choicervoicer.co/mic-help/) covers every browser's permission quirks.
3. Pick a scene, record your lines, chase a better score, and export your dub.

That is the entire onboarding. No account, no tutorial gate, no payment step.

## FAQ

**Is Choicer Voicer free to play?**
Yes. All scenes, scoring, and video export are free, with no watermark and no ads. The desktop game is a separate paid product by its own creator.

**Do I need to download anything?**
No. Everything runs in the browser, and your voice recordings never leave your device.

**Can I play Choicer Voicer on my phone?**
Yes. Any phone or tablet with a microphone and a recent browser works; video export needs a current browser version.

**Do I need a good microphone?**
No. Scoring rewards timing and rhythm, not audio fidelity — earbuds are plenty.

**What do I need to play Choicer Voicer online?**
A browser from the last couple of years and any microphone. A laptop mic or wired earbuds are perfectly fine.

**Is this the official site?**
No. It is an independent fan project. Every dub pack credits its creator, and the site actively encourages players to buy the original game.

## Credits and Links

- **Play now:** [choicer voicer](https://choicervoicer.co/) — the free browser dubbing game
- **Original game:** [*The Choicer Voicer* by YeahMaybe on itch.io](https://yeahmaybe.itch.io/the-choicer-voicer)
- **Dub pack community:** [GameBanana](https://gamebanana.com/games/20674), where every featured pack lives and every creator is credited

This project stands on the work of the original developer and the pack-making community. If you enjoy it, support them — and if you just want to make a friend laugh with a terrible line reading, the stage is one click away.
