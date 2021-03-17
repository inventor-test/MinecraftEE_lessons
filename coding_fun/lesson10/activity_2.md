### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
Під час **перевірки блоку знизу (While inspecting the block down)**, який **НЕ є спресованим льодом (packed ice)**, **якщо (if)** Агент **виявляє блок праворуч (detects the block right)**, йому потрібно **рухатися вперед (move forward)**. В іншому випадку (else) йому потрібно **рухатися праворуч (move right)**. У тому ж циклі, якщо Агент **перевіряє блок знизу (inspects the block down)** і він є **булижником (cobblestone)** **або** **гравієм (gravel)**, то йому потрібно **знищити (destroy)** і **зібрати все (collect all)**.


```template
player.onChat("ice", function () {
    while (0 == 0) {
        if (true) {
        	
        } else {
        	
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == COBBLESTONE ||agent.inspect(AgentInspection.Block, DOWN) == GRAVEL ) {
        	
        }
    }
})
```
```ghost
player.onChat("2", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == COBBLESTONE || agent.inspect(AgentInspection.Block, DOWN) == GRAVEL) {
            agent.destroy(DOWN)
            agent.collectAll()
        }
    }
})
```
