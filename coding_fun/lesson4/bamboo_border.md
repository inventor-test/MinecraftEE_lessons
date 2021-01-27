### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Бамбуковий кордон

## Крок 1
Ми підготували для вас початковий код. Спробуйте спочатку запустити його. Кінцева мета - посадити бамбук уздовж **4** сторін ділянки панди. 

```template
player.onChat("bamboo", function () {
    agent.setItem(BAMBOO, 64, 1)
    for (let index = 0; index < 16; index++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})
```
