# Plot Stop

An *X4: Foundations* mod that removes the DLC story plots so their regions and gamestarts are available without playing through the storylines.

## Compatibility

### X4 Upgrade Project – Cradle of Humanity (`xup_dlc_terran`)

Compatible. That mod's `md/terran_accelerator_reboot.xml` signals and checks cues in the Terran prelude story (`md.Story_Terran_Prelude`), which Plot Stop removes. To keep its references resolving without errors, Plot Stop:

- keeps two empty stub cues in `Story_Terran_Prelude`:
  - `Prelude_Teladi_Trespassing` — listens for xup's signal and does nothing.
  - `Prelude_Approach_Cutscene_Started` — completes at start, so xup's load-game handler cancels cleanly.
- declares an optional dependency on `xup_dlc_terran`, so Plot Stop loads after it when both are installed. Without xup, Plot Stop works as normal.

The prelude plot itself stays removed. The stub cue names must not change.
