### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
Під час **перевірки блоку знизу (While inspecting the block down)**, який є **спресованим льодом (packed ice)**, **якщо (if)** Агент **виявить блок праворуч (detects the block right)**, йому потрібно **рухатися вперед (move forward)**. В іншому випадку йому потрібно **рухатися праворуч (move right)**.



```ghost
player.onChat("1", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
    }
})
```

