### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Spiral

## Step 1
Поки Агент **перевіряє блок попереду (inspect forward)**, і цей блок **не** є **золотим блоком**, Агенту потрібно **рухатися вперед (move forward)**. Якщо Агент **не** виявляє блок попереду, йому також потрібно рухатися вперед, інакше він повинен **повернути ліворуч (turn left)**. Коли Агент дійшов до **золотого блоку**, йому потрібно **знищити (destroy)** та **зібрати (collect)** його.

```template
player.onChat("spiral", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
    }
})
```

```ghost
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```
