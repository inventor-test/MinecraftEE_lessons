### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true
### @explicitHints 1


# Спільна діяльність

## Step 1
Вибирайте блоки, які вам потрібні для побудови правильного будинку для тваринок. Всі блоки, якими ми користувались протягом уроків, зараз доступні для використання!


```ghost
player.onChat("run", function () {
    agent.teleportToPlayer()
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
    	
    }
    agent.place(FORWARD)
    agent.destroy(FORWARD)
    agent.setItem(GRASS, 1, 1)
    for (let index = 0; index < 4; index++) {
    	
    }
})

``` 
