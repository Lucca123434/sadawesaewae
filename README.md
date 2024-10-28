-- Kaitun Advanced Script for Blox Fruits with God Human and Super Human Farming
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local AutoFarmButton = Instance.new("TextButton")
local CollectFruitsButton = Instance.new("TextButton")
local TeleportButton = Instance.new("TextButton")
local FarmGodHumanButton = Instance.new("TextButton")
local FarmSuperHumanButton = Instance.new("TextButton")

ScreenGui.Parent = game.CoreGui

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.Position = UDim2.new(0.5, -150, 0.5, -150)
Frame.Size = UDim2.new(0, 300, 0, 300)

AutoFarmButton.Parent = Frame
AutoFarmButton.BackgroundColor3 = Color3.fromRGB(0, 170, 255)
AutoFarmButton.Position = UDim2.new(0.1, 0, 0.1, 0)
AutoFarmButton.Size = UDim2.new(0.8, 0, 0.1, 0)
AutoFarmButton.Text = "Auto Farm"

CollectFruitsButton.Parent = Frame
CollectFruitsButton.BackgroundColor3 = Color3.fromRGB(0, 255, 170)
CollectFruitsButton.Position = UDim2.new(0.1, 0, 0.25, 0)
CollectFruitsButton.Size = UDim2.new(0.8, 0, 0.1, 0)
CollectFruitsButton.Text = "Collect Fruits"

TeleportButton.Parent = Frame
TeleportButton.BackgroundColor3 = Color3.fromRGB(255, 170, 0)
TeleportButton.Position = UDim2.new(0.1, 0, 0.4, 0)
TeleportButton.Size = UDim2.new(0.8, 0, 0.1, 0)
TeleportButton.Text = "Teleport"

FarmGodHumanButton.Parent = Frame
FarmGodHumanButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
FarmGodHumanButton.Position = UDim2.new(0.1, 0, 0.55, 0)
FarmGodHumanButton.Size = UDim2.new(0.8, 0, 0.1, 0)
FarmGodHumanButton.Text = "Farm God Human"

FarmSuperHumanButton.Parent = Frame
FarmSuperHumanButton.BackgroundColor3 = Color3.fromRGB(0, 0, 255)
FarmSuperHumanButton.Position = UDim2.new(0.1, 0, 0.7, 0)
FarmSuperHumanButton.Size = UDim2.new(0.8, 0, 0.1, 0)
FarmSuperHumanButton.Text = "Farm Super Human"

local function teleportTo(position)
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
    humanoidRootPart.CFrame = CFrame.new(position)
end

local function attack()
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local tool = player.Backpack:FindFirstChildOfClass("Tool")
    if tool then
        character.Humanoid:EquipTool(tool)
        tool:Activate()
    end
end

AutoFarmButton.MouseButton1Click:Connect(function()
    while true do
        local enemyPosition = Vector3.new(0, 0, 0) -- Substitua pela posição do inimigo
        teleportTo(enemyPosition)
        attack()
        wait(1) -- Ajuste o tempo de espera conforme necessário
    end
end)

CollectFruitsButton.MouseButton1Click:Connect(function()
    while true do
        local fruitPosition = Vector3.new(0, 0, 0) -- Substitua pela posição da fruta
        teleportTo(fruitPosition)
        wait(1) -- Tempo para coletar a fruta
    end
end)

TeleportButton.MouseButton1Click:Connect(function()
    local teleportPosition = Vector3.new(0, 0, 0) -- Substitua pela posição desejada
    teleportTo(teleportPosition)
end)

FarmGodHumanButton.MouseButton1Click:Connect(function()
    while true do
        local godHumanNPCPosition = Vector3.new(0, 0, 0) -- Substitua pela posição do NPC de God Human
        teleportTo(godHumanNPCPosition)
        attack()
        wait(1) -- Ajuste o tempo de espera conforme necessário
    end
end)

FarmSuperHumanButton.MouseButton1Click:Connect(function()
    while true do
        local superHumanNPCPosition = Vector3.new(0, 0, 0) -- Substitua pela posição do NPC de Super Human
        teleportTo(superHumanNPCPosition)
        attack()
        wait(1) -- Ajuste o tempo de espera conforme necessário
    end
end)
