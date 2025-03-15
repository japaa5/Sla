local player = game.Players.LocalPlayer
local char = player.Character or player.CharacterAdded:Wait()
local rootPart = char:WaitForChild("HumanoidRootPart")

while true do
    for _, objeto in pairs(workspace:GetChildren()) do
        if objeto:IsA("Part") and objeto.Name == "Moeda" then
            local distancia = (rootPart.Position - objeto.Position).magnitude
            if distancia < 10 then -- Se a moeda estiver perto, coleta
                objeto.CFrame = rootPart.CFrame
                wait(0.5) -- Evita coleta muito rápida
            end
        end
    end
    wait(1) -- Tempo entre cada verificação
end
