### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Detecting your first material

## Step 1
Агенту потрібно **знищити (destroy)**, а потім **зібрати (collect)** блок **золота**.

```template
player.onChat("material", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(LEFT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == GOLD_BLOCK) {
            
        }
    }
})
```

```ghost
player.onChat("1", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(LEFT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == GOLD_BLOCK) {
            agent.destroy(FORWARD)
            agent.collectAll()
        }
    }
})
```



