### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
**Поки (While)** Агент **перевіряє блок знизу (inspect block down)**, і це **НЕ спресований лід (packed ice)**, запрограмуйте його знайти, **знищити (destroy)** та **зібрати (collect)** такі блоки: **залізо (iron)**, **золото (gold)**, **смарагд (emerald)** і **алмаз (diamond)**. Розташування блоків не випадкове! Подумайте, як зібрати всі блоки.

#### ~ tutorialhint 
Після знаходження дорогоцінного блоку агент має повернути або ліворуч, або праворуч, в залежності від блоку, а потім продовжити йти вперед. Щоб зробити код меншим, можна поєднати пару блоків логічним оператором OR.

```
player.onChat("1", function () {
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON || agent.inspect(AgentInspection.Block, DOWN) == GOLD) {

        }
        agent.move(FORWARD, 1)
    })
```

```ghost
player.onChat("3", function () {
    agent.setItem(STONE, 64, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != PACKED_ICE) {
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON || agent.inspect(AgentInspection.Block, DOWN) == GOLD) {
            agent.turn(LEFT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == DIAMOND || agent.inspect(AgentInspection.Block, DOWN) == EMERALD) {
            agent.turn(RIGHT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
```

