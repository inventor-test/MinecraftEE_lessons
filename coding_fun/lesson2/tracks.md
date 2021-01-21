### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# Запрограмуйте агента рухатися вздовж черепаших доріжок!

## Step 1
Перемістіть агента до воріт вздовж доріжок черепах, використовуючи блок ``||agent: agent move forward||``. Закінчивши, натисніть кнопку **Play**, щоб скомпілювати код. Не забудьте запустити свій код в Minecraft. 

```ghost
player.onChat("tracks", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
for (let index = 0; index < 4; index++) {
    	
 }
``` 
