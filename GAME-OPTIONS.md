# Game Options — Objects & Images (OOP)

Choose ONE game. Then design your class hierarchy to match.

---

## Option A: Space Invaders Remix

**Core concept:** Defend against waves of descending aliens with different types and behaviors.

**Class hierarchy:**
```
GameObject
  Player (shield, weapons array, power-up handling)
  Enemy
    BasicInvader (moves in formation, shoots randomly)
    TankInvader (more health, slower, drops power-ups)
    BossInvader (phase-based attacks, health bar)
  Projectile
    PlayerBullet (fast, upward)
    EnemyBullet (slower, downward)
    Missile (homing, tracks player)
  PowerUp
    ShieldPowerUp (temporary invincibility)
    SpreadShot (multi-directional bullets)
```

**Key polymorphism:** Enemy subclasses override `update()` for different movement patterns. All enemies share `collidesWith()` and `takeDamage()`.

**GameManager focus:** Formation management, wave definitions, difficulty scaling.

---

## Option B: Roguelike Dungeon Crawler

**Core concept:** Explore rooms, fight enemies, collect items, go deeper.

**Class hierarchy:**
```
GameObject
  Entity
    Player (inventory[], health, attack, defense)
    Enemy
      Skeleton (patrol AI, melee attack)
      Slime (random bounce, splits when killed)
      BossEnemy (phase attacks, minion spawning)
  Item
    Weapon (damage bonus, attack range)
    Potion (heal amount, effect type)
    Key (unlocks doors)
  Room (walls[], enemies[], items[], doors[])
```

**Key polymorphism:** `Entity.takeDamage()` calculates defense reduction. `Item.use(player)` has different effects per subclass. `Enemy.update()` varies AI per type.

**GameManager focus:** Room generation, room transitions, entity lifecycle.

---

## Option C: Plant Defense (Tower Defense)

**Core concept:** Place towers to stop waves of enemies walking a path.

**Class hierarchy:**
```
GameObject
  Tower
    Sunflower (generates resources over time)
    PeaShooter (single-target, medium range)
    WallNut (blocks enemies, high health, no attack)
    SnowPea (slows enemies, extends PeaShooter)
  Enemy
    BasicZombie (walks the path, attacks towers)
    ConeHead (more health, same speed)
    BucketHead (even more health, slower)
    RunnerZombie (fast, low health)
  Projectile
    Pea (straight line, single target)
    IcePea (extends Pea, applies slow effect)
```

**Key polymorphism:** `Tower.update()` handles different attack patterns. `Enemy.takeDamage()` checks for slow effects. Towers and enemies share `draw()` patterns but render differently.

**GameManager focus:** Grid-based placement, path definition, wave system, resource economy.

---

## Option D: Boss Rush (Co-op)

**Core concept:** Two players fight a series of increasingly difficult bosses.

**Class hierarchy:**
```
GameObject
  Player
    Warrior (melee attacks, high health, shield ability)
    Mage (ranged attacks, low health, heal ability)
  Boss
    StoneGolem (ground pound AoE, rock throw, summon minions)
    FireDragon (fire breath cone, charge attack, fly phase)
    ShadowKnight (teleport, dark slash, clone illusion)
  Projectile
    Sword (melee range, arc shape)
    MagicBolt (ranged, tracks slightly)
    BossProjectile (various shapes per boss)
  Minion extends Enemy (spawned by bosses)
```

**Key polymorphism:** Each Boss overrides `update()` with unique phase-based state machines. Player subclasses have different abilities. All share `collidesWith()` for hit detection.

**GameManager focus:** Boss health bars, phase transitions, two-player input handling, arena setup.

---

## Option E: Creature Battle

**Core concept:** Tournament-style battles between creatures with unique abilities.

**Class hierarchy:**
```
GameObject
  Creature
    Rabbit (dash ability, medium speed, low health)
    Turtle (shield ability, slow speed, high health)
    Eagle (fly ability, high speed, medium health)
    Wolf (pack bonus ability, balanced stats)
    Dragon (fire breath, slow, very high health)
  Ability
    DashAbility (burst of speed in a direction)
    ShieldAbility (temporary damage reduction)
    FlyAbility (ignore ground collisions temporarily)
    PackBonus (damage boost near allies)
    FireBreath (cone AoE damage)
  Arena (boundaries, obstacles, hazards[])
```

**Key polymorphism:** `Creature.act()` is overridden per species for unique behavior. `Ability.activate(creature)` modifies the creature differently. All creatures use shared `collidesWith()` and `takeDamage()`.

**GameManager focus:** Tournament bracket, round management, creature selection screen, stat comparison UI.
