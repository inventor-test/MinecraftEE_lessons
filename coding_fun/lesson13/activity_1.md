### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Lava swim

## Step 1
Ваше завдання - ``||player:swim (переплисти)||`` через озеро лави. Спробуйте застосувати ``||mobs:fire resistance (вогнетривкість)||`` до **найближчого гравця (nearest player)**.



```ghost
player.onTravelled(SWIM_LAVA, function () {
    mobs.applyEffect(FIRE_RESISTANCE, mobs.target(NEAREST_PLAYER), 10, 1)
    mobs.clearEffect(mobs.target(NEAREST_PLAYER))
})
```
