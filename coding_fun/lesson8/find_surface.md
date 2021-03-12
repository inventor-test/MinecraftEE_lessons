### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Reach magma

## Step 1
Запрограмуйте Агента зробити **1 крок вперед (move forward)**. Після цього, Поки Агент **перевіряє (inspects)** блок **знизу (down)** і це **не магма (magma)**, Агенту потрібно **рухатися вниз (move down)**.


```ghost
player.onChat("magma", function () {
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != MAGMA_BLOCK) {
        agent.move(DOWN, 1)
    }
})
```

