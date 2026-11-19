# Autonomous Chaos Sim

A WebGL-based social simulation prototype (Sims-like) built with Vibe Coding and Devin.

## 🧠 Core Mechanic: Autonomous Chaos

The game is driven by an **Event-Driven Finite State Machine (FSM)**. It is not just a 3D box mover; it's a social sim where NPC traits dictate emergent chaos.

### How it works:
1. **Base State Loop:** NPCs cycle through Idle, Moving, and Interacting with the environment.
2. **Trait Modifiers:** Every NPC has distinct traits (e.g., `Neat`, `Slob`).
3. **The Hook (Autonomous Chaos):** When a `Slob` NPC interacts with an object (e.g., leaves a mess), it broadcasts a `MESS_CREATED` event via a global Event Bus.
4. **Stress Debuffs:** If a `Neat` NPC receives this event, their FSM triggers a `stress_debuff` (+10 stress/sec). 
5. **The Game Loop:** The player must manage the environment to prevent NPCs from reaching a `Breakdown` state. 

## 🛠️ Tech Stack
- **Framework:** Vite + React (TypeScript)
- **3D Rendering:** Three.js via `@react-three/fiber` (R3F) & `@react-three/drei`
- **State Management:** Zustand (handling decoupled environment & NPC states)
- **Event Bus:** `mitt` (for highly scalable pub/sub event broadcasting)

## 🗺️ Roadmap (First Playable Build)
- [ ] Day 1-2: R3F Canvas, grid setup, basic placement.
- [ ] Day 3-4: Zustand stores, FSM implementation, NPC spawning.
- [ ] Day 5: Trait Modifier system & Stress Debuff logic.
- [ ] Day 6: UI implementation & Polish.
- [ ] Day 7: Deploy to Vercel and ship the live link.
