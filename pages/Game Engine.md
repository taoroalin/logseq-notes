---
title: Game Engine
---

## Can I outline how a game engine works?

## Some details: This is a 3D game. It uses an interitence-like thing, not ECS.

## Whole Game
### Startup
#### OS does run_exe

#### process starts

#### included DLLs are mmaped into your memory

#### Loads any files that are required but not part of scene

#### {{embed ((7c063065-c222-496f-8b5c-169d4738293a))}}

### Running
#### Main Loop
##### 

### Shutdown

## Load Scene
:PROPERTIES:
:ID:7c063065-c222-496f-8b5c-169d4738293a
:END:
### 

## Scene
### How is scene stored?
#### Unity scene format: YAML, tons of graphics default setting stored, files referenced by FileID, there are also GUIDs, 
##### gameobject, transform, and monobenavior are all stored next to each other, instead of gameobject on top. on top is just !u!_id__

##### 
