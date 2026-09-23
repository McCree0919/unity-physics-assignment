# In-Class Unity Physics Assignment

## Overview

This scene demonstrates Rigidbody physics, force-based movement, collisions, triggers, tags, and a success event. The Actor moves toward the Target, and the goal is for the Payload to enter the Goal Zone.

## Scene Objects

- Floor
- Actor
- Target
- Payload
- Goal Zone
- Camera
- Light

## Implementation

- The Actor uses a Rigidbody. `InClassActorController` applies force toward the assigned Target along the ground plane.
- The Payload must use the `Payload` tag so the Goal Zone can recognize it.
- The Goal Zone uses a trigger collider and the `InClassGoalZone` script.
- Only an object tagged `Payload` can trigger success. On its first entry per run, the script records the elapsed time since the run started and fires `PayloadSucceeded` with that time in seconds.

The saved scene includes the Actor's assigned Target reference, the Payload's `Payload` tag, and the Goal Zone collider with Is Trigger enabled.

## Experiment

I changed the Actor's Linear Damping and compared its movement.

### Test 1: Linear Damping = 0

- The Actor retained more velocity and felt more slippery.
- It often overshot the Target.
- It continued moving and rotating more after collisions.

### Test 2: Linear Damping = 3

- The Actor slowed down more quickly and felt more controlled.
- It overshot the Target less.
- It settled faster after collisions.

### Observation

In my tests, Linear Damping of 3 made the Actor easier to control and helped it settle sooner. With Linear Damping of 0, it kept more momentum and overshot more often.

## Running the Project

1. Open the project in Unity (project version: `6000.6.2f1`).
2. Open `Assets/Scenes/inClassAssignment1.unity`.
3. Press Play.
