# Open-source foundation review: teamBUDDY Action RPG

## Decision

There is no official open-source source code for Rune Factory that can simply be copied into teamBUDDY. Rune Factory is a proprietary franchise. We should reuse genre patterns (farming + real-time combat + village life), not its code, characters, art, music, names, dialogue, or other protected assets.

For a browser/Three.js reference, we reviewed [Veilspire](https://github.com/Lunaneco/veilspire), an original browser-based action RPG published under the MIT License. It demonstrates a procedural 3D world, combat, enemies, quests, equipment, crafting, local saves, and touch controls. Its camera and spell-focused mechanics differ from teamBUDDY's intended top-down low-poly farming RPG, so a wholesale replacement would be the wrong fit.

Other projects reviewed:
- [OpenAcre](https://github.com/OpenAcre-Project/OpenAcre) — Godot farming/survival simulator under GPL-3.0; useful for simulation ideas, but a different engine and a copyleft license.
- [Sulfur & Sunflowers](https://github.com/CapsCollective/sunflower) — Godot farming game; its README distinguishes MIT-like code licensing from proprietary game content, so assets/content must not be copied.
- [Farming RPG (Phaser)](https://github.com/Blockost/farming-rpg) — a 2D Phaser project, not a drop-in Three.js base.

## Integration approach

1. Keep the existing index.html game intact while experimenting.
2. Add a separate, original Three.js top-down action prototype under prototype/.
3. Use Veilspire as a reference for browser RPG architecture and touch-control patterns, not as a wholesale code import.
4. Once the prototype is tested, migrate systems into modules and integrate the existing teamBUDDY maps, NPCs, farming, cultural foodways, and Pocong character.
5. If any Veilspire source code is copied in a later step, retain its MIT copyright and license notice in the relevant distribution and document the exact files/changes.

## License and attribution

Veilspire's repository states that it is MIT-licensed and its LICENSE file names Copyright (c) 2026 Lunaneco. MIT reuse requires preserving the copyright and permission notice in copies or substantial portions. This prototype is newly authored for teamBUDDY and does not include copied Veilspire source or assets.

Open-source references:
- Veilspire repository and README: https://github.com/Lunaneco/veilspire
- Veilspire MIT license: https://github.com/Lunaneco/veilspire/blob/main/LICENSE
- OpenAcre: https://github.com/OpenAcre-Project/OpenAcre
- Sulfur & Sunflowers: https://github.com/CapsCollective/sunflower
- Farming RPG: https://github.com/Blockost/farming-rpg

## Next integration milestones

- [ ] Replace prototype primitives with original low-poly models and animations.
- [ ] Extract movement, combat, enemy AI, camera, and input into ES modules.
- [ ] Add inventory, item drops, equipment, and save migration.
- [ ] Reconnect the existing village, farm, food maps, and quest content.
- [ ] Add responsive mobile controls and test on actual touch devices.
- [ ] Review every external asset's license before bundling it.