local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Someone Hub Beta", "DarkTheme")
local FarmTab = Window:NewTab("Farm")

-- Bone Farming
local BoneFarmSection = FarmTab:NewSection("Auto Farm Bones")
local boneFarming = false
local function boneFarm()
    while boneFarming do
        wait(1)
        for _, item in pairs(workspace:GetChildren()) do
            if item:IsA("Part") and item.Name == "Bone" and item:IsTouching(game.Players.LocalPlayer.Character) then
                game.Players.LocalPlayer.Character.Humanoid:MoveTo(item.Position)
                fireclickdetector(item.ClickDetector)
                wait(0.5)
            end
        end
    end
end
BoneFarmSection:NewToggle("Start/Stop Bone Farming", "Toggles automatic bone farming.", function(state)
    boneFarming = state
    if boneFarming then boneFarm() end
end)

-- Fruit/Raids
local FruitRaidsTab = Window:NewTab("Fruit/Raids")
local FruitSection = FruitRaidsTab:NewSection("Auto Collect Fruits")
local fruitCollecting = false
local function collectFruits()
    while fruitCollecting do
        wait(1)
        for _, fruit in pairs(workspace:GetChildren()) do
            if fruit:IsA("Fruit") and fruit:IsTouching(game.Players.LocalPlayer.Character) then
                fireclickdetector(fruit.ClickDetector)
                wait(0.5)
            end
        end
    end
end
FruitSection:NewToggle("Start/Stop Fruit Collecting", "Toggles automatic fruit collecting.", function(state)
    fruitCollecting = state
    if fruitCollecting then collectFruits() end
end)

-- Auto Store Fruits
local StoreFruitSection = FruitRaidsTab:NewSection("Auto Store Fruits")
local fruitStoring = false
local function storeFruits()
    while fruitStoring do
        wait(1)
        local player = game.Players.LocalPlayer
        local inventory = player.Backpack:GetChildren()
        for _, fruit in ipairs(inventory) do
            if fruit:IsA("Fruit") then
                fireclickdetector(fruit.ClickDetector)
                wait(0.5)
            end
        end
    end
end
StoreFruitSection:NewToggle("Start/Stop Fruit Storing", "Toggles automatic fruit storing.", function(state)
    fruitStoring = state
    if fruitStoring then storeFruits() end
end)

-- Boss Tracker
local BossSection = FarmTab:NewSection("Active Bosses")
local bosses = {"Bandit Leader", "Brute", "Giant Pirate", "Buggy the Clown", "Mr. 3", "Supa", "Vice Admiral", "Saber Expert", "Diamond", "Magma Admiral", "Psycho", "Baron", "Killer", "Shadow King", "Saber Master", "Darkbeard", "Frog King", "Kizaru", "Admiral Akainu"}
local function updateBossList()
    BossSection:Clear()
    for _, bossName in ipairs(bosses) do
        local boss = workspace:FindFirstChild(bossName)
        BossSection:NewLabel(boss and boss:IsA("Model") and boss:FindFirstChild("Humanoid") and boss.Humanoid.Health > 0 and (bossName .. " is alive!") or (bossName .. " is not alive."))
    end
end
game:GetService("RunService").Stepped:Connect(updateBossList)
updateBossList()

-- Teleport
local TeleportSection = FarmTab:NewSection("Teleport to the Seas")
local function teleportTo(position)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(position)
end
TeleportSection:NewButton("Teleport to Sea 1", "Teleports to Sea 1.", function() teleportTo(Vector3.new(0, 10, 0)) end)
TeleportSection:NewButton("Teleport to Sea 2", "Teleports to Sea 2.", function() teleportTo(Vector3.new(3500, 10, 2000)) end)
TeleportSection:NewButton("Teleport to Sea 3", "Teleports to Sea 3.", function() teleportTo(Vector3.new(12000, 10, 3000)) end)
