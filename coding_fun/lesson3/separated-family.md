### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Розлучена родина!

## Крок 1
Запрограмуйте Агента побудувати міст через прірву в льоду. Переконайтеся, що Агент має **64** блоки **дубових дощок (oak planks)** в інвентарі.

#### ~ tutorialhint 
Не забудьте використати блок ``||logic:not||`` у вашому циклі ``||loops:while||``. Подумайте, де саме Агент має розміщувати блоки. 


```ghost
player.onChat("family", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }
})

``` 
