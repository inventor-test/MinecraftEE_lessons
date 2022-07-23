### @explicitHints 1

# Задвання 2: Програмуємо фонтан

## Step 1
Перейменуйте назву **run** блоку ``||Player:on chat command||`` на **park_fountain**.

Потрібно викопати межу фонтану. Ми зробимо це, розкопавши землю, а потім замінивши отвори **кругляком** (Cobblestone).

## Step 2
Перетягніть блок ``||Loops:repeat [4] times||`` всередину ``||Player:on chat command||``, значення залиште **4**.  

Це означає, що наш агент чотири рази повторить наступний набір дій. Оскільки ми будемо використовувати кілька циклів, цей перший буде називатися **зовнішнім** циклом.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {

    }
})
```

## Step 3
Перетягніть ще один блок ``||Loops:repeat [4] times||`` всередину ``||Player:on chat command||``. Поставте його **всередину** першого цилку.

Додайте всередину блок ``||Agent:agent destroy [forward]||`` та змініть значення на **down** (вниз).

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.destroy(DOWN)
        }
    }
})
```

## Step 4
Перетягніть блок ``||Agent:agent move [forward]||``, поставте його всередину ``||Loops:repeat [4] times||`` одразу після попереднього блоку.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
          agent.destroy(DOWN)
          agent.move(FORWARD, 1)
        }
    }
})
```


## Step 5
Додайте блок ``||Agent:agent turn [left]||`` **всередину зовнішнього циклу** ``||Loops:repeat [4] times||``, але **після внутрішнього** ``||Loops:repeat [4] times||``.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
          agent.destroy(DOWN)
          agent.move(FORWARD, 1)
        }
        agent.turn(LEFT_TURN)
    }
})
```

## Step 6
Можна перевірити код! Ви побачите, як ваш агент викопає в землі рамку 5 х 5.

Тепер нам потрібно заповнити цей отвір бруківкою, що буде рамкою для фонтану.

## Step 7
Перетягніть блок ``||Agent:agent set active slot||`` та поставте його під блоком ``||Loops:repeat [4] times||`` . Ця частина буде новою дією агента.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
      for (let index = 0; index < 4; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.turn(LEFT_TURN)
    }
    agent.setSlot(1)
})
```

## Step 8
Тепер маємо повторити попередні дії. Швидше буде скопіювати весь зовнішній цикл та поставити внизу програми, але **замінити** ``||Agent:agent destroy [down]||`` на ``||Agent:agent place [down]||``.  

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
})
```

## Step 9
Можна перевірити код ще раз. На цей раз агент має розмістити кругляк на тому місці, те викопає яму. **Cobblestone**. Так утвориться рамка нашого фонтану.

Тепер нам потрібно запрограмувати агента прибрати шар землі всередині фонтану, щоб вода не затопила парк.

## Step 10
Перетягніть блок ``||Agent:agent move [forward]||``, змініть значення на **left** (ліворуч) та поставте в кінець програми.

Витягніть ще один блок ``||Agent:agent move [forward]||``, поставте в кінець та залиште значення **forward** (вперед).

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
      for (let index = 0; index < 4; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.turn(LEFT_TURN)
    }
    agent.setSlot(1)
    for (let index = 0; index < 4; index++) {
      for (let index = 0; index < 4; index++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.turn(LEFT_TURN)
    }
    agent.move(LEFT, 1)
    agent.move(FORWARD, 1)
})
```

## Step 11
Витягніть блок ``||Loops:repeat [4] times||`` в кінець програми ``||Player:on chat command||``, а кількість повторів встановіть **3**.

У центрі фонтану є зона розміром 3х3 блоки, яку агенту потрібно очистити. Тому нам потрібно, щоб він 3 рази викопав блок і повторив це 3 рази, зміщуючись в сторону. Отже знову буде два цикли - зовнішний і внутрішній.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {

  }
})
```

## Step 12
Витягніть ще один блок ``||Loops:repeat [4] times||`` Поставте його **всередину** зовнішнього циклу, змініть значення на **3**.  

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {

      }
  }
})
```

## Step 13
Тепер, встановимо **всередині циклу** блок ``||Agent:agent destroy||`` та встановимо значення **down** (вниз).

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
      }
  }
})
```

## Step 14
Перетягніть блок ``||Agent:agent move [forward]||``, встановіть **всередині циклу** та залиште значення **1**.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 5; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
  }
})
```

## Step 15
Маємо повернути агента до початкової точки. Витягніть блок ``||Agent:agent move [forward]||`` та розмістіть його **після** внутрішнього циклу, але всередині **зовнішнього**. Встановіть напрямок **back**, та кількість **3**. 

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
  }
})
```

## Step 16
Витягніть блок ``||Agent:agent move [forward]||``, поставте під попереднім, змініть значення на **left** (ліворуч).
Таким чином ви перемістите агента на початок наступного рядочку блоків, які потрібно викопати, а зовнішній цикл повторить цю дію три рази.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
})
```

## Step 17
Давайте перевіримо програму і подивимось, як агент викопає внутрішню частину фонтану.

## Step 18
Тепер час запрограмувати водичку. Перетягніть блок ``||Agent:agent move [forward]||`` в **самий кінець** основної програми.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
})
```

## Step 19
Перетягніть ще один блок ``||Agent:agent move [forward]||`` та змініть напрямок на **right** (праворуч), а значення на **2**. Таким чином наш агент опиниться в центрі майбутнього фонтану.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
})
```

## Step 20
Витягніть блок ``||Loops:repeat [4] times||``, а кількість повторів змініть на **5**.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {

  }
})
```


## Step 21
В розділі ``||Agent:AGENT||`` витягніть блок ``||Agent:agent place [down]||`` та додайте до програми, поставивши його всередині блоку ``||Loops:repeat [5] times||``.
Тепер зробимо так, щоб Агент розміщував 5 блоків **кругляку** вгору, в основі фонтану.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
  }
})
```


## Step 22
Витягніть блок ``||Agent:agent move [forward]||``, поставте його **всередину** циклу та змініть значення на **up**. 
Агент переміститься до верхньої частини фонтану, готовий ставити водичку та запускати фонтан.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 5; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
    agent.move(UP, 1)
  }
})
```


## Step 23
Перетягніть блок ``||Agent:agent set active slot||``, додайте його в **кінець** програми, а значення встановіть **2**. В цьому слоті в агента лежить **відро води**.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
    agent.move(UP, 1)
  }
  agent.setSlot(2)
})
```


## Step 24
Додайте в кінець блок ``||agent:agent place||``, а значення встановіть **down** (вниз). Цей блок змусить агента розмістити воду.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
    agent.move(UP, 1)
  }
  agent.setSlot(2)
  agent.place(DOWN)
})
```


## Step 25
Тепер перегляньте та перевірте свій код спочатку десь подалі, перш ніж розміщувати фонтан у парку. Покличте агента свистком та запускайте код!
