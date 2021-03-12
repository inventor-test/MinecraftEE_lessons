### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Locate the Sample! 

## Step 1
**While** the Agent **inspects the block down** and does **not** find **blue ice**, program the Agent to **destroy** and **move down**. When the Agent locates the **blue ice**, it needs to **destroy down** and **collect** the sample. 

**Поки (while)** Агент **перевіряє блок знизу (inspects block down)** і **не (not)** знаходить **блакитний лід (blue ice)**, запрограмуйте його **знищувати (destroy)** та **рухатися вниз (move down)**. Коли Агент виявить **блакитний лід**, йому потрібно **знищити (destroy down)** і **зібрати (collect)** зразок.

```ghost 
player.onChat("ice", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != ICE) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
    }
    agent.destroy(DOWN)
    agent.collectAll()
    
})
```
