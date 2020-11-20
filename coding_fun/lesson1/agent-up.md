### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Запрограмуйте агента, щоб дістатись до золотої пластини!

## Step 1
Використовуйте команди ``||player:on chat||`` і  ``||agent:agent move||`` , щоб запрограмувати агента рухатися до золотої пластини. Ви можете запрограмувати агента рухатися **вгору**. Завершивши, натисніть кнопку **Play** щоб скомпілювати код. Зайдіть в Minecraft, щоб запустити свій код у грі.



```ghost
player.onChat("up", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

```  
