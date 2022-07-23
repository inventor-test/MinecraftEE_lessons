### @explicitHints 1

# Завдання 1: Програмуємо паркову огорожу

## Step 1
Перейменуйте назву **run** в блоці ``||Player:on chat command||`` на **park_fence**. 

Витягніть блок ``||Agent:agent set active slot||`` та вставте його в  ``||Player:on chat command||``.

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
})
```
## Step 2
Перетягніть блок ``||Loops:repeat [4] times||`` всередину ``||Player:on chat command||`` та змініть кількість повторів на **25**.

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
    	
    }
})
```

## Step 3
Перетягніть блок ``||Agent:agent move [forward]||``, та поставте його всередину циклу ``||Loops:repeat [25] times||``, в блоці ``||Player:on chat command||``, цифру залиште **1**. 

Візьміть блок ``||Agent:agent place [forward]||`` та перетягніть до ``||Player:on chat command||`` всередину циклу ``||Loops:repeats [25] times||``, під блок ``||Agent.agent move[forward]||``, змініть **forward** на **back** (назад).

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
})
```

## Step 4
Перетягніть блок ``||Agent:agent turn [left]||`` всередину ``||PLayer:on chat command||``, поставте його **під** циклом repeat. Оберіть напрямок, в якому агент має повернутись. За прикладом він буде **left** (ліворуч). 

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
    agent.turn(LEFT_TURN)
})
```

## Step 5
Перевірте свій код. Розмістіть свого агента на стартовий блок за допомогою свистка і запустіть код, відкривши чат буквою **T** та вписавши назву своєї програми. 

Агент збудує лише одну сторону за раз. Переконайтесь, що у вашого агента достатньо блоків, щоб закінчити кожну сторону! Щоб отримати більше блоків, попросіть їх в інструктора до першого завдання.
