-- ✅ USD HUB LOADING SCRIPT CORRIGIDO

-- Garantir execução local
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Remover UIs antigas se existirem
pcall(function()
	if playerGui:FindFirstChild("USDLoadingGui") then playerGui.USDLoadingGui:Destroy() end
	if playerGui:FindFirstChild("USDMainGui") then playerGui.USDMainGui:Destroy() end
end)

-- Criar GUI de carregamento
local loadingGui = Instance.new("ScreenGui", playerGui)
loadingGui.Name = "USDLoadingGui"
loadingGui.IgnoreGuiInset = true
loadingGui.ResetOnSpawn = false

-- Imagem de fundo do loading
local loadingImage = Instance.new("ImageLabel", loadingGui)
loadingImage.Size = UDim2.new(1, 0, 1, 0)
loadingImage.Position = UDim2.new(0, 0, 0, 0)
loadingImage.BackgroundTransparency = 1
loadingImage.Image = "rbxassetid://17447123781" -- <- ID da imagem 'LOADING...'

-- Texto personalizado
local textLabel = Instance.new("TextLabel", loadingGui)
textLabel.Size = UDim2.new(1, 0, 0.1, 0)
textLabel.Position = UDim2.new(0, 0, 0.85, 0)
textLabel.Text = "BEM VINDO AO USD HUB"
textLabel.TextColor3 = Color3.fromRGB(0, 255, 255)
textLabel.TextStrokeTransparency = 0.2
textLabel.TextScaled = true
textLabel.Font = Enum.Font.GothamBold
textLabel.BackgroundTransparency = 1

-- Espera 5 segundos, depois mostra a tela principal
task.delay(5, function()
	loadingGui:Destroy()

	local mainGui = Instance.new("ScreenGui", playerGui)
	mainGui.Name = "USDMainGui"
	mainGui.IgnoreGuiInset = true
	mainGui.ResetOnSpawn = false

	local mainImage = Instance.new("ImageLabel", mainGui)
	mainImage.Size = UDim2.new(1, 0, 1, 0)
	mainImage.Position = UDim2.new(0, 0, 0, 0)
	mainImage.BackgroundTransparency = 1
	mainImage.Image = "rbxassetid://17447166434" -- <- ID da imagem com o Kaká
end)
