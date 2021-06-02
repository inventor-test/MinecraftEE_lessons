### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Вітаємо! Ви пройшли до кінця

## Крок 1
Ура, ви пройшли цей урок! Можете використати всі блоки, які були на уроці, щоб потренуватися у програмуванні. Або потренуйтесь у майстерності будівництва.


```ghost
player.onChat("garbage", function () {
    for (let index = 0; index < 4; index++) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.destroy(FORWARD)
        agent.collectAll()
    }
})
```
