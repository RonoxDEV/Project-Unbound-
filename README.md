🚀 Project Unbound: Supreme Optimization (PRE-ALPHA)
⚠️ WARNING: EXPERIMENTAL BUILD ⚠️
This is a PRE-ALPHA release. It contains bugs, instability, and experimental code. DO NOT use this on your main survival world or a production server without a backup.

Goal of this release: This version is a "Proof of Concept" released specifically for developers and technical enthusiasts to provide feedback, suggestions, and stress-test data.

🛑 The Problem
Minecraft Vanilla is built on 15-year-old architecture. It runs on a single main loop: if a zombie thinks too hard, your frame rate (FPS) dies. This is the Single-Thread Bottleneck.

⚡ The Solution: Project Unbound
Project Unbound is a surgical rewrite of the game's Kernel. We replaced the Mojang main loop with a custom Multithreaded Scheduler designed to leverage the modern power of Java 21.

🛠️ Key Features (V1.0 - Experimental)
1. 🔓 Decoupled Update Loop (Unlocked FPS)
In Vanilla, FPS is tied to TPS. If the server lags, your screen lags. Unbound separates them.

Result: Even if the internal server drops to 5 TPS under heavy load, your game remains visually fluid at 144+ FPS. You retain full control of your movement.

2. 🧠 D.A.B. (Dynamic Activation of Brains)
Why calculate the AI of a zombie 100 blocks away? The D.A.B. system analyzes entity relevance in real-time.

Green Zone (<32 blocks): Full AI. Vanilla behavior.

Red Zone (>32 blocks): "Lobotomy". The entity becomes dormant. It exists, acts as a physical object, but stops consuming CPU for logic.

Gain: Reduces entity-related CPU load by ~80%.

3. ⏳ Time Dilation (Anti-Freeze)
No more crashes when you explode too much TNT. Instead of freezing your screen, the engine activates Time Dilation.

The simulation enters "Bullet Time" (Slow Motion) to allow the CPU to catch up.

The game slows down, but the rendering remains smooth. It adapts instead of crashing.

4. 🖥️ Cyberpunk HUD
Press F3 isn't enough. We have a custom overlay.

Real-time display of Active vs. Lobotomized (Sleep) entities.

Visual proof of the optimization logic.

🐛 Current State & Known Issues
This is where I need you. As a Pre-Alpha, expect the following:

Visual Glitches: Some entities might jitter or float incorrectly due to interpolation changes.

Mod Compatibility: Likely breaks compat with other heavy optimization mods (Sodium/Lithium usually fine, but core-logic mods may conflict).

Physics: Entity collisions might behave weirdly during "Time Dilation".

👉 I am looking for suggestions on:

Scheduler stability.

Handling mod conflicts.

Aggressiveness of the D.A.B. system.

⚙️ Technical Requirements
This mod pushes the JVM to its limits.

Minecraft: 1.21.1

Loader: Fabric

Java: Java 21 REQUIRED

JVM Arguments: -XX:+UseZGC -XX:+ZGenerational

📦 Installation
Install Fabric Loader for Minecraft 1.21.1.

Ensure you are running with a Java 21 Runtime.

Drop ProjectUnbound-1.0-alpha.jar into your mods folder.

Launch. Break things. Report back.

Experimental project created by Ronox_.
