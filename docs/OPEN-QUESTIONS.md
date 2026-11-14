# Open questions and tests

These have to be settled before spending beyond the first test board. In priority order.

## 1. Does the iPhone / Watch work as an always-on beacon?

The risk: Apple's background UWB ranging needs the accessory paired over Bluetooth LE, and I have not confirmed the phone keeps ranging with the screen off and in my pocket — or that the Watch ranges with the wrist down and screen asleep. One old forum report had an Apple Watch ranging only sometimes.

**Test:** Buy one Qorvo DWM3001CDK. Run Qorvo's free background app with the phone locked in my pocket, and walk between rooms for 30 minutes. Then repeat with the Watch, screen asleep. See which keeps reporting distance.

- Phone half uses Qorvo's free App Store apps.
- Watch half means building Apple's sample code myself — I have not confirmed Qorvo ships a watch app.

**Fallback if it fails:** a dedicated UWB tag in my pocket. Nothing else in the design changes.

## 2. Does the HomeView run off a USB-C power bank?

The risk: I have not confirmed the HomeView runs from a power bank, or its actual power draw. It needs constant wired power and has no battery.

**Test:** Before building anything, run the HomeView on a table from a USB-C PD power bank (≥20 W). Confirm it powers up and stays up.

## 3. Direction method: lidar-fusion or two UWB modules?

Plan is one UWB module plus lidar fusion. Not yet confirmed an iPhone will hold two UWB sessions reliably in the background, which is what the two-module approach would need. Decide after test 1.

## 4. Motor and controller choice

Hub motors (quiet, need a brushless controller) vs geared DC with encoders (simpler, noisier). Noise matters because it is for calls. Not yet sourced a brushless controller in India.

## 5. Drop protection

Only needed if the robot can reach a stair. No stairs in scope, but confirm there is no edge it could roll off before skipping this.

## Known UWB caveat

Ultra-wideband is switched off by Apple in some countries for regulatory reasons. India is **not** on that list, so this is fine here.
