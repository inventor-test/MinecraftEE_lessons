### @explicitHints 1

# Завдання 2: Програмуємо доріжки зоопарку 

## Step 1
Перейменуйте назву **run** в блоці ``||Player:on chat command||`` на **zoo_path_1**. 

Перетягніть блок ``||Blocks:fill with||`` та вставте всередину ``||Player:on chat command||``. 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRASS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 2
Використовуючи випадаюче меню, змініть блок побудови з **трави** на **Gravel** (гравій). 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 3
Тепер відкриємо розділ ``||Positions:POSITIONS||``. 

Пригадаємо, що в ньому містяться блоки, які дозволяють змінювати світ у Minecraft через ***позиції***, або ж ***координати***. Кожен блок у світі Minecraft має свою позицію по осі X, Y та Z.

Перетягніть два блоки ``||Positions:world [0] [0] [0]||`` та замініть відносні координати ``||Positions:[~0] [~0] [~0]||`` в полях ``||Blocks:from||`` і ``||Blocks:to||``. 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 4
Тепер маємо додати початкові координати доріжки в поле ``||Blocks:from||``, всередину комірок ``||Positions:world [0] [0] [0]||``. 
Впишіть координати свого ***початку*** доріжки, або ж скористайтесь прикладом: в ньому ці числа **-40, 69, -575**.

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 69, -575),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 5
Те саме маємо зробити для поля ``||Blocks:to||``. Впишіть координати ***кінця*** доріжки в комірки ``||Positions:world [0] [0] [0]||``. Знайдіть в світі свій варіант, або скористайтесь прикладом: в ньому ці числа **-60, 69, -575**.

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 69, -575),
    world(-60, 69, -575),
    FillOperation.Replace
    )
})
```

## Step 6
Тепер маємо змінити *другу* координату **Y** на одну цифру менше, щоб доріжка створилась **в землі**. В нашому прикладі це буде **68**.  
Пам'ятайте, центральна координата означає висоту, в нижній точці світу вона **0**, а в самій верхній **256**. Ми хочемо змінити траву **під ногами** на гравій, а блок, в якому ми заміряли координати, - це **ноги** нашого гравця. Тож якщо запустимо код без змін, дорога буде **над землею** на 1 блок вище. А зменшивши висоту, замінимо траву.

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 68, -575),
    world(-60, 68, -575),
    FillOperation.Replace
    )
})
```
## Step 7
Давайте перевіримо ваш код! Якщо все правильно, в обраних вами координатах трава має замінитись на гравій.   

## Step 8
Запустіть програму з координатами для інших 2-3 доріжок. Можете спланувати систему доріг так, як вам захочеться, але залиште місце для вольєрів. 

