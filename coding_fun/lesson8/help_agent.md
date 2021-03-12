### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Iron

## Step 1
Поки **(while)** Агент **перевіряє блок знизу (inspect block down)** і цей блок НЕ є **залізною рудою (iron ore)**, йому потрібно **рухатися вперед (move forward)**. Якщо Агент **виявляє блок попереду (detect block forward)**, тоді йому потрібно **знищити спереду (destroy forward)**. Коли Агент виявить залізо, запрограмуйте його на **збір (collect)**. Щоб зібрати блок, Агенту потрібно спочатку його знищити.

```ghost
player.onChat("4", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != IRON_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the iron ore!")
    agent.destroy(DOWN)
    agent.collectAll()
})
```
