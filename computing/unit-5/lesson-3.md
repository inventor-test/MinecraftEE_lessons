# Завдання 3: Запрограмуй систему освітлення  

## Крок 1
Давайте запрограмуємо вироблення електрики вітряком. Перше, що нам потрібно зробити - це створити ілюзію, що лопаті не завжди повертаються. Як і в реальному житті, вітер іноді може зникати.

Використовуйте готовий код і змініть значення для блоку ``||loops:repeat||`` з **4** на **10**. Якщо ви використовували свої координати лопатей, потрібно також замінити їх у всіх блоках ``||Blocks:clone||``.

``` template
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## Крок 2
Запрограмуємо генерацію енергії. Перетягніть блок ``||Blocks:place [block] at||`` та вставте його **на початок** вашої програми, над блоком ``||Loops:repeat [10] times||``.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(GRASS, pos(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## Крок 3
Змініть **блок трави** на **Блок редстоуну (Block of Redstone)**.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, pos(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## Крок 4
Змініть **відносні** координати на **абсолютні** ``||Positions:world [0] [0] [0]||`` з розділу ``||Positions:POSITIONS||``.  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## Крок 5
Поверніться до гри і встаньте на перший блок у траншеї, яку ви викопали для свого редстоуну. Подивіться на координати в цьому місці. У прикладі це **8 81 -412**, хоча у вас може бути інша.  

## Крок 6
Впишіть цю координату в блок ``||Blocks:place [Block of Redstone]||``.  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## Крок 7
Скопіюйте блок ``||Blocks:place [Block of Redstone]||``, натиснувши праву кнопку миші (або потримавши палець з планшету) та вибравши пункт **Duplicate**.  

Вставте скопійований блок в самому низу, під циклом ``||Loops:repeat||``.  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
})
```

## Крок 8
У випадаючому меню змініть **Блок редстоуну** на **повітря (air)**. Готовий код має виглядати як в прикладі, але з вашими координатами.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
})
```

## Крок 9
Перевірте код! Якщо все правильно, встановлена раніше **Редстоун лампа** має засвітитись, коли ви запустите команду **wind_turbine**.  

## Крок 10
Витягніть блок ``||Loops:forever||``.  

Цей блок - цикл, який повторюється вічно. Так можна зробити погодні умови, або в цьому випадку, вітер.

## Крок 11
Тепер перетягніть **всю попередню програму** до блоку ``||Loops:forever||``. Потягніть за перший блок в програмі, ``||Blocks:place [Block of Redstone]||`` та перетягніть все до нового блоку.  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
})
loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    )
})
```   

## Крок 12
Змініть кількість повторів в циклі ``||Loops:repeat [10] times||`` на **20**. 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    
})
loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 20; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    )
})
```  

## Крок 13
Наостанок, нам потрібно якось зробити імітацію відсутності вітру. Поки що вітряк постійно обертається, і електроенергія не зникає. Правильно розміщена пауза в коді дасть нам цей ефект.

## Крок 14
Поверніться до розділу ``||Loops:LOOPS||`` та перетягніть блок ``||Loops:pause (ms)||``. Поставте його одразу після останнього блоку ``||Blocks:place [Air]||``. Змініть значення на **5000**.  

Для прикладу, 1000 мс - це одна секунда в грі. Отже, 5000 мс означатиме паузу в 5 секунд. На 5 секунд вітер буде "закінчуватися" і енергія зникатиме. 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
   
})
loops.forever(function () {
    for (let index = 0; index < 20; index++) {
        blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    loops.pause(5000)
})
```
## Крок 15
Перевіримо програму! Наш вітряк має обернутись 20 разів, а потім зупинитися на 5 секунд, і це все буде повторюватись нескінченно. Ваша редстоун лампа має світитись лише тоді, коли лопаті обертаються. Якщо щось не буде працювати, перегляньте свій код і внесіть необхідні корективи за потреби. Потім можете повторити кроки для інших турбін.
