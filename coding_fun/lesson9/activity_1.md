### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Locating stone 

## Step 1
Виправте цей фрагмент коду. Ось що повинен зробити Агент: **пройти ліворуч 4 кроки**, **знищити блок знизу (destroy down)**, **пройти вниз (move down)**. Якщо Агент виявляє блок **каменя (stone)** попереду, йому потрібно сказати "Знайшов камінь!", **знищити блок попереду (destroy forward)** і **зібрати все (collect all)**. Якщо камінь **не виявлено**, Агенту потрібно сказати: "Тут немає каменю!". Кожного разу після кроку вниз, Агенту потрібно **зробити 1 крок вгору (move up)** до поверхні. Цю діяльність потрібно повторити **4** рази.


```template
player.onChat("stone", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(RIGHT, 4)
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) != STONE) {
            player.say("Found the stone!")
            agent.destroy(FORWARD)
            agent.collectAll()
        } else {
            player.say("No stone here!")
        }
        agent.move(UP, 1)
    }
})
```
