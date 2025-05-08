# XR BeatSaber RipOff VR Game

A BeatSaber-inspired VR rhythm game built in Unity using the Meta XR SDK. Punch on-coming diamonds to the beat, dodge obstacles, and survive until the song ends!


---

## Features

- **Rhythm-driven spawning:** Shapes and obstacles spawn on the beat.  
- **Two-hand color matching:** Punch teal-colored diamonds with your right controller, coral-colored diamonds with your left.  
- **Variable breakage:** Weak, moderate, or strong punches break diamonds into small, medium, or large pieces.  
- **Scorekeeping & Win/Lose states:** Earn points for correct punches; game ends on score ≤ 0 (lose) or when the song finishes (win).  
- **Multiple levels & lobby menu:** Select from three levels via the lobby scene.  
- **Full haptic feedback:** Controller vibrations for hits, misses, and collisions.  
- **Polish:** Fog effects, explosion forces, audio cues, and customizable presets.  

---

## Scenes

### 1. Lobby  
![Lobby Scene](assets/images/lobby_scene.png)  
- Main menu with background audio.  
- Three diamond “buttons” inside a vertical pipe; punch to select level. 

### 2. Level Template  
![Pipe Environment](assets/images/pipe_environment.png)  
- Giant pipe environment with ground/platform models inside.  
- Fog effect applied via **Window → Rendering → Lighting → Environment**.  
- Duplicate template for each level; customize music/fog color. 

---

## Audio & Beat Sync

- **AudioSpectrum** script attached to `OVRCameraRig` computes spectrum from `AudioSource`.  
- **AudioSyncer** base class calculates beats; extend via **AudioSyncSpawn** (spawns shapes) and **AudioSyncScale** (scales pipes).  
- Override `OnBeatEvent()` to hook into beat callbacks. 

---

## Haptic & Visual Feedback

- Haptic vibration on:
  - Correct punch  
  - Wrong punch  
  - Block collision  
  - Hand-to-hand bump  
- Visual polish: explosion forces on broken pieces, dynamic scaling of environment frames. 
---

## Installation

1. Clone this repo:  
   ```bash
   https://github.com/MondayMonster/BeatSaber-VR-Ripoff.git
   cd BeatSaber-VR-Ripoff
