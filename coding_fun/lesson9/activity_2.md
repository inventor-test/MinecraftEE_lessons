### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Deep Stone 

## Step 1
Виправте цей фрагмент коду. Ось ціль Агента: копати вглиб поверхні, поки він не дістане до **золотого (gold)** блоку **зліва (left)**. **Якщо** на шляху вниз Агент виявить **камінь (stone)** перед ним, то має зібрати його.


```template
player.onChat("dig", function () {
    while (agent.inspect(AgentInspection.Block, LEFT) == AIR) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
            if (agent.inspect(AgentInspection.Block, FORWARD) != GRASS) {
                player.say("Found the stone!")
                agent.destroy(FORWARD)
                agent.collectAll()
        }
    }
})
```


