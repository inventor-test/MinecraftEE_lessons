### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Chicken Coup

## Step 1
Агенту потрібно розмістити **9** блоків **залізних прутків** у **2** шари (в висоту). **Залізні прутки** мають бути з **4** сторін. Не забудьте використати ``||agent:agent move up||`` для побудови другого поверху.

#### ~ tutorialhint
В кінці у вас має вийти **3** блоки ``||loops:repeat|`` всередині один одного. Перевірте, чи Агент має більше 64 блоків у своєму інвентарі!

```ghost
player.onChat("chicken", function () {
    for (let index = 0; index < 2; index++) {
        agent.setItem(IRON_BARS, 1, 1)
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 9; index++) {
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})

``` 
