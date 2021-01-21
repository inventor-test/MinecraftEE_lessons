### @hideIteration false 
### @flyoutOnly 1
### @explicitHints 1


# Запрограмуйте агента рухатися вздовж маршруту черепах!

## Крок 1
Перемістіть агента вздовж черепаших доріжок, використовуючи блок ``||agent: agent move forward||``. 

#### ~ tutorialhint 
Спробуйте використати блок ``||loops:repeat||`` , щоб зробити код більш ефективним.

## Крок 2
Закінчивши, натисніть кнопку **Play**, щоб скомпілювати код. Не забудьте запустити свій код в Minecraft. 

```blocks
player.onChat("run", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
for (let index = 0; index < 4; index++) {
    	
 }
``` 

