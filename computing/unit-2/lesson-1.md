### @explicitHints 1

# Lesson 1: Code a Road Network

## Step 1
Перейменуйте назву **run** в блоці ``||Player:on chat command||`` на **road_1**. Виберіть блок ``||Blocks:fill with||`` та перетягніть його всередину блоку ``||Player:on chat command||``.

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRASS,

    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 2
Клацніть по випадаючому меню, щоб змінити тип блоку з **Grass** на **Gray Concrete**.
### ~ tutorialhint

``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 3
Тепер відкрийте розділ ``||Positions:POSITIONS||`` та витягніть до робочої області блок ``||Positions:world [0] [0] [0]||``.
Замініть блоком ``||Positions:world [0] [0] [0]||`` блок ``||Positions:відносних [~0] [~0] [~0]||`` координат  всередині блоку ``||Blocks:fill||``.

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 4
Перетягніть ще один блок ``||Positions:world [0] [0] [0]||`` з розділу ``||Positions:POSITIONS||`` та замініть наступний блок ``||Positions:відносних||`` координат всередині блоку ``||Blocks:fill with||``.

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 5
Ми майже готові перевірити наш код, однак є ще одна важлива річ, яку ми повинні зробити, щоб код працював належним чином. Змініть центральну координату **Y**, на одну цифру нижче. У нашому прикладі це буде **68**. Тепер нумо перевіряти код! Якщо ви все правильно зробили, то маєте побачити, як на місці трави з’явиться дорога.

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -565),
    world(61, 68, -569),
    FillOperation.Replace
    )
})

```

## Step 6
Повторіть кроки для наступної дороги.

### ~ tutorialhint
``` blocks
player.onChat("road_2", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -532),
    world(61, 68, -536),
    FillOperation.Replace
    )
})
```

## Step 7
*(Додатково)* Коли дві дороги готові, можете збудувати більше, використовуючи щойно створений код. Коли ви закінчите, поговоріть з інструктором до 1-го завдання і попросіть трохи килиму, щоб зробити дорожню розмітку. Використайте агента, щоб розмістити килими.
