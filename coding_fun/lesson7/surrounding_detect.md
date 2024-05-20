### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
Поки Агент **перевіряє блок знизу (inspect block down)**, і цей блок - **камінь**, Агенту потрібно **рухатися вперед (move forward)**. Якщо Агент **не** виявляє блоку спереду, Агенту потрібно **рухатися вперед**, інакше він повинен **повернути ліворуч**.


```template
player.onChat("inspect", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == STONE) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
        } else {
        }
    }
})
```

```ghost
player.onChat("inspect", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == STONE) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
})
```

