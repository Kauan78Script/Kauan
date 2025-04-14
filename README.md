local UserInputService = game:GetService("UserInputService")
local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Criando a interface (botão)
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = playerGui
screenGui.Name = "MyInterface"

local button = Instance.new("TextButton")
button.Parent = screenGui
button.Size = UDim2.new(0, 200, 0, 100)  -- tamanho do botão
button.Position = UDim2.new(0.5, -100, 0.5, -50)  -- posição central
button.Text = "Clique Aqui"
button.TextSize = 30
button.BackgroundColor3 = Color3.fromRGB(0, 255, 0)  -- Cor do botão (verde)

-- Ação ao clicar
button.MouseButton1Click:Connect(function()
    print("Botão clicado! Ação executada!")
    -- Aqui você pode adicionar a ação que deseja fazer ao clicar
end)

-- Detecção de toque na tela (para celular)
UserInputService.TouchTap:Connect(function(touchPositions, isProcessed)
    if isProcessed then return end

    -- Se tocou na tela, simula um clique no botão
    print("Toque detectado na tela!")
    button:MouseButton1Click()
end)
