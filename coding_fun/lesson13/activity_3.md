### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Building

## Step 1
Дайте собі блоком ``||mobs:Give||`` щонайменше **34 смарагдові (emerald)** блоки. Створіть нову **змінну** (``||variable||``) та назвіть її **count**. Візьміть блок ``||blocks:on block placed||`` і встановіть для нього значення **смарагд (emerald)**. Перетягніть блок ``||change count||`` всередину ``||blocks: on block placed||`` і додайте блок ``||player: say||``. Додайте ``||count||`` всередину блоку ``||player: say||``. Таким чином, коли ви розміщуєте блоки, гра буде підраховувати, скільки блоків ви розмістили.

### ~ tutorialhint 

Ви можете вибрати залізо, золото, смарагд або алмаз.

```blocks
let count = 0
blocks.onBlockPlaced(EMERALD_BLOCK, function () {
    count += 1
    player.say(count)
})

```

```ghost
blocks.onBlockBroken(STONE, function () {
    count += 1
    player.say(count)
})
let count = 0
mobs.give(
mobs.target(NEAREST_PLAYER),
STONE,
1
)
})
```


