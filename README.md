# HomeView Follow-Me Stand

A wheeled, battery-powered stand for an Apple HomeView that follows me from room to room, so I can stay on a FaceTime call while I move around the house.

## What it does

- Carries a HomeView on a mast at seated eye level.
- Runs off its own batteries, so no trailing power cable.
- Turns to face me (the HomeView screen itself only tilts up and down, it does not swivel).
- Follows me as I walk to another room.

## How following works

I carry an iPhone or wear an Apple Watch. The robot has a UWB module that measures how far away that device is. A lidar on the base builds a map of the room, avoids obstacles, and works out which direction I am in. The robot drives toward me and stops at a set distance.

No stairs in scope — single floor only.

## Status

Idea stage. Nothing bought or built yet. The open questions in `docs/OPEN-QUESTIONS.md` have to be answered by testing before any money is spent.

## Documents

- `docs/REQUIREMENTS.md` — what it has to do.
- `docs/DESIGN.md` — how it is put together and why.
- `docs/PARTS.md` — parts, Indian sources, prices, and what is still unverified.
- `docs/OPEN-QUESTIONS.md` — the unknowns and the tests that settle them.
- `docs/SOURCES.md` — every link the research rests on.
