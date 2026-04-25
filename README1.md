# Retro 2D Slot Machine

## 🎰 Game Overview

This project is a classic, 16-bit arcade-style slot machine built using the Unity 2D engine and was made by Dnyanesh Mote. It features a complete gameplay loop where players can place bets, pull the lever, and watch the reels spin to land on randomized outcomes. The project emphasizes clean code architecture, separating the visual frontend (UI, animations, masking) from the backend mathematical logic (RNG, win evaluation, payouts).

**Key Features:**

* **Winning Logic:** Evaluates payouts based on matching symbols across all three reels.
* **Smooth Reel Animations:** Utilizes a seamless looping vertical scroll system to mimic the physical weight and momentum of real slot reels.
* **Clean Symbol Display:** Hides off-screen symbols using Unity's `RectMask2D` for crisp, arcade-perfect framing.
* **Randomized Outcomes:** Implements a robust Random Number Generator (RNG) to dictate final symbol positions fairly.

## 🚀 Instructions to Run WebGL Build

To play the game directly in your web browser without installing Unity:

1. Download and extract the provided `WebGL\_Build.zip` folder.
2. If you are using a modern browser (like Chrome or Edge), security policies may prevent running local files directly. You can run it easily by:

   * **Using Python:** Open your terminal/command prompt in the extracted folder and run `python -m http.server 8000`. Then open your browser and navigate to `http://localhost:8000`.
   * **Using VS Code:** Open the folder in VS Code and use the "Live Server" extension to launch `index.html`.
   * **Hosting:** Alternatively, upload the unzipped folder to a free hosting service like GitHub Pages or Itch.io.
3. Click the **Lever** to spin the reels, or use the **Bet** buttons on the right to adjust your wager!

## 🧠 Thought Process \& Approach

Approaching this as part of my final-year engineering portfolio, my primary technical goal was to establish a highly modular and organized foundation. I wanted to ensure the architecture strictly separated the visual presentation (the "Body") from the data and logic (the "Brain").

Building upon my ongoing interest in game development and the systems I designed for previous projects, such as *Dharma-choice-based-gameplay*, I structured the game around Object-Oriented Programming principles. The `SlotGameManager` acts as the central hub, completely isolated from how the graphics are rendered. It calculates the random results *first*, and then delegates the animation commands to the individual `ReelController` instances.

To achieve the "infinite scroll" illusion for the reels, I opted against generating hundreds of UI elements. Instead, I used a lightweight looping algorithm that detects when a symbol passes the bottom threshold of the `RectMask2D` and instantly snaps it back to the top. This keeps the performance cost extremely low and the hierarchy clean. The use of the 2D Core template and Canvas scaling ensures the machine maintains perfect visual fidelity on any screen size.

