### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Величезна прірва!

## Крок 1
Запрограмуйте Агента **побудувати міст** через прірву в льоду. Використайте блок ``||agent:set block or item||`` щоб переконатися, що Агент має необхідні матеріали в інвентарі. Виберіть **дуб** як будівельний матеріал та **64** для **кількості блоків**. ``||loops:while||`` Агент **не** виявляє блоки знизу, запрограмуйте його ставити дубові дошки **вниз** і рухатися **вперед**, щоб створити міст.    


```template
player.onChat("chasm", function () {
    agent.setItem(PLANKS_OAK, 1, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, DOWN))) {
    	
    }
})
```

```ghost
player.onChat("chasm", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})

``` 

