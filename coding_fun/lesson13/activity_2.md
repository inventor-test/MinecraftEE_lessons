### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# The Climb

## Step 1
Ваше випробування в тому, щоб ``||mobs:jump (стрибнути)||`` дуже високо, і піднятися на важкодоступну ділянку.


```ghost
loops.forever(function () {
    mobs.applyEffect(JUMP_BOOST, mobs.target(NEAREST_PLAYER), 10, 1)
    mobs.clearEffect(mobs.target(NEAREST_PLAYER))
})
```
