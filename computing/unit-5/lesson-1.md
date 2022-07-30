

# Завдання 1: Запрограмуй вітряк

## Крок 1
Перш ніж ми почнемо будувати вітроелектростанцію, давайте виберемо для нього гарне місце. За прикладом ми будемо використовувати пагорб біля міста. Щоб запрограмувати турбіну, потрібно використати один із методів, яких ми навчились. Маємо створити одну турбіну, а потім зклонувати її, щоб зробити ферму.

```template
player.onChat("run", function(){
})
player.teleport(pos(19, 79, -413))
```

## Крок 2
Перевірте себе. Ви маєте бути знайомі з двома основними методами програмної побудови, ``||Agent:AGENT||`` та ``||Builder:BUILDER||``, Подумайте, як можна використати якийсь з цих методів, щоб збудувати вітряк.

## Крок 3
Коли вітряк побудований, використайте блок ``||Blocks:clone||`` з розділу ``||Blocks:BLOCKS||``, щоб зробити копії та збудувати цілу ферму, якщо хочете. Для цього ви маєте знайти координати вгорі праворуч і внизу зліва вітряка, щоб утворився невидимий куб з ним всередині. Ці координати потрібно записати в поля **from** і **to**.


#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        pos(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
)
```


```ghost
player.onChat("run", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
    agent.destroy(FORWARD)
    agent.place(FORWARD)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.teleportToPlayer()
    agent.setItem(GRASS, 1, 1)
    for (let index = 0; index < 4; index++) {
        blocks.place(GRASS, world(0, 0, 0))
    }
    while (true) {
    	
    }
})
```
