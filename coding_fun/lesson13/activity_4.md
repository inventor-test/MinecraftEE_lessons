### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# Change the world!

## Step 1

Використовуйте подію ``||player:on player walk||``, щоб встановити блок за певним набором ``||positions: world||`` координат: **100, 68, 100**. Створіть ``||variable: змінну||`` та назвіть її **count**. Перетягніть блок ``||change count by 1||`` та блоки ``||blocks:place||`` з доданою змінною ``||count||``, яка збільшиться на 1 і розмістить блок, який пов'язаний з номером. 1 = камінь, 2 = трава, 3 = бруд тощо. Використовуйте інший блок подій, наприклад ``||player:on player fall||``, щоб скинути блок. Для цього перетягніть ``||set count||`` та поставте **0**, щоб перезапустити відлік, і додайте блок ``||blocks: place||`` з доданою змінною ``||variable:count||``, з тими ж самими світовими координатами. Таким чином, коли ви стрибаєте у світі, блок скидається.


### ~ tutorialhint 
Don't forget to use ``||positions: world||`` positions to indicate the coordinates. 

Не забудьте використовувати `` ||positions: world (абсолютні)|| ``, позиції для позначення координат. 

```blocks
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
```


```ghost
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
player.onTravelled(FALL, function () {
    count = 0
    blocks.place(count, world(100, 68, 100))
})
```

