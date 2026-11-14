# Design

This is the current thinking. Nothing here is final until the tests in `OPEN-QUESTIONS.md` pass.

## Overall shape

A two-wheel differential-drive base with castors, a mast rising from the base, and the HomeView on top. Batteries sit low in the base for stability.

## 1. Drive base

Two driven wheels, one each side, plus one or two castors for balance. Differential drive means the robot turns on the spot by running the wheels in opposite directions. That same turning is how it aims the HomeView left and right, which the screen cannot do on its own.

Wheels around 6 inches so it clears door thresholds and rug edges.

## 2. Following

Two parts working together:

- **Distance** comes from UWB (ultra-wideband) ranging between a module on the robot and the iPhone or Apple Watch I carry. UWB works through walls and around corners, where a camera would lose me.
- **Direction** comes from the lidar. With the phone in my pocket the UWB gives distance only, not bearing, so the robot cannot get direction from UWB alone. The lidar builds a 360° picture of the room, and the robot matches "the person is 2.3 m away" from UWB to a person-shaped object at 2.3 m in the lidar scan.

The lidar also handles obstacle avoidance.

Why not the HomeView's own camera: Center Stage keeps me framed in a call, but only within the camera's field of view. It cannot turn the robot or see me once I leave the room.

## 3. Mast

An aluminium extrusion (e.g. 2020 or 3030 T-slot) putting the screen at seated eye level. Batteries low in the base keep the centre of gravity down so it does not tip when it stops or turns.

## 4. Power — two separate batteries

- **One pack for the HomeView**, through a USB-C PD power bank. The HomeView has no battery and draws power over USB-C; its stated minimum is a 20 W supply, and it ships with a 30 W adapter.
- **One pack for the motors and electronics.**

Keeping them separate means motor current spikes and electrical noise never reach the Apple device.

## 5. Brain

- **Raspberry Pi** for the lidar, the follow logic, and talking to the UWB module.
- **A microcontroller** (e.g. an ESP32 or an Arduino-class board) driving the motor controller, taking commands from the Pi.

## 6. Tilt

Manual to start — set the screen angle by hand. A small servo cradle can be added later for app-controlled tilt.

## Open design decisions

- **Direction method.** Lidar-fusion (one UWB module) vs two UWB modules on the robot computing bearing from the difference. Lidar-fusion is the plan; it needs the follow logic written and tuned.
- **Motor + controller pairing.** Hub motors are quiet but need a brushless controller. Geared DC motors with encoders are simpler but noisier on a call. Not yet decided.
- **Drop protection.** Not needed if it truly never reaches a stair, but cheap insurance if it might.
