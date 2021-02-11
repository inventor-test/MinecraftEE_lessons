### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Cattle

## Step 1
Подивіться на початковий код і спробуйте запустити його. Цей код дозволяє керувати Агентом без підрахунку блоків. Подивіться на шлях, який повинен пройти Агент, і переконайтеся, що ви зробили послідовність коду з правильними поворотами для Агента. Переконайтесь, що Агент може дістатися до **золотої пластини**. 

```template
player.onChat("sheep", function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})

``` 

