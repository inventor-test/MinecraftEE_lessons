### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Бамбукова схованка

## Крок 1
Запрограмуйте Агента посадити **3** блоки бамбука з кожного боку піщаної ділянки. Додайте команду ``||agent:agent turn||``, щоб переконатись, що Агент може виконати завдання.

#### ~ tutorialhint
Має бути 2 цикли ``||loops:repeat||`` **(повторення)**, один вкладений всередину іншого.
 
```ghost
player.onChat("bamboo", function () {
    for (let index = 0; index < 3; index++) {
        agent.setItem(BAMBOO, 64, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
})
```


