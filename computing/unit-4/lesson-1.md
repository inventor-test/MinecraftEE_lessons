### @explicitHints 1

# Завдання 1: Програмуємо вхід до зоопарку

## Step 1
Перейменуйте назву **run** блоку ``||Player:on chat command||`` на **build_gates**.

Перетягніть блок ``||Agent:agent set active slot||``, значення залиште **1**. Тоді додайте блок ``||Agent:agent move [forward]||``, а значення змініть на **up** (вгору), значення має залишитись **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
})
```

## Step 2
Поставте блок ``||Loops:repeat [4] times||`` в кінець програми ``||Player:on chat command||`` та змініть значення на **15**. Це будуть велиикі ворота.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {

    }
})
```

## Step 3
Перетягніть всередину циклу блок ``||Agent:agent place [forward]||``, змініть значення на **down** (вниз).   

Додайте блок ``||Agent:agent move [forward]||``, напрямок маємо змінити на **right** (праворуч), а кількість кроків залишити **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
    }
})
```

## Step 4
Перетягніть ще один блок ``||Agent:agent place [forward]||`` з розділу ``||Agent:Agent||`` та встановіть напрямок **down** (вниз).

Поставте далі блок ``||Agent:agent move [forward]||``, залишимо напрямок **forward** та значення **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```


## Step 5
Перетягніть ще один блок ``||Agent:agent place [forward]||`` з розділу ``||Agent:Agent||`` та встановіть напрямок **down** (вниз).

Також додайте ще один блок ``||Agent:agent move [forward]||`` і встановіть напрямок **left** (ліворуч), кількість залишимо **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
    }
})
```

## Step 6
Витягніть ще один блок ``||Agent:agent place [forward]||`` з розділу ``||Agent:Agent||``, встановіть значення **down** (вниз).  
Тепер ми маємо направити ``||Agent:агента||`` до наступної початкової точки, щоб завершити першу частину воріт.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
    }
})
```

## Step 7
З розділу ``||Agent:Agent||`` перетягніть ДВА блоки ``||Agent:agent move [forward]||`` та встановіть їх під блоком ``||Agent:agent place [down]||``. У випадаючому меню змініть напрямок на **back** у першому блоці, та **up** в другому.  

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```
## Step 8
За допомогою свистка розмістіть агента на **блоці жовтої шерсті**.

## Step 9
Давайте перевіримо код! Введіть назву своєї команди ``||Player:on chat command||`` до чату, відкривши його кнопкою **T** та прослідкуйте, чи правильно агент будує першу частинку воріт.

## Step 10
Виконайте цю програму для другої частини воріт. Розмістіть агента на іншому **блоці жовтої шерсті** і запустіть команду ще раз. Тепер у вас має бути два дерев'яних стовпи для входу.  

## Step 11
Давайте запрограмуємо напис над входом.   

Додайте ще один блок ``||Player:on chat command||`` та перейменуйте його з **jump** на **zoo_sign**.

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {

})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## Step 12
Вставте блок ``||Blocks:print [HELLO]||`` до нового блоку ``||Player:on chat command||``.

Змініть напис **HELLO** на **ZOO**, або щось своє. ***Напис має бути англійською мовою.***

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    GRASS,
    pos(0, 0, 0),
    WEST
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## Step 13
Змінимо блок, з якого будуватиметься напис, з **трави** на **Oak Wood** (блок дубового дерева). Або виберіть свій варіант.

Перетягніть блок ``||Positions:world [0] [0] [0]||`` та замініть ним блок відносних координат ``||Positions:[~0] [~0] [~0]||`` всередині блоку ``||Blocks:print||``.

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(0, 0, 0),
    WEST
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## Step 14
Змініть координати на ``||Positions:world (абсолютні)||`` координати над воротами. Маємо вибрати точку, в якій буде починатись наш напис. За прикладом координати будуть **-31, 83, -560**. Зауважте, що *мінус* в числах дуже важливий для координат.

Можуть знадобитись декілька спроб, щоб правильно розташувати напис, залежно від того скільки букв у написі, де вони розміщуються та в якому напрямку розвернуті.
#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(-31, 83, -560),
    WEST
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## Step 15
Щоб обрати правильний напрямок написання, змініть значення параметру ``||Blocks:along||``. За прикладом це буде **North (negative Z)**, але якщо ви програмуєте свою версію воріт, напрямок може бути іншим.  

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(-31, 83, -560),
    NORTH
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## Step 16
Гайда перевіряти код! Впишіть в чат команду **zoo_sign** та запустіть її кнопкою Enter. Маєте побачити, як у світі над воротами з'являється напис **ZOO** (або ваш власний).
