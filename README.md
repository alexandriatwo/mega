# Omega

This repo is code for a machine learning social "turing" test run on Clubhouse.

It's a conversational bot that leverages GPT-3 to reply contextually to speakers in Clubhouse topics. It uses Google Speech to translate peoples audio responses into text. ("speech to text") The text is then sent to GPT-3 with a default prompt (personality). The bot also contains multiple variations of "personalities", it tries to redirect responses from speakers in Clubhouse to an appropriate personality. In the GPT-3 prompt this codebase is configured to inject primitive "memories" that are generated by calls to GPT-3 through it's classification methodology. (in some lazy attempt to make the "personalities" evolve over time)

Once GPT-3 replies with a textual response, it triggers Omega to do "text-to-speech" that plays the audio stream into Clubhouse. The output voice is generated by Google speech and configured to use the "personalities" speech profile. The file is saved, then streamed back through the local computers audio device routing through the virtual audio device. (VB - Audio Control)

At this point, people in clubhouse should be able to have a back and fourth with GPT-3.

## Getting Started

```
git clone git@github.com:thomasdavis/omega.git
npm i
pm2 start ecosystem.config.js
// The bot crashes a lot for various reason so we use pm2 to keep it restarting
// So it starts as a long running process, to see the logs;
pm2 logs

```

## Requirements

Install VB Audio Control
https://vb-audio.com/Cable/

Clubdeck
https://www.clubdeck.app/

M Player
https://mplayer.en.softonic.com/

Todo:

- [ ] Speech time
- [ ] Delineate between different voices
- [ ] Store memories and messages in a database
