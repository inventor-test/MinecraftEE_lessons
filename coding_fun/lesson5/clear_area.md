### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Clear the Foliage!

## Step 1
Агенту потрібно знищити **8** блоків листя, рухаючись при цьому **вперед**. Є **16** рядків листя, які Агентові потрібно знищити. Агенту потрібно знищувати блок спереду (``||agent:destroy forward||``) та рухатись вперед (``||agent:move forward||``) **8** разів. 

#### ~ tutorialhint 
```blocks
player.onChat("foliage", function () {
    for (let index = 0; index < 8; index++) {
        for (let index = 0; index < 8; index++) {
        	
        }
    }
})

```

```ghost
player.onChat("foliage", function () {
    for (let index = 0; index < 8; index++) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        for (let index = 0; index < 2; index++) {
            agent.move(FORWARD, 1)
            agent.turn(RIGHT_TURN)
        }
    }
})
``` 
