### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1


# Місце повище!

## Крок 1
Запрограмуйте Агента побудувати вежу з **дубових дошок**, висотою **10** блоків. Спочатку переконайтеся, що Агент має **64** блоки **дубової дошки**, використовуючи команду ``||agent:set block or item||``. Потрібно розмістити дубові дошки **спереду (forward)**, **ліворуч (left)** та **праворуч (right)** за допомогою команди ``||agent:agent place||``. Агенту потрібно **рухатися вгору (move up)** після розміщення блоків. 

#### ~ tutorialhint 
Спробуйте використати блок ``||loops:repeat||`` та змінити кількість повторів на **10**. 

## Крок 2
Запрограмуйте Агента збудувати **драбину** на вежу, висотою **10** блоків. Він має ставити драбину, покроково рухаючись **вниз** від верхівки вежі. Драбина потрібна, щоб ви залізли на вежу!

#### ~ tutorialhint 
Не забудьте видати **64** блоки **драбини** в інвентар Агенту командою ``||agent: agent set block||``, щоб Агент зміг її розмістити. 


```ghost
player.onChat("tower", function () {
    agent.move(FORWARD, 1)
    agent.setItem(LADDER, 64, 1)
    for (let index = 0; index < 10; index++) {
        agent.place(FORWARD)
        agent.move(UP, 1)
    }
    agent.move(DOWN, 10)
})

``` 


