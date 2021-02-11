### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Hazing 

## Step 1
Агенту потрібно встановити **розтяжку**, щоб вовки не заходили всередину. Встановіть блок ``||agent:agent set block||`` з **розтяжкою (tripwire)** та встановіть кількість **64**. Використайте блок циклу ``||loops:while||`` і помістіть умову всередину.  

#### ~ tutorialhint
Не забудьте використати ``||logic:not||`` у вашій умові. 

```blocks
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
    	
    }
})

``` 
```ghost
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```
