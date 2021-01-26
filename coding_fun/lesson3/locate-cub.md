### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Знайдіть дитинча!

## Крок 1
Запрограмуйте агента викопати шлях, не знаючи, наскільки далеко він проходить, за допомогою команди ``||loops:while||`` та ``||agent:agent detect||``. Агент має розламувати блоки перед собою та згори, командами ``||agent:destroy forward & up||`` щоб ви змогли пройти! Закінчивши, натисніть кнопку **Play**, щоб скомпілювати код. Не забудьте запустити свій код в Minecraft.

#### ~ tutorialhint 
Зверніть увагу на форми частин кодування, коли ви їх з’єднуєте. Використовуйте ``||agent:agent move forward||``.

```template
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
    	
    }
})
```

```ghost
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.destroy(UP)
    }
})

``` 
