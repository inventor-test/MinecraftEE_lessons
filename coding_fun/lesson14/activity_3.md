### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Power the portal!

## Step 1
Вас має вдаряти блискавкою в той час, коли ви стоїте на **золотих пластинах**. По-перше, вам потрібно змінити погоду ``||gameplay:погоду (weather)||`` на дощ  ``||loops:при запуску (on start)||``. Потім спробуйте використати ``||logic:if (якщо)||``, ``||blocks:test for (тест під собою)||`` та ``||mobs:spawn a lightning bolt (спавн блискавки)||`` щоб нанести удар блискавкою саме в потрібний момент.


### ~ tutorialHint
Золоті пластини знаходяться під вами за координатами **0, -1, 0**.

```ghost
player.onTravelled(WALK, function () {
    if (blocks.testForBlock(GOLD_BLOCK, pos(0, -1, 0))) {
        mobs.spawn(LIGHTNING_BOLT, pos(0, 0, 0))
    }
})
gameplay.setWeather(RAIN)
```
