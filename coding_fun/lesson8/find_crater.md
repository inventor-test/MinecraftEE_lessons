### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
Поки (while) Агент **виявляє блок знизу (detects block down)**, йому потрібно рухатися вперед (move forward). Якщо Агент **перевіряє блок знизу (inspects block down)** і знаходить **повітря (air)**, використовуйте команду ``||player:say||``, щоб сказати **Кратер знайдено!**.



```template
player.onChat("crater", function () {
            player.say("Crater found!")
})
```
```ghost
player.onChat("1", function () {
    while (agent.detect(AgentDetection.Block, DOWN)) {
        agent.move(FORWARD, 1)
    }
    if (agent.inspect(AgentInspection.Block, DOWN) == AIR) {
        player.say("Crater found!")
    }
})
```