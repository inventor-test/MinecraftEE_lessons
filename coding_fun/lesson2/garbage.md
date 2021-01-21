### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Запрограмуйте Агента, щоб зібрати все сміття!

## Крок 1
Запрограмуйте Агента для очищення черепашого маршруту, використовуючи блоки ``||agent: agent destroy||`` та ``||agent:agent collect all||``. Спробуйте використати блок ``||loops:repeat||``, щоб зробити код більш ефективним. Закінчивши, натисніть кнопку **Play**, щоб скомпілювати код. Не забудьте запустити свій код в Minecraft.


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
