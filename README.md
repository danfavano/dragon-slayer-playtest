# Dragon Slayer Playtest

A free Windows prototype of an ASCII, turn-based RPG built in Unity. Explore Ashford, talk to its townsfolk, and follow leads into generated adventures.

This repository hosts **downloads and player instructions only**. The Unity project and game source are not included. This is an unfinished experiment, not a finished commercial game.

## Download and run

1. Open the [latest release](https://github.com/danfavano/dragon-slayer-playtest/releases/latest).
2. Download `DragonSlayer-v0.1.0-windows-x64.zip` under **Assets**. Do not download GitHub's automatic "Source code" archives; those contain only this repository's documentation.
3. Extract the entire ZIP into a folder you can write to. Keep `DragonSlayer.exe`, `DragonSlayer_Data`, and all supporting files together.
4. Run `DragonSlayer.exe`. You do not need Unity or a separate .NET installation to play.

The build targets 64-bit Windows. Other operating systems are not supported by this release. Minimum hardware requirements have not been established.

## Local AI setup

The game can run without a local model using fallback dialogue and adventures. To try the intended AI-driven experience:

1. Install [LM Studio](https://lmstudio.ai/). This [setup video](https://www.youtube.com/watch?v=UngVdAsQEiU) introduces installation and the local server.
2. Download and load **Gemma 4 E4B**, with model identifier `google/gemma-4-e4b`.
3. Set a context length of at least **8,192 tokens**, if supported by your model and available memory.
4. Start LM Studio's local OpenAI-compatible server on port **1234**. The game uses `http://127.0.0.1:1234/v1` and the model identifier above.
5. Start or restart Dragon Slayer after the server is running. Keep LM Studio running while playing.

This prototype does not provide an in-game endpoint or model selector. A different port or incompatible model identifier can cause it to use fallback content. Model weights and LM Studio are not bundled; their own terms apply.

The game probes the server at startup and reports storyteller availability in its status/chronicle. AI requests can take time or fail; fallback content is not evidence that the model connected successfully.

## Controls

| Action | Control |
|---|---|
| Move around town or a dungeon | WASD or arrow keys |
| Speak to townsfolk or use the east gate | Move onto the marked town tile and follow the prompt |
| Answer a numbered prompt | 1 or 2, as displayed |
| Send a conversation message | Type in the conversation input and press Enter |
| Leave a conversation | Escape or 3 |
| Attack / defend / flee in combat | 1 / 2 / 3 |
| Close the game | Alt+F4 or the window close button |

Follow the on-screen prompts. Combat is turn-based; conversations and adventure generation may wait for the local model.

## Known limitations

- Combat, balance, loot, and progression are prototype systems.
- Local model performance depends on your hardware, context settings, and model configuration.
- Generated stories may repeat ideas or produce incomplete responses.
- Supported enemies and layouts are limited; generated descriptions do not create new engine capabilities.
- This release is not a guarantee of future features, compatibility, or a commercial release.

## Troubleshooting and feedback

If the game will not launch, confirm you extracted the complete ZIP and kept its supporting files together. If AI is unavailable, check LM Studio's loaded model, port, and server status, then restart the game.

Use [Issues](https://github.com/danfavano/dragon-slayer-playtest/issues) for bugs and playtest feedback. Include the version, Windows version, reproduction steps, and whether LM Studio was running.

The game writes Unity player logs and narrative trace logs. Narrative traces can include your conversation text and model replies. Review and redact logs before sharing them publicly.

## License

The prototype is proprietary, not open source. It is free for personal playtesting. Gameplay videos, streams, screenshots, and reviews are permitted, including monetized coverage. Reselling or redistributing the game build is not permitted; link people to the official release instead.

See [LICENSE.txt](LICENSE.txt) for the prototype terms and [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt) for bundled component notices. Third-party permissions remain governed by their respective licenses.
