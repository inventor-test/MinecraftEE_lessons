
### @hideIteration false 
### @flyoutOnly 1
### @explicitHints 1


# Hazing One

## Step 1
Встановіть блок ``||agent:agent set block||`` з **розтяжкою (tripwire)** та встановіть кількість **64**. 

## Step 2
Візьміть блок ``||loops:while||`` та вставте умову всередину нього (циклу ``||loops:while||``).  

#### ~ tutorialhint

```blocks
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
    	
    }
})

``` 
## Step 3
Додайте блоки ``||agent: agent place||`` та ``||agent: agent move||`` всередину циклу ``||loops:while||``. 

```blocks
player.onChat("run", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```