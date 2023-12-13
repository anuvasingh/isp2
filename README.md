﻿# Blackguard
Blackguard is a roguelike-inspired, 2D ASCII adventure game. It will be set in a fantasy environment with a mix of premade and randomly generated levels and biomes. The player can explore and complete quests, defeat bosses, and interact with in-game characters and shopkeepers.

### For instructions on how to set up the programming environment, look [here](https://github.com/ppebb/isp2/blob/main/docs/setup.md)

## Architecture Design Document
The architecture of this project centers around a single-threaded game loop synchronized at 60 ticks per second. There will be a separate thread to poll for input and a separate thread for drawing text to the screen.

The project will follow an OOP design structure, with base classes for things such as tiles, UI elements, entities, and the player, of which instances will be made and stored in a central list to be updated 60 times a second.

Entities and the player will each have an Update method that will handle movement and AI for each entity present on the screen and a Draw method that handles how it is rendered to the screen, along with methods to handle interactions with the players and dialogue.

Each screen will be implemented off of a base class that defines how it looks and the functionality of each element (buttons, text, etc.), where each screen will be swapped based on user input.

World generation will be implemented in a chunking system, with each chunk being saved and loaded to disk based on what region of the map is loaded.

Saves will be handled using a JSON format to allow players to pause and resume without leaving the game open.

## Coding standards and guidelines
Ensure that all code is tested before committing, and ensure you have a proper formatter run based on the configuration files in the repository.

## Setting
- Medieval Fantasy
- Magic
- No Guns or real advanced Tech

## Features
- Main Menu
- Health Bar
- Mana Bar
- Sprint Bar
- Different biomes
- Different enemies
- Status Conditions / Window
- Real-time Movement
- Perma Death
- Upgrades to Equipment
- Adjustable stats
- Turn-Based combat
- Different Starting classes and races
- Projectiles
- Color text
- [Nerd Font](https://www.nerdfonts.com/)
- Area Bosses
- Final Boss
- Experience system / Leveling System
- Global scoreboard

## Databases
The global database for the leaderboards will be interfaced with a simple JSON API that will return global scores as well as an endpoint to upload scores. The database will be a simple Postgresql table with columns for score, playtime, % completion, etc.
