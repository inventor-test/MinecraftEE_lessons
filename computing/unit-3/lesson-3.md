### @explicitHints 1

# Завдання 3: Садимо квіти 

## Step 1
Перейменуйте назву **run** команди ``||Player:on chat command||`` на **plant_flowers**. 

Перетягніть блок ``||Loops:repeat [4] times||`` всередину ``||Player:on chat command||`` та встановіть значення рівним довжині сторони вашого парку. За прикладому це буде **20**. 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
    	
    }
})
```

## Step 2
Тепер перетягніть блок ``||Agent:agent set active slot||`` всередину циклу ``||loops: repeat||``.    

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(1)
    }
})
```

## Step 3
Зайдіть до розділу ``||Math:MATH||``. 

Блоки в цьому розділі дозволяють користуватись математичними виразами.

Перетягніть блок ``||Math:pick random [0] to [10]||`` всередину ``||Player:on chat command||`` та замініть ним цифру 1 в блоці ``||Agent:agent set active slot||``. 

Тепер ми запрограмували, щоб агент обирав випадковий слот у своєму інвентарі, а не якийсь один.

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(0, 10))
    }
})
```

## Step 4
Першим числом впишіть **1**, а другим **5**, оскількі в агента зараз зайняті 5 слотів інвентаря. 
#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
    }
})
```


## Step 5
Запрограмуємо агента рухатись випадковим чином. У розділі ``||Agent:Agent||`` знайдіть та перетягніть блок ``||Agent:agent move [forward]||`` в кінець нашої програми.   

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, 1)
    }
})
```

## Step 6
Витягніть ще один блок ``||Math:pick random [0] to [10]||`` та замініть цифру 1 в блоці ``||Agent:agent move [forward]||``. Замініть друге число в блоці ``||Math:pick random [0] to [10]||`` на **20**. 

З цим рядком коду агент буде рухатись вперед на випадкову кількість блоків, від 1 до 20.

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
    }
})
```

## Step 7
Перетягніть два блоки ``||Agent:agent place [forward]||`` та поставте в кінець програми, але в одного блоку значення змініть на **back** (назад). 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
    }
})

```

## Step 8
Перетягніть ще один блок ``||Agent:agent set active slot||`` до програми. З розділу ``||Math:MATH||`` витягніть блок ``||Math:pick random [0] to [10]||`` та вставте в блок ``||Agent:agent set active slot||``, змініть значення на 1 та 5. 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
    }
})
```

## Step 9
З розділу ``||Agent:Agent||`` витягніть блок ``||Agent:agent move [forward]||``, вкажіть значення **back** (назад).

Додайте блок ``||Math:pick another pick random [0] to [10]||`` всередину ``||Agent:agent move [back]||`` та поставте значення **0** та **20**. 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(BACK, Math.randomRange(0, 20))
    }
})
```

## Step 10
Тепер з розділу ``||Agent:Agent||`` перетягніть ще два блоки ``||Agent:agent place [forward]||``, в одному з них змінивши значення на **back**. 

Наостанок перетягніть блок ``||Agent:agent move [left]||`` до програми, щоб завершити її. 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(BACK, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.move(LEFT, 1)
    }
})
```

## Step 11
Покличте агента до себе за допомогою свистка та запустіть код. Розмістіть свого агента в одному з кутів вашого парку, так щоб позаду нього була огорожа, а сам парк знаходився ліворуч від нього.

Гайда перевіряти наш код! Агент повинен рухатися вперед у випадкове місце, садити пару випадково вибраних квітів, рухатися назад, робити те саме і переміщатися ліворуч, щоб почати все спочатку. Має утовритись луг з випадкових квітів.
