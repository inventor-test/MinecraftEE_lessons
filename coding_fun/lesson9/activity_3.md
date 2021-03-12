### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Track Down the Rover 

## Step 1
Виправте цей фрагмент коду. Ось мета: Поки (while) Агент **перевіряє попереду (inspecting forward)** наявність блоку **кварцу (quartz)** і **не** знаходить його, Агенту потрібно **рухатися вперед (move forward)**. Якщо він **виявить (detect)** **золотий (gold)** блок **знизу (down)**, йому потрібно **повернути праворуч (turn right)**. Якщо він виявив **блок заліза знизу (down)**, йому потрібно **повернути ліворуч (turn left)**. В кінці Агент повинен сказати: "Знайшов марсохід!"

```template
player.onChat("rover", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != BLOCK_OF_QUARTZ) {
            if (agent.inspect(AgentInspection.Block, UP) == GOLD_BLOCK) {
            agent.turn(LEFT_TURN)
        }
            if (agent.inspect(AgentInspection.Block, RIGHT) == IRON_BLOCK) {
            agent.turn(RIGHT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the rover!")
})
```

