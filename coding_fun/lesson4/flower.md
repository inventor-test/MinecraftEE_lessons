### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true
### @explicitHints 1


# Зробіть район гарним!

## Step 1
Вам потрібно посадити **14 кульбаб (dandelions)** уздовж **4** боків сховища. Агент може посадити **14** кульбаб з одного боку.

#### ~ tutorialhint 
Не забудьте вибрати кількість блоків, які ви видаєте командою ``||agent:agent set block||``. 


```ghost
player.onChat("flower", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 14; index++) {
            agent.setItem(YELLOW_FLOWER, 64, 1)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})

``` 
