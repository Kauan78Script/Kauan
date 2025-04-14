local UserInputService = game:GetService("UserInputService")

UserInputService.TouchTap:Connect(function(touchPositions, isProcessed)
    if isProcessed then return end

    print("Toque detectado sem cooldown!")
end)
