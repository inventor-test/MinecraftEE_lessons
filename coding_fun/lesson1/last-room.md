### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Запрограмуйте агента, щоб дістатись до золотої пластини!

## Step 1
Запрограмуйте Агента, щоб він дістався до золотої пластини. Спочатку вам потрібно стояти на одній золотій пластині, а Агенту - на іншій. Закінчивши програму, натисніть кнопку **Play**, щоб скомпілювати код. Потім запустіть свій код у Minecraft.


```ghost
player.onChat("last", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
```  