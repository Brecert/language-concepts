## Spark Wand Example
### formatting
```sh
@NAME Spark Wand
@DESCRIPTION Launch magic sparks.
Projectile::Snowball
  | Speed::Medium
  | Area::Medium
    | Damage::Type::Enemy
      | Damage::Amount::Low
```

### no formatting
```sh
@NAME Spark Wand
@Description Launch magic sparks.
Projectile::Snowball
Speed::Medium
Area::Medium
Damage::Type::Enemy
Damage::Amount::Low
```

### Temporary Acceptance System
```ex
» Blocks
  » Elementals
    | Ice
    | Fire (emulated block using particles)
    | @ Spell::Creation

» Effect
  » Negative
    » Ambiant
      | Slowness
      | Mining Fatuige
    » Damaging
      | Fire
      | Poision

» Spell
  » Creation
    » Wall
      | @ Blocks::Elementals
  » Destruction
    | Tnt
  » Damaging
    | Undead
    | Arachnid
    | Spark (Undead | Arachnid)
    | @ Effect::Negative::Damaging
  » Effect
    | @ Effect::Negative::Ambiant
```

