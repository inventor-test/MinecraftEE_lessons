### @explicitHints 1

# Завдання 3: Програмуємо житло для тварин 

## Step 1
В цьому завданні скористуємось Будівельником! Спочатку маємо вказати Будівельнику (BUILDER), де починати. Перейменуйте назву **run** в блоці  ``||Player:on chat command||`` на **ocelot_wall**. 

Щоб знайти блоки для Будівельника, зайдіть в чорний розділ ``||Advanced:ADVANCED||``, а тоді знайдіть там розділ ``||Builder:BUILDER||``. Розділ ``||Builder:BUILDER||`` дозволяє гравцям керувати побудовою різних конструкцій в Minecraft. Можна уявити ``||Builder:будівельника||`` як невидимого ``||Agent:агента||``. 

Отже, задамо початкову точку. Перетягніть блок ``||Builder:builder teleport to [~0] [~0] [~0]||`` до вашої програми ``||Player:on chat command||``. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(pos(0, 0, 0))
})
```

## Step 2
Перетягніть блок ``||Positions:world [0] [0] [0]||`` до попереднього блоку, замінивши **відносні** координати. 

Тепер змінимо початкову координату ``||Positions:world [0] [0] [0]||`` на ту, де ви хочете почати будувати стіну. За прикладом початок буде трохи правіше блоку золота, в координатах **-39, 69, -577**. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
})
```

## Step 3
Тепер нам потрібно вказати Будівельнику, в якому напрямку будувати. Згадайте, що у світі Minecraft є 4 напрямки: північ та південь, і схід та захід, а також напрямок вгору та вниз. Простий спосіб знайти правильний шлях за допомогою компаса.

Ви знайдете компас у своєму інвентарі.

Якщо ви покрутитесь, так само буде крутитись і стрілка **компасу**. В цьому світі червона стрілка вказує на північ, тоді зліва буде схід, праворуч захід, позаду південь. За прикладом ``||Builder:BUILDER||`` має почати будувати на Захід. 

## Step 4
Зайдіть в розділ ``||Builder:BUILDER||`` та витягніть блок ``||Builder:builder face [West (negative X)||``. Додайте його до програми. 

Примітка: Якщо ви будуєте свою конструкцію, то змініть напрямок відповідно до побажань. Використайте **компас**, щоб знайти правильний напрямок для ``||Builder:BUILDER||`` та виберіть його в блоці. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
    builder.face(WEST)
})
```

## Step 5
З розділу ``||Builder:BUILDER||`` перетягніть блок ``||Builder:builder move [forward]||`` до основної програми. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
    builder.face(WEST)
    builder.move(FORWARD, 1)
})
```

## Step 6
Змініть число кроків у блоці ``||Builder:builder move [forward]||`` до потрібної кількості (довжини вашої стіни). За прикладом, це буде число **21**, але у вас може бути інше. 

Тепер перетягніть блок ``||Builder:builder turn [left]||`` до основної програми. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(LEFT_TURN)
})
```

## Step 7
Змініть напрямок повороту на той, в якому ``||Builder:BUILDER||`` має повернутись. За прикладом, це буде **right** (праворуч). 

Додайте ще один блок ``||Builder:builder move [forward]||`` та змініть число на кількість блоків в іншій стінці. За прикладом це буде **9**. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
})
```

## Step 8
Наостанок, маємо вказати ``||Builder:будівельнику||``, якими блоками будувати.  З розділу ``||Builder:BUILDER||`` перетягніть блок ``||Builder:builder trace a path from mark with||`` до основної програми. 

Цей блок вказує будівельнику залишати лінію з якогось блоку на шляху його пересування. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(GRASS)
})
```

## Step 9
У випадаючому меню змініть матеріал на бажаний для побудови стіни. У прикладі ми використовуємо **Stone Bricks** (кам'яні цеглинки). 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(STONE_BRICKS)
})
```

## Step 10
Давайте перевіримо код! ``||Builder:Будівельник||`` має телепортуватись до координати **-39, 69, -577** та пройти на Захід **21** блок, тоді повернутись **ліворуч** і пройти ще **9** блоків, при цьому ставити на шляху **кам'яні цеглинки**. В результаті має вийти невеличкий напів-периметр навколо першого житла. Можна помітити, що процес відбувається значно швидше, ніж при використанні ``||Agent:агента||`` та блоків з розділу ``||Blocks:BLOCKS||``. З невеличким плануванням можна створювати величезні побудови всього за кілька секунд. 

## Step 11
За прикладом ми будуємо вольєр для оцелотів. Ця стінка не втримає їх, тож додамо повище огорожу.

## Step 12
Можете зробити новий код, або підлаштувати вже готовий. Потрібно всього лиш змінити значення **висоти** на **1** блок, а матеріал, наприклад, на **Oak Fence** (дерев'яний паркан). Можете зазирнути у приклад. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-39, 69, -577))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
})
```

## Step 13
Тепер ми можемо якось покращити житло оцелотам (або вашим тваринкам).

Запрограмуємо спавн оцелота у його житлі. Залишиться лише познайомити його з новим житлом.

## Step 14
Витягніть новий блок ``||Player:on chat command||`` та перейменуйте його на **ocelot**. 

## Step 15
Витягніть блок ``||Mobs:spawn [animal] at||`` з розділу ``||Mobs:MOBS||`` до вашого нового блоку ``||Player:on chat command||``. 

У випадаючому меню **animal** виберіть потрібну тваринку, наприклад **ocelot** (оцелота). 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, pos(0, 0, 0))
})
```

## Step 16
Зайдіть в розділ ``||Positions:POSITIONS||`` та перетягніть блок **абсолютних** координат ``||Positions:world [0] [0] [0]||``, щоб замінити **відносні** координати. Тепер маємо записати в них координату десь всередині вольєру. За прикладом можемо взяти **-50, 69, -581**. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, world(-50, 69, -581))
})
```

## Step 17
Спробуємо перевірити код та заспавнити оцелота (чи вашу тварину). Якщо все правильно, тваринка має з'явитись всередині свого житла!


## Step 18
Тепер можете додати інші вольєри, наприклад для **вовка** та **полярного ведмедя**, або будь-яких інших. Врахуйте їх середовище проживання та облаштуйте їх житло відповідно до цього.
