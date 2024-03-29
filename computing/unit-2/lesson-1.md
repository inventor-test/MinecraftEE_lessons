### @explicitHints 1

# Завдання 1: Запрограмуйте мережу доріг

## Крок 1
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

## Крок 2
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

## Крок 3
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

## Крок 4
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

## Крок 5
Остання важлива річ, яку ми повинні зробити, це вказати правильні координати. Якщо ви хочете збудувати дороги за планом, відкрийте підказку і перепишіть координати звідти. Якщо ж захочете збудувати свою дорогу - маєте вказати дві крайні точки, на початку та в кінці вашої дороги. Побачити координату, на якій ви стоїте, можна у верхньому лівому кутку, якщо згорнути інструкцію. Центральну координату **Y** маємо вказувати на одну цифру нижче, щоб створити дорогу під собою. У нашому прикладі це буде **68**. Тепер нумо перевіряти код! Якщо ви все правильно зробили, то маєте побачити, як на місці трави з’явиться дорога.

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

## Крок 6
Повторіть кроки для наступної дороги. Можете переписати координати з підказки, або вписати свої, якщо створюєте власні дороги.

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

## Крок 7
**Додатково.** Коли дві дороги готові, можете збудувати більше, використовуючи щойно створений код.
