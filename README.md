# BanditTexture

Resource pack for the Bandit Minecraft server. Minecraft Java 1.21.4, `pack_format` 46,
namespace `bandit`.

## Contents

- Item icons for all 21 pieces of Bandit gear, in both diamond and netherite tiers
- Worn armor skins for the bandit, crowned, arcane and ember sets
- Five kill sound effects

## How it renders

**Item icons** use `custom_model_data` with a `range_dispatch` in
`assets/minecraft/items/<base_item>.json`. Every one of those files falls back to the plain
vanilla model, so ordinary gear with no Bandit model data still looks completely normal,
with or without this pack.

**Worn armor** uses the `equippable` component's `asset_id`, which resolves to a layer
definition in `assets/bandit/equipment/`. That component has no fallback of its own: a
client that cannot resolve the asset draws nothing at all rather than falling back to
vanilla. This is why the server requires the pack.

## Layout

```
pack.mcmeta
assets/
  bandit/
    equipment/            8 layer definitions, one per set and tier
    models/item/          41 item models
    textures/item/        41 item icons
    textures/entity/equipment/
      humanoid/           worn armor, helmet, chestplate and boots
      humanoid_leggings/  worn armor, leggings
  minecraft/
    items/                11 vanilla overrides carrying the range_dispatch
    sounds.json
    sounds/custom/kill/   5 ogg files
```

## Installing

Players do not need to install anything, the server pushes the pack on join. To test it
locally instead, drop the folder or the zip into `.minecraft/resourcepacks` and enable it.

When zipping by hand, `pack.mcmeta` and `assets/` must sit at the root of the archive, not
inside a wrapper folder.

## Credits

Kill sounds come from Pixabay. Individual source links are listed in `SOURCE_LINKS.txt`.
