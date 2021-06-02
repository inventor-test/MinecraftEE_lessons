### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Вітаємо! Ви пройшли до кінця

## Step 1
Ура, ви пройшли цей урок! Можете використати всі блоки, які були на уроці, щоб потренуватися у програмуванні. Або потренуйтесь у майстерності будівництва.


```ghost
player.onChat("foliage", function () {
    for (let index = 0; index < 8; index++) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        for (let index = 0; index < 2; index++) {
            agent.move(FORWARD, 1)
            agent.turn(RIGHT_TURN)
            while (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
        }
    }
})
``` 
