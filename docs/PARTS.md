# Parts

Prices are indicative, from the sources in `SOURCES.md`, and change often. "Verified" means I confirmed the part fits this job; it does not mean I confirmed today's price or stock.

## Confirmed direction

| Part | Role | Source / status | Indicative price |
|---|---|---|---|
| Apple HomeView (tabletop) | The device being carried | On sale in India since 13 Nov 2026 | ₹39,900 |
| RPLIDAR A1M8-R5 | 360° lidar — direction + obstacle avoidance | **Already owned (sister's unit).** Confirm it spins and scans before relying on it | ₹0 |
| 6-inch brushless hub motors ×2 | Drive wheels | Zbotic / Robodo list 24V–36V units | ~₹3,000–3,500 each |

The A1M8-R5 is rated 0.15–12 m, ≥8000 samples/s, scan rate adjustable 2–10 Hz. More than enough for a room. Run it near 10 Hz for faster reaction. Blind below 15 cm, so add a bumper or short-range sensor at the front.

## Still to source and price

| Part | Role | Note |
|---|---|---|
| UWB module | Distance to my iPhone / Watch | Qorvo DWM3001CDK is interoperable with Apple's U1/U2 chip and ships with free iOS apps, firmware and sample source. No Indian stockist found yet — likely an import. |
| Brushless motor controller | Drive the hub motors | Not yet sourced in India. |
| Raspberry Pi (5 or similar) | Main brain | Widely available in India. |
| Microcontroller (ESP32 / Arduino) | Motor control | Widely available. |
| USB-C PD power bank | Power the HomeView (≥20 W, 30 W better) | Must confirm the HomeView runs off one — see open questions. |
| Motor/electronics battery pack | Power the drive | Size after motor choice. |
| Aluminium T-slot extrusion + brackets | Mast | Local. |
| Wheels / castors, chassis plate, fasteners | Base | Local. |
| Bumper switch or short-range sensors | Blind-spot and drop protection | Local. |

## Notes

- If I carry the phone or wear the Watch, no separate UWB tag is needed — but that depends on the background-ranging test. A small UWB tag is the fallback.
- Swapping the A1 lidar for a newer RPLIDAR C1 later would not mean rewriting code — the C1 keeps the A-series sampling protocol.
