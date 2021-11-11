### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Захистіть територію

## Step 1
Запрограмуйте Агента побудувати **дубову огорожу (oak fence)**. Агенту потрібно розмістити блоки **дубової огорожі (oak fence)** праворуч, знищити перешкоди і рухатися вперед. Огорожа повинна бути довжиною **17 блоків**.

#### ~ tutorialhint
Переконайтеся, що Агент розміщує блоки праворуч і знищує блоки ліворуч.

```blocks
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
            }
})
```
```ghost
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
        agent.place(RIGHT)
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
    }
})
``` 

