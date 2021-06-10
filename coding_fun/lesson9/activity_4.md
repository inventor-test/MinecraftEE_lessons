### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Repair the Rover 

## Step 1
Виправте цей фрагмент коду. Ось, як має бути: **перевіряючи (inspecting)** на наявність блоку **повітря (air)** попереду (forward) і **не** знаходячи його, Агенту потрібно **рухатися праворуч (move right)**. Якщо Агент знаходить **лазуритовий блок (lapis lazuli)** **попереду (forward)**, йому потрібно **пройти праворуч (move right)**, **повернути ліворуч (turn left)**, потім **пройти праворуч (move right)**. Після цього Агент має сказати: "Знайшов обрив! (Found the break!)" та **помістити блок редстоуну попереду (place a block of redstone forward)**.


```template
player.onChat("repair", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) == AIR) {
        agent.move(RIGHT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == LAPIS_LAZULI_BLOCK) {
            agent.move(RIGHT, 1)
            agent.turn(RIGHT_TURN)
            agent.move(LEFT, 1)
        }
    }
    player.say("Found the break!")
    agent.setItem(GRASS, 1, 1)
    agent.place(FORWARD)
})
```
