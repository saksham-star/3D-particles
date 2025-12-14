# 3D-particles
Project Title: Neural Dust – Gesture-Controlled 3D Particle Morphing

Overview
Neural Dust is an interactive web experiment that merges Computer Vision with WebGL 3D rendering. It creates a living digital sculpture that responds physically to the user's hand movements in real-time. By holding up a hand to the webcam, users can telekinetically control a swarm of 15,000 glowing particles, morphing them into complex mathematical shapes (like planets, hearts, or flowers) simply by changing the number of fingers they extend.

How It Works (The Architecture)
The application runs entirely in the browser (client-side) using a pipeline of three distinct stages:

Input (Computer Vision):
The webcam feed is processed by Google MediaPipe, a machine-learning framework.
It detects 21 specific 3D landmarks on the user's hand (knuckles, fingertips, wrist) with high precision.
The system analyzes these landmarks to calculate Gesture Logic (how many fingers are open) and Spatial Logic (where the hand is in 3D space).

Processing (The Math Engine):
Based on the gesture detected (e.g., "Peace Sign"), the engine selects a specific mathematical formula (Parametric Equation).
It calculates target coordinates (x,y,z) for every single particle to form the desired shape.
It uses Linear Interpolation (Lerp) to calculate the path between the particle's current position and its target position, creating a fluid, swarm-like transition effect rather than a hard cut.

Output (WebGL Rendering):
Three.js renders the 15,000 particles using BufferGeometry for high performance.
The scene is updated 60 times per second, rotating the entire particle cloud to match the user's hand tilt and roll.

Key Features
👆 Gesture Recognition: Detects distinct hand states (Fist, Pointing, Peace Sign, Open Palm) to trigger shape changes.
🌌 5 Unique Visual Modes:
Heart: Uses parametric math to form a 3D volume heart.
Saturn: Generates a spherical planet with a tilted, flat ring system.
Flower: Uses Phyllotaxis algorithms (sunflower spirals) to arrange particles naturally.
Fireworks: A chaotic, expanding cloud of particles.
Black Hole (Collapse): A physics-simulation effect where all matter is sucked into a singular point.
🎥 Augmented Reality Feel: The particle system tracks the hand's position on the screen, creating the illusion that the user is holding or rotating the hologram.
⚡ Zero Latency: Runs optimized on the GPU, allowing for smooth 60FPS animation even with thousands of particles.

Tech Stack
Language: JavaScript (ES6+)
3D Engine: Three.js (WebGL)
AI/ML: MediaPipe Hands (TensorFlow-based solution optimized for web)
Styling: HTML5 & CSS3
Potential Use Cases
Interactive Art Installations: Museums or galleries where visitors control digital art without touching a screen.
Web Design: A "Hero Section" background that reacts to the user's mouse or webcam.

Education: Visualizing mathematical formulas or physics concepts (like gravity or atomic structures) in a fun, interactive way.

Why This Project is Challenging
This project requires bridging two very different disciplines: 3D Graphics programming (understanding vertices, buffers, and vectors) and AI interaction (normalizing coordinate systems and interpreting vague sensor data into binary triggers). Creating the "smooth" transition where particles fly to their new spots requires implementing custom physics logic rather than using pre-made animations.



