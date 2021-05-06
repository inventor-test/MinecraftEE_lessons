### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Make it rain!

## Step 1
Зробіть так, щоб пішов дощ, поки ви танцюєте в Minecraft! Для цього вам потрібно використати кілька обробників подій. 1. Створіть свої змінні, наприклад: **walk**, **jump** та / або **break**. 2. Виберіть обробники подій, наприклад ``||player: on player fall||``, ``||player: on player walk||``. 3. Встановіть для нових ``||змінних (variables)||`` значення ``||logic: true||`` всередині кожного відповідного блоку подій. 4. Використайте блок **завжди** (``||loop: forever||``) і перетягніть всередину нього ``||logic: if (умову)||``. Встановіть для всіх своїх умов значення ``||logic:true||`` і додайте до них блок ``||gameplay: weather||``, встановивши **дощ (rain)**.

### ~ tutorialHint
```blocks
let walk = false
player.onTravelled(WALK, function () {
    walk = true
})
loops.forever(function () {
    if (walk == true && "" == "") {
    	
    }
})

```

```ghost
let climb = false
let walk = false
let _break = false
player.onTravelled(CLIMB, function () {
    climb = true
})
player.onTravelled(WALK, function () {
    walk = true
})
blocks.onBlockBroken(STONE, function () {
    _break = true
})
loops.forever(function () {
    if (walk == true && climb == (true && _break == true)) {
        gameplay.setWeather(RAIN)
    }
})
```
