# Changelog

## 1.2.0

### Summary

Bridge mode can now send the icons and names of modded blocks, items and mobs to the Discord bot, so statistics show them properly

### Added

- Added sending of icons and names (English and French) for blocks, items and mobs from other mods, read from their files on the server when the bot asks for them
- Added the `[bridge] modIcons` setting (enabled by default), added to the config automatically
- Added the icon sending state to `/portalsync status`
- Added the `item_assets` capability and the `assets_request` / `item_assets` messages to the public protocol

### Notes

- Available for Forge 1.16.5, 1.19.2, 1.20.1, 1.21.1, Fabric 1.16.5, 1.19.2, 1.20.1, 1.21.1 and NeoForge 1.21.1
- Compatible with bots that do not support `item_assets` yet: nothing extra is sent to them
- On Forge and NeoForge, `modIcons` is also available in the loader config file

## 1.1.0

### Summary

Bridge mode now sends every player statistic line instead of a short summary

### Added

- Added sending of every statistic line: blocks mined, mobs killed, items crafted, used, broken, picked up and dropped, deaths by mob and general statistics, modded entries included
- Added a limit of 1,000 lines per category, one message per category (always under 64 KB)
- Added the `[bridge] fullStats` setting (enabled by default) to send only the summary when disabled
- Added the `stats_full` capability and the `player_stats_full` message to the public protocol

### Notes

- Available for Forge 1.16.5, 1.19.2, 1.20.1, 1.21.1, Fabric 1.16.5, 1.19.2, 1.20.1, 1.21.1 and NeoForge 1.21.1
- Compatible with bots that do not support `stats_full` yet: only the summary is sent to them
- On Forge and NeoForge, `fullStats` is also available in the loader config file

## 1.0.0

### Summary

First public release of PortalSync, a server-side mod that links a Minecraft server to Discord

### Added

- Added in-game chat relay to Discord, with each player's name and head
- Added join, leave and first join messages
- Added advancements, deaths with the real death message and boss kills (configurable list, modded bosses included)
- Added server online and offline messages
- Added staff command logs (disabled by default): all commands (`*`) or a list, optional private messages (`privateMessages`), login and password commands are never sent
- Added Webhook mode with up to 3 channels (chat, events, logs)
- Added Bridge mode to connect to a Discord bot (Aelyx on approval, or your own bot through the [public protocol](https://cmloxy.fr/portalsync/protocole/)), with Discord messages shown in game, server status (players, TPS, memory, mods) and player statistics
- Added full configuration in `config/portalsync-common.toml`: events, texts and language (English or French)
- Added protection against mentions from the game (`@everyone`, `@here`, roles)
- Added `/portalsync status` and `/portalsync reload` commands (operators)

### Notes

- Available for Forge 1.16.5, 1.19.2, 1.20.1, 1.21.1, Fabric 1.16.5, 1.19.2, 1.20.1, 1.21.1 and NeoForge 1.21.1
- Server-side only: players do not need to install anything
- Also works in singleplayer, with no impact on TPS
- Messages blocked by a mute mod are not sent to Discord
