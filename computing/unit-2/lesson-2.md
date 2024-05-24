### @explicitHints 1

# Завдання 2: Програмуємо будівлі

## Крок 1
Почнемо з будівництва стін. Перейменуйте назву **run** в блоці ``||Player:on chat command||`` на **build_a_structure**. Витягніть і вставте блок ``||Agent:agent set active slot||`` всередину блоку  ``||Player:on chat command||``. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
})
```

## Крок 2
Перетягніть блок ``||Agent:agent [place on move]||`` всередину ``||Player:on chat command||`` та приєднайте знизу. У меню цього блоку встановіть значення **ON**.

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
})
```

## Крок 3
Тепер надамо агенту інструкції, що будувати і як. Зазирніть до розділу ``||Loops:LOOPS||``. Витягніть блок ``||Loops:repeat [4] times||`` та приєднайте знизу до програми ``||Player:on chat command||``. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        
    }
})
```


## Крок 4
Поверніться в розділ ``||Agent:AGENT||`` та витягніть блок ``||Agent:agent move [forward]||``, тепер поставте його всередину циклу ``||Loops:repeat [4] times||``. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 1)
    }
})
```

## Крок 5
Змініть у блоці ``||Agent:agent move [forward]||`` кількість рухів до **5**. Витягніть блок повороту ``||Agent:agent turn [left]||`` та поставте його всередину циклу ``||Loops:repeat [4] times||``. Ви можете змінити напрямок повороту залежно від того, що і де будуєте. Для цього прикладу ми залишимо його як ліворуч **(left)**. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
})
```

## Крок 6
Давайте перевіримо код. Наш агент має збудувати чотири стіни і повернутись на початок.

## Крок 7
Зайдіть в розділ ``||Agent:AGENT||`` та додайте ще один блок ``||Agent:agent move [forward]||``, але змініть напрямок на **up** (вгору). Але цей блок вже поставте за межами циклу ``||Agent:repeat [4] times||``, тобто після нього знизу, як окрему дію. Цей блок перемістить агента вгору на один блок, щоб мати змогу далі ставити блоки.

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
})
```

## Крок 8
Додайте ще один блок ``||Agent:agent [place on move]||``, але тут виберіть значення **OFF**. Адже тепер ми не хочемо, щоб агент будував, поки рухається. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
    agent.setAssist(PLACE_ON_MOVE, false)
})
```


## Крок 9
Витягніть ще один блок ``||Agent:agent move [forward]||``, та змініть напрямок на **right** (праворуч). Це поверне агента на стартову позицію, щоб він був готовий розпочати наступний шар стін.

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(RIGHT, 1)
})
```

## Крок 10
Тепер нам потрібно повторити весь цей процес для чотирьох шарів стін. Для цього стане в нагоді ще один цикл. 
Заходьте в розділ ``||Loops:LOOPS||`` та витягніть ще один цикл ``||Loops:repeat [4] times||``. Цього разу поставте цикл так, щоб всередині нього опинилась ВСЯ програма, адже нам потрібно повторювати всю процедуру побудови стін. 

## Крок 11
Поверніться до розділу ``||Agent:AGENT||`` та додайте блок ``||Agent:agent [place on move]||``, встановіть значення на **ON**. Можете перевірити код. 

## Крок 12
Зайдіть в розділ ``||Agent:AGENT||`` та додайте блок ``||Agent:agent set active slot||``, замініть значення на **2**. Використайте ще один цикл **repeat**, в якому агент має пройти вперед на 5 блоків, а потім на 1 блок ліворуч, в тому ж циклі потім пройти 5 блоків назад і знову 1 блок ліворуч. Ця дія має повторитись 3 рази, щоб в нас вийшов дах. Блоками для даху можна обрати **Stone Slabs** (кам'яні плити).

### ~ tutorialhint

``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
})
```

## Крок 13
Тепер настав час додати вікно та двері. Додайте ще один блок ``||Agent:agent [place on move]||``, встановіть його значення як **OFF**. Додайте блок ``||Agent:agent move [forward]||``, але напрямок виберіть **down** (вниз), а кількість **3**. Тепер ваш агент переміститься вниз на три блоки, де розміститься вікно, і не буде ставити блоки даху.

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
})
```


## Крок 14
Додайте ще один блок ``||Agent:agent move [forward]||``, напрямок має бути ``||Agent:forward||``, а кількість кроків **1**.

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
})
```


## Крок 15
Додамо ще один блок ``||Agent:set active slot||``, а значення встановимо **3**. Цим зробимо активним третій слот інвентаря агента, отже будівельним матеріалом стануть **скляні панелі**. 

Додайте блок ``||Agent:agent destroy [forward]||``. Вставте його нижче останнього блоку і змініть значення на **right** (праворуч). Таким чином цим кроком агент знищить блок праворуч від себе, звільняючи місце під вікно.

## Крок 16
Тепер поставте наступним новий блок ``||Agent:agent place [forward]||``, у випадаючому меню змініть значення на **right** (праворуч). В цій частині програми агент розмістить **Glass Pane** (скляну панель) прямо у отворі, що утворився після знищення стіни. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
})
```


## Крок 17
Додайте ще один блок ``||Agent:agent move [forward]||``. Залиште значення **forward** (вперед), але цифру замініть на **2**.

## Крок 18
Оскільки нам потрібно додати двері, потрібно буде пробити в стіні два блоки в висоту. Перший блок можемо зламати одразу, розмістивши ``||Agent:agent destroy [forward]||`` та змінивши значення на **right** (праворуч). 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
})
```

## Крок 19

Додайте ще один блок ``||Agent:agent move [forward]||``. Значення змініть на **down** (вниз), зробити агент має 1 крок. Тоді він опиниться прямо там, де нам потрібно розмістити двері. Отже, нам потрібно розбити блок, встановити правильний активний слот та розмістити двері. 

### ~ tutorialhint
``` blocks 
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
})
```

## Крок 20
Додамо ще один блок ``||Agent:agent destroy [forward]||``, значення змінимо на **right**.

Зазирнемо у розділ ``||Agent:AGENT||`` та витягнемо блок ``||Agent:select active slot||``. Змініть значення на **4**. Тепер активним буде 4 слот інвентаря агента, в якому лежить **Acacia Door** (акацієві двері). 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
    agent.destroy(RIGHT)
    agent.setSlot(4)
})
```


## Крок 21
Повернемось до розділу ``||Agent:AGENT||`` та поставимо в кінець блок ``||Agent:agent place [forward]||``, але змінимо значення на **right**. Цей блок поставить двері праворуч від агента та завершить наш будинок. Гайда перевіряти код! 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
    agent.destroy(RIGHT)
    agent.setSlot(4)
    agent.place(RIGHT)
})
```
