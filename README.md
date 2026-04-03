# [RealRim] Heaters

Author: SIGSEGV111

Package ID: `sigsegv111.realrim.heaters`

License: `AGPL-3.0`

Repository: <https://github.com/SIGSEGV111/RealRimHeaters>

## What this mod does

This is an XML-only RimWorld 1.6 balancing mod that increases the active power usage of electrical room heaters and reduces their idle draw to a near-standby value.

The balancing anchor is the vanilla heater request:

- 21 heat-per-second -> 2500 W active;
- 5 W idle.

Everything else is scaled linearly from that point for active draw:

- 40 heat-per-second -> 4762 W active;
- 75 heat-per-second -> 8929 W active;
- 400 heat-per-second -> 47619 W active.

Idle draw for all supported heater tiers is normalized to 5 W.

## Included coverage

- Vanilla Heater;
- WallStuff Wall Heater;
- any other electrical temperature building using the standard RimWorld power + temp-control comp setup and one of the supported heat-push tiers above.

## Soft compatibility

There are no hard dependencies.

The patch file uses `PatchOperationConditional`, so missing targets are ignored cleanly. Optional `loadAfter` entries are included for known heater-related mods so that, when present, their defs are more likely to exist before these patches run.

## Installation

Drop the mod folder into your RimWorld `Mods` directory and enable it in the mod list.
