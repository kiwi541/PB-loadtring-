local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- Lista de usuários autorizados
local authorizedUsers = {
    ["AdmBrookhaven4"] = true,
    ["sr_greg81"] = true,
    ["TwT_perdiminhaconta"] = true,
    ["scarys_cary66666"] = true,
    ["AdmBrookhaven5"] = true,
    ["kdjdhwie12"] = true,
    ["admbughaven4"] = true,
    ["Pguel_01"] = true,
    ["fazolpguel2"] = true,
    ["kdjdhwie14"] = true,
    ["kdjdhwie13"] = true,
    ["TemplariosHub"] = true,
    ["j3ffwoods"] = true,
    ["Ink_sannes13"] = true,
    ["juninho126501"] = true,
    ["baconbadass6"] = true,
    ["Johnatan_FF95"] = true,
    ["Nego_Doce144"] = true,
    ["joaoantonio1997"] = true,
    ["contadefarme12"] = true,
    ["sr_greg26"] = true,
    ["sirtjfoxy123"] = true,
    ["samuel123456game1"] = true,
    ["thekjahwn"] = true,
    ["bypassadonis"] = true,
    ["PerfFectBx4483"] = true,
    ["breno628e5"] = true,
    ["kdjdhwie"] = true,
    ["SCARYS_CARY66666"] = true,
    ["davigemes300617"] = true,
    ["ERROR887282"] = true,
    ["Meliodas1234328"] = true,
    ["ajudante_Claudio"] = true,
    ["hdqnwsn"] = true,
    ["thek01890"] = true,
    ["mano_shark6"] = true,
    ["volvinhr"] = true,
    ["KAIO_XTY"] = true,
    ["djekejsn"] = true,
    ["D99SHOP"] = true,
    ["cotryball8"] = true,
    ["ADMBROOKHAVEN6676"] = true,
    ["cuidado_025"] = true,
    ["PerfFectBx4483"] = true,
    ["Mateuszinban"] = true,
    ["nolyhaha"] = true,
    ["mTADORDEWEB666"] = true,
    ["contasecundariamrred"] = true,
    ["novacontapolicebrook"] = true,
    ["Nego_doce144"] = true,
    ["amandabrfofinhagam2"] = true,
    ["uehdutududgetd"] = true,
    ["PROBLEMATICOGAMES3"] = true,
}

-- Caso o jogador não seja autorizado, ele será kickado
if not authorizedUsers[LocalPlayer.Name] then
    LocalPlayer:Kick("❌️ Você não tem Permissão para Executar esse Script, fale com o criador dele para que ele libere seu acesso.")
    return
end


local Intro = Instance.new("ScreenGui")
local Logo = Instance.new("ImageLabel")
local Circle = Instance.new("UICorner")

Intro.Name = "Intro"
Intro.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
Intro.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Logo.Name = "Logo"
Logo.Parent = Intro
Logo.AnchorPoint = Vector2.new(0.5, 0.5)
Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Logo.BackgroundTransparency = 1.000
Logo.BorderColor3 = Color3.fromRGB(0, 0, 0)
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0.5, 0, 0.5, 0)
Logo.Size = UDim2.new(0, 400, 0, 400)
Logo.Image = "rbxassetid://86898373680592"
Logo.ImageTransparency = 0
Logo.ScaleType = Enum.ScaleType.Crop

Circle.CornerRadius = UDim.new(110235, 0)
Circle.Name = "Circle"
Circle.Parent = Logo

-- Timer de 3 segundos antes de desaparecer
task.wait(3) -- Aguarda 3 segundos
Logo:TweenSizeAndPosition(
    UDim2.new(0, 0, 0, 0), -- Diminui o logo
    UDim2.new(0.5, 0, 0.5, 0), -- Mantém no centro
    Enum.EasingDirection.Out,
    Enum.EasingStyle.Quad,
    1, -- Tempo da animação
    true,
    function()
        Intro:Destroy() -- Remove a tela de introdução
    end
)


local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/kiwi541/Libray-branca-ak/refs/heads/main/README.md')))()
local Window = OrionLib:MakeWindow({
    Name = "PB HUB V9.0",
    HidePremium = false, 
    SaveConfig = true, 
    ConfigFolder = "PBHubConfigs",
    IntroEnabled = true,
    IntroText = "Team Police Brookhaven",
    IntroIcon = "rbxassetid://86898373680592",
    Icon = "rbxassetid://86898373680592",
    CloseCallback = function() 
        print("PB hub fechado")
    end
})


local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "ScreenGui"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

local Toggle = Instance.new("ImageButton")
Toggle.Name = "Toggle"
Toggle.Parent = ScreenGui
Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Toggle.BackgroundTransparency = 0.5
Toggle.Position = UDim2.new(0, 0, 0.454706937, 0)
Toggle.Size = UDim2.new(0, 50, 0, 50)
Toggle.Image = "rbxassetid://86898373680592"
Toggle.Draggable = true

local Corner = Instance.new("UICorner")
Corner.CornerRadius = UDim.new(0.1, 0)
Corner.Parent = Toggle

local isOn = false
local selectedPlayerName = nil

local function onButtonClicked()
    if gethui():FindFirstChild("Orion") then
        gethui().Orion.Enabled = not gethui().Orion.Enabled
    end
end

local function offButtonClicked()
    if gethui():FindFirstChild("Orion") then
        gethui().Orion.Enabled = not gethui().Orion.Enabled
    end
end

Toggle.MouseButton1Click:Connect(function()
    isOn = not isOn
    if isOn then
        Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        onButtonClicked()
    else
        Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        offButtonClicked()
    end
end)


local Tab = Window:MakeTab({
	Name = "Bem Vindo",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


-- Adicionar a seção "Olá (Nome do Jogador) Seja bem-vindo"
Tab:AddSection({
    Name = "Olá " .. game.Players.LocalPlayer.Name .. " Seja bem-vindo Soldado",
    Icon = creditTabImageId -- Definir o ícone da seção como o ID da imagem da aba
})


Tab:AddParagraph("Avantes Soldados","")


Tab:AddButton({
	Name = "Infinity Yield(Obrigatório)",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Infinite-Yield_500"))()
	print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "Items",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "Bombox Fe Tool",
	Callback = function()
      		local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")

-- Criar o item Boombox e adicioná-lo diretamente na Backpack
local i = Instance.new("Tool")
i.Name = "Boombox"
i.Parent = backpack  -- Agora é adicionado diretamente na Backpack
i.Grip = CFrame.new(0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 0, 0)
i.GripForward = Vector3.new(0, -1, 0)
i.GripRight = Vector3.new(0, 0, 1)
i.GripUp = Vector3.new(1, 0, 0)

local j = Instance.new("Part")
j.Name = "Handle"
j.Parent = i
j.Size = Vector3.new(1, 1.2, 1)
j.Color = Color3.new(0.0666667, 0.0666667, 0.0666667)
j.Transparency = 1
j.Anchored = false
j.CanCollide = false

local screenGui

local function createGui()
    screenGui = Instance.new("ScreenGui")
    screenGui.Name = "BoomboxGui"
    screenGui.Parent = game.Players.LocalPlayer.PlayerGui

    local frame = Instance.new("Frame")
    frame.Size = UDim2.new(0, 350, 0, 150)
    frame.Position = UDim2.new(0.5, -175, 0.5, -75)
    frame.BackgroundColor3 = Color3.fromRGB(0, 100, 255) -- Azul
    frame.BackgroundTransparency = 0.3 -- Transparente
    frame.BorderSizePixel = 0
    frame.Parent = screenGui

    local uiCorner = Instance.new("UICorner")
    uiCorner.CornerRadius = UDim.new(0, 15)
    uiCorner.Parent = frame

    local title = Instance.new("TextLabel")
    title.Size = UDim2.new(1, 0, 0.4, 0)
    title.Position = UDim2.new(0, 0, 0, 0)
    title.Text = "Coloque um ID de áudio e aperte Play Boombox By:Noly Fragiota"
    title.TextColor3 = Color3.fromRGB(255, 255, 255)
    title.BackgroundTransparency = 1
    title.Font = Enum.Font.GothamBold
    title.TextWrapped = true
    title.TextScaled = true
    title.Parent = frame

    local input = Instance.new("TextBox")
    input.Size = UDim2.new(0.9, 0, 0.18, 0)
    input.Position = UDim2.new(0.05, 0, 0.5, 0)
    input.Text = "1780625909"
    input.TextColor3 = Color3.fromRGB(255, 255, 255)
    input.BackgroundColor3 = Color3.fromRGB(0, 50, 150) -- Azul escuro
    input.BackgroundTransparency = 0.3
    input.Font = Enum.Font.SourceSans
    input.TextScaled = true
    input.BorderSizePixel = 0
    input.Parent = frame

    local inputCorner = Instance.new("UICorner")
    inputCorner.CornerRadius = UDim.new(0, 10)
    inputCorner.Parent = input

    -- Função para criar os botões
    local function createButton(text, positionY, callback)
        local button = Instance.new("TextButton")
        button.Size = input.Size
        button.Position = UDim2.new(0.05, 0, positionY, 0)
        button.Text = text
        button.TextColor3 = Color3.fromRGB(255, 255, 255)
        button.BackgroundColor3 = Color3.fromRGB(0, 50, 150) -- Azul escuro
        button.Font = Enum.Font.GothamBold
        button.TextScaled = true
        button.BorderSizePixel = 1
        button.BorderColor3 = Color3.fromRGB(255, 255, 255)
        button.Parent = frame

        local buttonCorner = Instance.new("UICorner")
        buttonCorner.CornerRadius = UDim.new(0, 10)
        buttonCorner.Parent = button

        button.MouseButton1Click:Connect(callback)
    end

    -- Função do botão Play (toca o áudio)
    createButton("Play", 0.75, function()
        local audioId = tonumber(input.Text) or 7337298420
        local args = {
            [1] = "PickingTools",
            [2] = "Assault"
        }

        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

        wait(0.1)

        local player = game.Players.LocalPlayer
        local backpack = player:WaitForChild("Backpack")

        local tool = backpack:WaitForChild("Assault", 10)

        if tool then
            tool.Parent = player.Character
        end

        wait(0.1)

        local args = {
            [1] = workspace.Model.Street.Street,
            [2] = game:GetService("Players").LocalPlayer.Character.Assault.Handle,
            [3] = Vector3.new(0.2, 0.3, -2.5),
            [4] = Vector3.new(115.74, 0.025, -36.11),
            [5] = game:GetService("Players").LocalPlayer.Character.Assault.GunScript_Local.MuzzleEffect,
            [6] = game:GetService("Players").LocalPlayer.Character.Assault.GunScript_Local.HitEffect,
            [7] = audioId,
            [8] = audioId,
            [9] = { [1] = false },
            [10] = {
                [1] = 25,
                [2] = Vector3.new(0.25, 0.25, 100),
                [3] = BrickColor.new(24),
                [4] = 0.25,
                [5] = Enum.Material.SmoothPlastic,
                [6] = 0.25
            },
            [11] = true,
            [12] = false
        }

        local muzzleEffect = game:GetService("Players").LocalPlayer.Character.Assault.GunScript_Local.MuzzleEffect
        local sound = muzzleEffect:FindFirstChildOfClass("Sound")

        if sound then
            sound.SoundId = "rbxassetid://" .. audioId
        end

        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1n"):FireServer(unpack(args))

        wait(1.4)

        game:GetService("ReplicatedStorage").RE["1Clea1rTool1s"]:FireServer("ClearAllTools")
    end)

    -- Função do botão Play All (toca para todos)
    createButton("Play All", 0.95, function()
        local audioId = tonumber(input.Text) or 7236490488
        local args = {workspace, audioId, 1}

        local soundID = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s")

        if soundID then
            soundID:FireServer(unpack(args))
            wait(6)
            soundID:FireServer(workspace, 0, 0)
        end
    end)
end

-- Função de equipar o item
local function onEquipped()
    createGui()
    local args = { "wear", 18756289999 }
    local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
    if updateAvatarEvent then
        updateAvatarEvent:FireServer(unpack(args))
    end
end

-- Função de desequipar o item
local function onUnequipped()
    if screenGui then
        screenGui:Destroy()
        screenGui = nil
    end
    local args = { "remove", 18756289999 }
    local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
    if updateAvatarEvent then
        updateAvatarEvent:FireServer(unpack(args))
    end
end

-- Conectar eventos de Equipar e Desequipar
i.Equipped:Connect(onEquipped)
i.Unequipped:Connect(onUnequipped)

i.Parent = backpack -- Agora o Boombox será adicionado à Backpack do jogador

print("Tool 'Boombox'.")
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Tool Black Role",
	Callback = function()
      		mouse = game.Players.LocalPlayer:GetMouse()
tool = Instance.new("Tool")
tool.RequiresHandle = false
tool.Name = "Click Black Role"
tool.Activated:connect(function()
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local Workspace = game:GetService("Workspace")

local angle = 1
local radius = 10
local blackHoleActive = false

local function setupPlayer()
    local character = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    local Folder = Instance.new("Folder", Workspace)
    local Part = Instance.new("Part", Folder)
    local Attachment1 = Instance.new("Attachment", Part)
    Part.Anchored = true
    Part.CanCollide = false
    Part.Transparency = 1

    return humanoidRootPart, Attachment1
end

local humanoidRootPart, Attachment1 = setupPlayer()

if not getgenv().Network then
    getgenv().Network = {
        BaseParts = {},
        Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
    }

    Network.RetainPart = function(part)
        if typeof(part) == "Instance" and part:IsA("BasePart") and part:IsDescendantOf(Workspace) then
            table.insert(Network.BaseParts, part)
            part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
            part.CanCollide = false
        end
    end

    local function EnablePartControl()
        LocalPlayer.ReplicationFocus = Workspace
        RunService.Heartbeat:Connect(function()
            sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
            for _, part in pairs(Network.BaseParts) do
                if part:IsDescendantOf(Workspace) then
                    part.Velocity = Network.Velocity
                end
            end
        end)
    end

    EnablePartControl()
end

local function ForcePart(v)
    if v:IsA("Part") and not v.Anchored and not v.Parent:FindFirstChild("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
        for _, x in next, v:GetChildren() do
            if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                x:Destroy()
            end
        end
        if v:FindFirstChild("Attachment") then
            v:FindFirstChild("Attachment"):Destroy()
        end
        if v:FindFirstChild("AlignPosition") then
            v:FindFirstChild("AlignPosition"):Destroy()
        end
        if v:FindFirstChild("Torque") then
            v:FindFirstChild("Torque"):Destroy()
        end
        v.CanCollide = false
        
        local Torque = Instance.new("Torque", v)
        Torque.Torque = Vector3.new(1000000, 1000000, 1000000)
        local AlignPosition = Instance.new("AlignPosition", v)
        local Attachment2 = Instance.new("Attachment", v)
        Torque.Attachment0 = Attachment2
        AlignPosition.MaxForce = math.huge
        AlignPosition.MaxVelocity = math.huge
        AlignPosition.Responsiveness = 500
        AlignPosition.Attachment0 = Attachment2
        AlignPosition.Attachment1 = Attachment1
    end
end

local function toggleBlackHole()
    blackHoleActive = not blackHoleActive
    if blackHoleActive then
        for _, v in next, Workspace:GetDescendants() do
            ForcePart(v)
        end

        Workspace.DescendantAdded:Connect(function(v)
            if blackHoleActive then
                ForcePart(v)
            end
        end)

        spawn(function()
            while blackHoleActive and RunService.RenderStepped:Wait() do
                angle = angle + math.rad(2)

                local offsetX = math.cos(angle) * radius
                local offsetZ = math.sin(angle) * radius

                Attachment1.WorldCFrame = humanoidRootPart.CFrame * CFrame.new(offsetX, 0, offsetZ)
            end
        end)
    else
        Attachment1.WorldCFrame = CFrame.new(0, -1000, 0)
    end
end

LocalPlayer.CharacterAdded:Connect(function()
    humanoidRootPart, Attachment1 = setupPlayer()
    if blackHoleActive then
        toggleBlackHole()
    end
end)

spawn(function()
    while true do
        RunService.RenderStepped:Wait()
        if blackHoleActive then
            angle = angle + math.rad(angleSpeed)
        end
    end
end)

toggleBlackHole()


end)
tool.Parent = game.Players.LocalPlayer.Backpack
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "tool Speed",
	Callback = function()
      		local player = game.Players.LocalPlayer
        local backpack = player:WaitForChild("Backpack")
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")
        local originalWalkSpeed = humanoid.WalkSpeed

        local h = Instance.new("Model", game:GetService("Lighting"))

        local i = Instance.new("Tool")
        i.Name = "SPEEDTOOL"
        i.Parent = h
        i.Grip = CFrame.new(0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 0, 0)
        i.GripForward = Vector3.new(0, -1, 0)
        i.GripRight = Vector3.new(0, 0, 1)
        i.GripUp = Vector3.new(1, 0, 0)
        i.TextureId = "rbxassetid://106331933297015"

        local j = Instance.new("Part")
        j.Name = "Handle"
        j.Parent = i
        j.Size = Vector3.new(1, 1.2, 1)
        j.Color = Color3.new(0.0666667, 0.0666667, 0.0666667)
        j.Transparency = 1
        j.Anchored = false
        j.CanCollide = false

        local function onEquipped()
            humanoid.WalkSpeed = 100

            local args = {
                [1] = "wear",
                [2] = 18385684081
            }
            local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
            if updateAvatarEvent then
                updateAvatarEvent:FireServer(unpack(args))
            end
        end

        local function onUnequipped()
            humanoid.WalkSpeed = originalWalkSpeed

            local args = {
                [1] = "remove",
                [2] = 18385684081
            }
            local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
            if updateAvatarEvent then
                updateAvatarEvent:FireServer(unpack(args))
            end
        end

        i.Equipped:Connect(onEquipped)
        i.Unequipped:Connect(onUnequipped)

        i.Parent = backpack

        print("Tool speed add")
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Couch",
	Callback = function()
      	local args = {
                [1] = "PickingTools",
                [2] = "Couch"
            }
            game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Cartão Da Agência",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "KeyCardDarkGreen"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Cartão da elétrica",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "PowerKeyCard"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Arco",
	Callback = function()
      		        local args = {
            [1] = "PickingTools",
            [2] = "Arch"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Crystal 1",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "Crystals"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Crystal 2",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "Crystal"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Agência Book",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "AgencyBook"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "OldKey",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "OldKey"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Arma De Assalto",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "Assault"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Shotgun",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "Shotgun"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


local Section = Tab:AddSection({
    Name = "Config tool"
})

local args = {
    [1] = "PickingTools",
    [2] = ""
}

local function pegarItem(itemName)
    args[2] = itemName
    game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Too1l"):InvokeServer(unpack(args))
end

Tab:AddTextbox({
    Name = "Item Name",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        pegarItem(value)
    end
})

Tab:AddButton({
    Name = "Pegar Item",
    Callback = function()
        local itemName = ItemPickerTab:GetTextbox("Item Name").Value
        pegarItem(itemName)
    end
})
local Section = Tab:AddSection({
    Name = "Bomb"
})
Tab:AddButton({
Name = "FireX",
Callback = function()
local args = {
    [1] = "Bomb1NCD3NT"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Blo1wBomb1sServe1r"):FireServer(unpack(args))
wait(1)
local args = {
    [1] = "Bomb1NCD3NT"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Blo1wBomb1sServe1r"):FireServer(unpack(args))
wait(1)
local args = {
    [1] = "Bomb1NCD3NT"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Blo1wBomb1sServe1r"):FireServer(unpack(args))
wait(1)
end
})
Tab:AddButton({
Name = "Bomb",
Callback = function()
local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

local itemToDuplicate = backpack:FindFirstChild("Bomb") -- Nome do item

if itemToDuplicate then
    local clonedItem = itemToDuplicate:Clone() -- Clonar o item
    clonedItem.Parent = backpack -- Colocar o clone no inventário
    print("Item duplicado!")
else
    print("Item não encontrado no inventário.")
end
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Bomb")
end
})


local Section = Tab:AddSection({
    Name = "Tools Fake/Visual"
})
Tab:AddButton({
Name = "FE PUNCH",
Callback = function()
 loadstring(game:HttpGet(('http://pastefy.app/GvnHVjT5/raw'),true))()
end
})
Tab:AddButton({
Name = "Telekiness [FE]",
Callback = function()
 loadstring(game:HttpGet(('https://raw.githubusercontent.com/SAZXHUB/Control-update/main/README.md'),true))()
end
})
Tab:AddButton({
Name = "f3x",
Callback = function()
 loadstring(game:GetObjects("rbxassetid://6695644299")[1].Source)()
end
})
Tab:AddButton({
Name = "Btools",
Callback = function()
 loadstring(game:HttpGet("https://raw.githubusercontent.com/err0r129/PqpHadesBlair/main/Bao.lua"))()
end
})
Tab:AddButton({
Name = "Click TP",
Callback = function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/err0r129/KptHadesBlair/main/Bao.lua"))()
end
})
local Section = Tab:AddSection({
    Name = "Taser"
})
Tab:AddButton({
	Name = "Give Taser",
	Callback = function()
      	local args = {
    [1] = "PickingTools",
    [2] = "Taser"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
  	end    
})

local toggleActive = false
local function loopTaser()
while toggleActive do
local args = {
    [1] = "Taser",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.Taser.ToolSound:FireServer(unpack(args))
wait(0.111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Taser",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopTaser()
end
end
})
local Section = Tab:AddSection({
    Name = "FireX"
})
Tab:AddButton({
	Name = "Give FireX",
	Callback = function()
      	local args = {
    [1] = "PickingTools",
    [2] = "FireX"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
  	end    
})

local toggleActive = false
local function loopFireX()
while toggleActive do
local args = {
    [1] = "FireX",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.FireX.ToolSound:FireServer(unpack(args))
wait(0.111111111111111111111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop FireX",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFireX()
end
end
})
local Section = Tab:AddSection({
    Name = "Basketball"
})
Tab:AddButton({
	Name = "Give Basketball",
	Callback = function()
      	local args = {
    [1] = "PickingTools",
    [2] = "Basketball"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--Ball

local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

local itemToDuplicate = backpack:FindFirstChild("Basketball") -- Nome do item

if itemToDuplicate then
    local clonedItem = itemToDuplicate:Clone() -- Clonar o item
    clonedItem.Parent = backpack -- Colocar o clone no inventário
    print("Item duplicado!")
else
    print("Item não encontrado no inventário.")
end
  	end    
})

local toggleActive = false
local function loopBall()
while toggleActive do
local args = {
    [1] = Vector3.new(-30.919673919677734, 0.02500009536743164, 190.3595733642578)
}

game:GetService("Players").LocalPlayer.Character.Basketball.ClickEvent:FireServer(unpack(args))
wait(1) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Ball",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopBall()
end
end
})
local Section = Tab:AddSection({
    Name = "Gun mod"
})
Tab:AddButton({
Name = "Give Sniper Fire",
Callback = function()
 local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
 local args = {
    [1] = "PickingTools",
    [2] = "PaperbagFire"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("PaperbagFire")
    end
})
Tab:AddButton({
Name = "Equip all guns",
Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Assault"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local args = {
    [1] = "PickingTools",
    [2] = "Shotgun"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local args = {
    [1] = "PickingTools",
    [2] = "GlockBrown"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("Shotgun")
equiparItem("Assault")
equiparItem("GlockBrown")
end
})
Tab:AddButton({
Name = "Give Gun Smoke",
Callback = function()
 local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
 local args = {
    [1] = "PickingTools",
    [2] = "FireX"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("FireX")
    end
})

local toggleActive = false
local function loopSmoke()
while toggleActive do
local args = {
    [1] = "FireX",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.FireX.ToolSound:FireServer(unpack(args))
wait(0.111111111111111111111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Smoke",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopSmoke()
end
end
})

Tab:AddButton({
Name = "Give Gun Taser",
Callback = function()
 local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
 local args = {
    [1] = "PickingTools",
    [2] = "Taser"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("Taser")
    end
})

local toggleActive = false
local function loopTaser()
while toggleActive do
local args = {
    [1] = "Taser",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.FireX.ToolSound:FireServer(unpack(args))
wait(0.111111111111111111111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Taser",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopTaser()
end
end
})


local Tab = Window:MakeTab({
	Name = "Matar",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


local running = false
local stopEvent

local Players = game:GetService("Players")
local PlayerList = {}
local TargetPlayerName = nil
local running = false
local stopEvent = nil

-- Função para atualizar a lista de jogadores no dropdown
local function UpdatePlayerList()
    PlayerList = {}
    for _, player in pairs(Players:GetPlayers()) do
        table.insert(PlayerList, player.Name)
    end
    -- Atualiza as opções do dropdown apenas se ele foi criado
    if Dropdown then
        Dropdown:UpdateOptions(PlayerList)
    end
end

-- Atualiza a lista de jogadores inicialmente
UpdatePlayerList()

local Dropdown = Tab:AddDropdown({
    Name = "Selecione o Jogador",
    Default = "Nenhum Jogador",
    Options = PlayerList,
    Callback = function(selectedPlayerName)
        TargetPlayerName = selectedPlayerName
    end
})

Tab:AddButton({
    Name = "Matar Jogador",
    Callback = function()
        local lp = Players.LocalPlayer
        local Target = nil

        -- Verificar se o jogador selecionado existe
        for _, player in pairs(Players:GetPlayers()) do
            if player.Name == TargetPlayerName then
                Target = player
                break
            end
        end

        if Target and Target.Character and Target.Character:FindFirstChild("HumanoidRootPart") then
            if running then return end -- Prevent multiple activations
            running = true

            local Thrust = Instance.new('BodyThrust', lp.Character.HumanoidRootPart)
            Thrust.Force = Vector3.new(1000000000000000, 1000000000000000, 1000000000000000)
            Thrust.Name = "TemplariosForce"
            local direction = 1

            stopEvent = game:GetService("RunService").Heartbeat:Connect(function()
                if lp.Character and lp.Character:FindFirstChild("Humanoid") and lp.Character.Humanoid.Health > 0 then
                    lp.Character.HumanoidRootPart.CFrame = Target.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3)

                    if lp.Character.HumanoidRootPart.Position.Z >= Target.Character.HumanoidRootPart.Position.Z + 5 then
                        direction = -1
                    elseif lp.Character.HumanoidRootPart.Position.Z <= Target.Character.HumanoidRootPart.Position.Z - 5 then
                        direction = 1
                    end

                    Thrust.Location = Target.Character.HumanoidRootPart.Position - Vector3.new(0, 0, 10 * direction)
                else
                    -- Se o jogador morrer, desconectar o evento
                    stopEvent:Disconnect()
                    stopEvent = nil
                    running = false
                    if lp.Character and lp.Character:FindFirstChild("HumanoidRootPart") then
                        local Thrust = lp.Character.HumanoidRootPart:FindFirstChild("TemplariosForce")
                        if Thrust then Thrust:Destroy() end
                    end
                end
            end)
        else
            OrionLib:MakeNotification({
                Name = "Templarios Hub",
                Content = "Selecione o Jogador!",
                Time = 5
            })
        end
    end
})

-- Atualizar a lista de jogadores a cada vez que a lista de jogadores muda
Players.PlayerAdded:Connect(UpdatePlayerList)
Players.PlayerRemoving:Connect(UpdatePlayerList)

local Section = Tab:AddSection({

	Name = "Parar de Matar"

})

Tab:AddButton({
	Name = "Parar de Matar",
	Callback = function()
		if running then
			if stopEvent then
				stopEvent:Disconnect() -- Stop the Heartbeat connection
				stopEvent = nil
			end
			running = false
			if lp.Character and lp.Character:FindFirstChild("HumanoidRootPart") then
				local Thrust = lp.Character.HumanoidRootPart:FindFirstChild("TemplariosForce")
				if Thrust then Thrust:Destroy() end -- Remove the thrust effect
			end
			OrionLib:MakeNotification({
				Name = "Templarios Hub",
				Content = "A função foi parada.",
				Time = 5
			})
		else
			OrionLib:MakeNotification({
				Name = "Templarios Hub",
				Content = "Nada está em andamento!",
				Time = 5
			})
		end
	end
})

local Section = Tab:AddSection({

	Name = "Pegar Sofa"

})

Tab:AddButton({

    Name = "Pegar Sofa",

    Callback = function()

        local args = {

    [1] = "PickingTools",

    [2] = "Couch"

}

 

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

 local function equiptool()
  for i,v in ipairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
    if v:IsA("Tool") then
      v.Parent = game.Players.LocalPlayer.Character
    end
  end
end

equiptool()

    end

})

local Section = Tab:AddSection({

	Name = "Espectar Jogador"

})

-- Função para retornar a visão normal da câmera
local function resetCameraView()
    -- Define o CameraSubject de volta para o jogador local
    game:GetService("Workspace").CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character
end

Tab:AddTextbox({
    Name = "Espectar Jogador (Insira o Nome do Jogador)",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        print("Valor digitado:", Value)  -- Debug: Verifica se o valor está sendo capturado corretamente
        
        -- Encontra o jogador com o nome fornecido
        local player = nil
        for _, ply in pairs(game.Players:GetPlayers()) do
            if string.lower(string.sub(ply.Name, 1, #Value)) == string.lower(Value) then
                player = ply
                break
            end
        end
        
        if player then
            print("Jogador encontrado:", player.Name)  -- Debug: Verifica se o jogador foi encontrado
            
            -- Define o jogador como o CameraSubject para mudar a visão
            game:GetService("Workspace").CurrentCamera.CameraSubject = player.Character
        else
            print("Jogador não encontrado!")
        end
    end
})

Tab:AddButton({
    Name = "Parar de Espectar Jogador",
    Callback = function()
        resetCameraView()
    end
})

Tab:AddParagraph("Hey!","Não Precisa colocar o nome completo do jogador, apenas colocando as letras iniciais do nome dele o Espectar Jogador ja funciona, coloque o Nome Original do Jogador. :D")

 local Section = Tab:AddSection({

	Name = "Fling All"

})

Tab:AddButton({

    Name = "Fling All",

    Callback = function()

        local Targets = {"All"} -- "All", "Target Name", "arian_was_here"

local Players = game:GetService("Players")
local Player = Players.LocalPlayer

local AllBool = false

local GetPlayer = function(Name)
    Name = Name:lower()
    if Name == "all" or Name == "others" then
        AllBool = true
        return
    elseif Name == "random" then
        local GetPlayers = Players:GetPlayers()
        if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
        return GetPlayers[math.random(#GetPlayers)]
    elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
        for _,x in next, Players:GetPlayers() do
            if x ~= Player then
                if x.Name:lower():match("^"..Name) then
                    return x;
                elseif x.DisplayName:lower():match("^"..Name) then
                    return x;
                end
            end
        end
    else
        return
    end
end

local Message = function(_Title, _Text, Time)
    game:GetService("StarterGui"):SetCore("SendNotification", {Title = _Title, Text = _Text, Duration = Time})
end

local SkidFling = function(TargetPlayer)
    local Character = Player.Character
    local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
    local RootPart = Humanoid and Humanoid.RootPart

    local TCharacter = TargetPlayer.Character
    local THumanoid
    local TRootPart
    local THead
    local Accessory
    local Handle

    if TCharacter:FindFirstChildOfClass("Humanoid") then
        THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
    end
    if THumanoid and THumanoid.RootPart then
        TRootPart = THumanoid.RootPart
    end
    if TCharacter:FindFirstChild("Head") then
        THead = TCharacter.Head
    end
    if TCharacter:FindFirstChildOfClass("Accessory") then
        Accessory = TCharacter:FindFirstChildOfClass("Accessory")
    end
    if Accessoy and Accessory:FindFirstChild("Handle") then
        Handle = Accessory.Handle
    end

    if Character and Humanoid and RootPart then
        if RootPart.Velocity.Magnitude < 50 then
            getgenv().OldPos = RootPart.CFrame
        end
        if THumanoid and THumanoid.Sit and not AllBool then
            return Message("Error Occurred", "Targeting is sitting", 5) -- u can remove dis part if u want lol
        end
        if THead then
            workspace.CurrentCamera.CameraSubject = THead
        elseif not THead and Handle then
            workspace.CurrentCamera.CameraSubject = Handle
        elseif THumanoid and TRootPart then
            workspace.CurrentCamera.CameraSubject = THumanoid
        end
        if not TCharacter:FindFirstChildWhichIsA("BasePart") then
            return
        end
        
        local FPos = function(BasePart, Pos, Ang)
            RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
            Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
            RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
            RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
        end
        
        local SFBasePart = function(BasePart)
            local TimeToWait = 2
            local Time = tick()
            local Angle = 0

            repeat
                if RootPart and THumanoid then
                    if BasePart.Velocity.Magnitude < 50 then
                        Angle = Angle + 100

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()
                    else
                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()
                        
                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()
                    end
                else
                    break
                end
            until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
        end
        
        workspace.FallenPartsDestroyHeight = 0/0
        
        local BV = Instance.new("BodyVelocity")
        BV.Name = "EpixVel"
        BV.Parent = RootPart
        BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
        BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
        
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
        
        if TRootPart and THead then
            if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
                SFBasePart(THead)
            else
                SFBasePart(TRootPart)
            end
        elseif TRootPart and not THead then
            SFBasePart(TRootPart)
        elseif not TRootPart and THead then
            SFBasePart(THead)
        elseif not TRootPart and not THead and Accessory and Handle then
            SFBasePart(Handle)
        else
            return Message("Error Occurred", "Target is missing everything", 5)
        end
        
        BV:Destroy()
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
        workspace.CurrentCamera.CameraSubject = Humanoid
        
        repeat
            RootPart.CFrame = getgenv().OldPos * CFrame.new(0, .5, 0)
            Character:SetPrimaryPartCFrame(getgenv().OldPos * CFrame.new(0, .5, 0))
            Humanoid:ChangeState("GettingUp")
            table.foreach(Character:GetChildren(), function(_, x)
                if x:IsA("BasePart") then
                    x.Velocity, x.RotVelocity = Vector3.new(), Vector3.new()
                end
            end)
            task.wait()
        until (RootPart.Position - getgenv().OldPos.p).Magnitude < 25
        workspace.FallenPartsDestroyHeight = getgenv().FPDH
    else
        return Message("Ocorreu um Erro", "Erro aleatório", 5)
    end
end

if not Welcome then Message("#TemplariosTeam!", "Aproveite!", 5) end
getgenv().Welcome = true
if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end

if AllBool then
    for _,x in next, Players:GetPlayers() do
        SkidFling(x)
    end
end

for _,x in next, Targets do
    if GetPlayer(x) and GetPlayer(x) ~= Player then
        if GetPlayer(x).UserId ~= 4550163963 then
            local TPlayer = GetPlayer(x)
            if TPlayer then
                SkidFling(TPlayer)
            end
        else
            Message("Ocorrreu um Erro", "Este usuário está na lista de permissões ! (Owner)", 5)
        end
    elseif not GetPlayer(x) and not AllBool then
        Message("Ocorreu um Erro", "Nome de Usuário Invalido", 5)
    end
end


    end

})

Tab:AddButton({

    Name = "Fling All (Sofa Automatico)",

    Callback = function()

        local args = {

    [1] = "PickingTools",

    [2] = "Couch"

}

 

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

local Targets = {"All"} -- "All", "Target Name", "arian_was_here"

local Players = game:GetService("Players")
local Player = Players.LocalPlayer

local AllBool = false

local GetPlayer = function(Name)
    Name = Name:lower()
    if Name == "all" or Name == "others" then
        AllBool = true
        return
    elseif Name == "random" then
        local GetPlayers = Players:GetPlayers()
        if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
        return GetPlayers[math.random(#GetPlayers)]
    elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
        for _,x in next, Players:GetPlayers() do
            if x ~= Player then
                if x.Name:lower():match("^"..Name) then
                    return x;
                elseif x.DisplayName:lower():match("^"..Name) then
                    return x;
                end
            end
        end
    else
        return
    end
end

local Message = function(_Title, _Text, Time)
    game:GetService("StarterGui"):SetCore("SendNotification", {Title = _Title, Text = _Text, Duration = Time})
end

local SkidFling = function(TargetPlayer)
    local Character = Player.Character
    local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
    local RootPart = Humanoid and Humanoid.RootPart

    local TCharacter = TargetPlayer.Character
    local THumanoid
    local TRootPart
    local THead
    local Accessory
    local Handle

    if TCharacter:FindFirstChildOfClass("Humanoid") then
        THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
    end
    if THumanoid and THumanoid.RootPart then
        TRootPart = THumanoid.RootPart
    end
    if TCharacter:FindFirstChild("Head") then
        THead = TCharacter.Head
    end
    if TCharacter:FindFirstChildOfClass("Accessory") then
        Accessory = TCharacter:FindFirstChildOfClass("Accessory")
    end
    if Accessoy and Accessory:FindFirstChild("Handle") then
        Handle = Accessory.Handle
    end

    if Character and Humanoid and RootPart then
        if RootPart.Velocity.Magnitude < 50 then
            getgenv().OldPos = RootPart.CFrame
        end
        if THumanoid and THumanoid.Sit and not AllBool then
            return Message("Error Occurred", "Targeting is sitting", 5) -- u can remove dis part if u want lol
        end
        if THead then
            workspace.CurrentCamera.CameraSubject = THead
        elseif not THead and Handle then
            workspace.CurrentCamera.CameraSubject = Handle
        elseif THumanoid and TRootPart then
            workspace.CurrentCamera.CameraSubject = THumanoid
        end
        if not TCharacter:FindFirstChildWhichIsA("BasePart") then
            return
        end
        
        local FPos = function(BasePart, Pos, Ang)
            RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
            Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
            RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
            RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
        end
        
        local SFBasePart = function(BasePart)
            local TimeToWait = 2
            local Time = tick()
            local Angle = 0

            repeat
                if RootPart and THumanoid then
                    if BasePart.Velocity.Magnitude < 50 then
                        Angle = Angle + 100

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()
                    else
                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()
                        
                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()
                    end
                else
                    break
                end
            until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
        end
        
        workspace.FallenPartsDestroyHeight = 0/0
        
        local BV = Instance.new("BodyVelocity")
        BV.Name = "EpixVel"
        BV.Parent = RootPart
        BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
        BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
        
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
        
        if TRootPart and THead then
            if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
                SFBasePart(THead)
            else
                SFBasePart(TRootPart)
            end
        elseif TRootPart and not THead then
            SFBasePart(TRootPart)
        elseif not TRootPart and THead then
            SFBasePart(THead)
        elseif not TRootPart and not THead and Accessory and Handle then
            SFBasePart(Handle)
        else
            return Message("Error Occurred", "Target is missing everything", 5)
        end
        
        BV:Destroy()
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
        workspace.CurrentCamera.CameraSubject = Humanoid
        
        repeat
            RootPart.CFrame = getgenv().OldPos * CFrame.new(0, .5, 0)
            Character:SetPrimaryPartCFrame(getgenv().OldPos * CFrame.new(0, .5, 0))
            Humanoid:ChangeState("GettingUp")
            table.foreach(Character:GetChildren(), function(_, x)
                if x:IsA("BasePart") then
                    x.Velocity, x.RotVelocity = Vector3.new(), Vector3.new()
                end
            end)
            task.wait()
        until (RootPart.Position - getgenv().OldPos.p).Magnitude < 25
        workspace.FallenPartsDestroyHeight = getgenv().FPDH
    else
        return Message("Ocorreu um Erro", "Erro aleatório", 5)
    end
end

if not Welcome then Message("#TemplariosTeam!", "Aproveite!", 5) end
getgenv().Welcome = true
if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end

if AllBool then
    for _,x in next, Players:GetPlayers() do
        SkidFling(x)
    end
end

for _,x in next, Targets do
    if GetPlayer(x) and GetPlayer(x) ~= Player then
        if GetPlayer(x).UserId ~= 4550163963 then
            local TPlayer = GetPlayer(x)
            if TPlayer then
                SkidFling(TPlayer)
            end
        else
            Message("Ocorrreu um Erro", "Este usuário está na lista de permissões ! (Owner)", 5)
        end
    elseif not GetPlayer(x) and not AllBool then
        Message("Ocorreu um Erro", "Nome de Usuário Invalido", 5)
    end
end

local args = {

    [1] = "PickingTools",

    [2] = "Couch"

}

 

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))


    end

})

local Section = Tab:AddSection({

	Name = "Fling na Pessoa que Descer do Sofa"

})

Tab:AddButton({

    Name = "Fling na Pessoa que Descer do Sofa",

    Callback = function()

        loadstring(game:HttpGet(('https://raw.githubusercontent.com/0Ben1/fe/main/obf_5wpM7bBcOPspmX7lQ3m75SrYNWqxZ858ai3tJdEAId6jSI05IOUB224FQ0VSAswH.lua.txt'),true))()

    end

})

Tab:AddButton({

    Name = "Fling na Pessoa que Descer do Sofa (Sofa Automatico)",

    Callback = function()

        local args = {

    [1] = "PickingTools",

    [2] = "Couch"

}

 

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

loadstring(game:HttpGet(('https://raw.githubusercontent.com/0Ben1/fe/main/obf_5wpM7bBcOPspmX7lQ3m75SrYNWqxZ858ai3tJdEAId6jSI05IOUB224FQ0VSAswH.lua.txt'),true))()

    end

})


local Tab = Window:MakeTab({
	Name = "Ilhas Adm",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


-- VariÃ¡veis
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local player = Players.LocalPlayer

-- PosiÃ§Ã£o do mapa secreto
local mapPosition = Vector3.new(10000, 500, 10000)

-- FunÃ§Ã£o para gerar a ilha
local function generateIsland()
    -- Criar o chÃ£o de grama
    local grass = Instance.new("Part")
    grass.Size = Vector3.new(200, 2, 200)
    grass.Position = mapPosition
    grass.Anchored = true
    grass.Material = Enum.Material.Grass
    grass.Color = Color3.fromRGB(34, 139, 34)
    grass.Parent = game.Workspace

    -- Criar Ã¡rvores arredondadas
    local function createTree(position)
        local trunk = Instance.new("Part")
        trunk.Size = Vector3.new(2, 8, 2)
        trunk.Position = position
        trunk.Anchored = true
        trunk.Material = Enum.Material.Wood
        trunk.Color = Color3.fromRGB(139, 69, 19)
        trunk.Parent = game.Workspace

        local leaves = Instance.new("Part")
        leaves.Size = Vector3.new(8, 8, 8)
        leaves.Position = position + Vector3.new(0, 6, 0)
        leaves.Anchored = true
        leaves.Shape = Enum.PartType.Ball
        leaves.Material = Enum.Material.Grass
        leaves.Color = Color3.fromRGB(34, 139, 34)
        leaves.Parent = game.Workspace
    end

    -- Posicionamento das Ã¡rvores
    local treePositions = {
        mapPosition + Vector3.new(60, 1, 60),
        mapPosition + Vector3.new(-60, 1, 60),
        mapPosition + Vector3.new(60, 1, -60),
        mapPosition + Vector3.new(-60, 1, -60),
        mapPosition + Vector3.new(30, 1, 70),
        mapPosition + Vector3.new(-30, 1, 70),
        mapPosition + Vector3.new(50, 1, 30),
        mapPosition + Vector3.new(-50, 1, -30),
        mapPosition + Vector3.new(20, 1, -60),
        mapPosition + Vector3.new(-20, 1, 50),
        mapPosition + Vector3.new(70, 1, -20),
        mapPosition + Vector3.new(-70, 1, 20),
    }

    for _, pos in pairs(treePositions) do
        createTree(pos)
    end

    -- Criar muros ao redor da ilha
    local function createWall(position, size)
        local wall = Instance.new("Part")
        wall.Size = size
        wall.Position = position
        wall.Anchored = true
        wall.Material = Enum.Material.Brick
        wall.Color = Color3.fromRGB(150, 75, 0)
        wall.Parent = game.Workspace
    end

    -- Criando os muros
    createWall(mapPosition + Vector3.new(0, 6, 101), Vector3.new(200, 12, 2)) -- Frente
    createWall(mapPosition + Vector3.new(0, 6, -101), Vector3.new(200, 12, 2)) -- TrÃ¡s
    createWall(mapPosition + Vector3.new(101, 6, 0), Vector3.new(2, 12, 200)) -- Direita
    createWall(mapPosition + Vector3.new(-101, 6, 0), Vector3.new(2, 12, 200)) -- Esquerda
end

-- OpÃ§Ã£o para gerar a ilha
Tab:AddButton({
    Name = "Gerar Ilha Sharingan/Kaimui",
    Callback = function()
        generateIsland()
    end
})

-- FunÃ§Ã£o para teleportar para a ilha com efeito
local function teleportWithEffect()
    local character = player.Character or player.CharacterAdded:Wait()
    local root = character:FindFirstChild("HumanoidRootPart") or character:WaitForChild("HumanoidRootPart", 3)

    if not root then return end -- Impede erro caso o root nÃ£o seja encontrado

    local PlayerGui = player:FindFirstChildOfClass("PlayerGui")

    -- Criando a ScreenGui
    local ScreenGui = Instance.new("ScreenGui")
    ScreenGui.Parent = PlayerGui

    -- Criando a ImageLabel
    local ImageLabel = Instance.new("ImageLabel")
    ImageLabel.Parent = ScreenGui
    ImageLabel.Size = UDim2.new(0, 500, 0, 500)
    ImageLabel.Position = UDim2.new(0.5, -250, 0.42, -250)
    ImageLabel.Image = "rbxassetid://117307865668673"
    ImageLabel.BackgroundTransparency = 1

    -- Criando o Sound
    local Sound = Instance.new("Sound")
    Sound.Parent = PlayerGui
    Sound.SoundId = "rbxassetid://1592708450"
    Sound.Volume = 2
    Sound:Play()

    -- Efeito de rotaÃ§Ã£o
    local RotationSpeed = -5
    local RotationConnection
    RotationConnection = RunService.RenderStepped:Connect(function(deltaTime)
        ImageLabel.Rotation = ImageLabel.Rotation + (RotationSpeed * (deltaTime * 60))
    end)

    -- Teleporta o jogador 2 segundos depois, enquanto a animaÃ§Ã£o ocorre
    task.spawn(function()
        task.wait(2)
        if root then
            root.CFrame = CFrame.new(mapPosition + Vector3.new(0, 3, 0))
        end
    end)

    -- Espera 3 segundos antes do efeito de desaparecimento
    task.wait(3)

    -- Efeito de diminuiÃ§Ã£o atÃ© sumir
    for i = 1, 30 do
        ImageLabel.Size = ImageLabel.Size - UDim2.new(0, 15, 0, 15)
        ImageLabel.Position = UDim2.new(0.5, -ImageLabel.Size.X.Offset / 2, 0.42, -ImageLabel.Size.Y.Offset / 2)
        task.wait(0.05)
    end

    -- Remover tudo
    RotationConnection:Disconnect()
    ScreenGui:Destroy()
    Sound:Destroy()
end

-- OpÃ§Ã£o para teleportar para a ilha
Tab:AddButton({
    Name = "Teleportar para ilha Sharingan",
    Callback = function()
        teleportWithEffect()
    end
})


-- FunÃ§Ã£o para teleportar para a ilha com efeito
local function teleportWithEffect()
    local character = player.Character or player.CharacterAdded:Wait()
    local root = character:FindFirstChild("HumanoidRootPart") or character:WaitForChild("HumanoidRootPart", 3)

    if not root then return end -- Impede erro caso o root nÃ£o seja encontrado

    local PlayerGui = player:FindFirstChildOfClass("PlayerGui")

    -- Criando a ScreenGui
    local ScreenGui = Instance.new("ScreenGui")
    ScreenGui.Parent = PlayerGui

    -- Criando a ImageLabel
    local ImageLabel = Instance.new("ImageLabel")
    ImageLabel.Parent = ScreenGui
    ImageLabel.Size = UDim2.new(0, 500, 0, 500)
    ImageLabel.Position = UDim2.new(0.5, -250, 0.42, -250)
    ImageLabel.Image = "rbxassetid://110470606429328"
    ImageLabel.BackgroundTransparency = 1

    -- Criando o Sound
    local Sound = Instance.new("Sound")
    Sound.Parent = PlayerGui
    Sound.SoundId = "rbxassetid://997057912"
    Sound.Volume = 2
    Sound:Play()

    -- Efeito de rotaÃ§Ã£o
    local RotationSpeed = -5
    local RotationConnection
    RotationConnection = RunService.RenderStepped:Connect(function(deltaTime)
        ImageLabel.Rotation = ImageLabel.Rotation + (RotationSpeed * (deltaTime * 60))
    end)

    -- Teleporta o jogador 2 segundos depois, enquanto a animaÃ§Ã£o ocorre
    task.spawn(function()
        task.wait(2)
        if root then
            root.CFrame = CFrame.new(mapPosition + Vector3.new(0, 3, 0))
        end
    end)

    -- Espera 3 segundos antes do efeito de desaparecimento
    task.wait(3)

    -- Efeito de diminuiÃ§Ã£o atÃ© sumir
    for i = 1, 30 do
        ImageLabel.Size = ImageLabel.Size - UDim2.new(0, 15, 0, 15)
        ImageLabel.Position = UDim2.new(0.5, -ImageLabel.Size.X.Offset / 2, 0.42, -ImageLabel.Size.Y.Offset / 2)
        task.wait(0.05)
    end

    -- Remover tudo
    RotationConnection:Disconnect()
    ScreenGui:Destroy()
    Sound:Destroy()
end

-- OpÃ§Ã£o para teleportar para a ilha
Tab:AddButton({
    Name = "Teleportar para ilha Kamui",
    Callback = function()
        teleportWithEffect()
    end
})


local Section = Tab:AddSection({
	Name = "models"
})


Tab:AddButton({
	Name = "gerar Brookhaven Fake",
	Callback = function()
      		local ModelObject = game:GetObjects("rbxassetid://13904015351")[1]

ModelObject.Parent = workspace

for _, part in pairs(ModelObject:GetDescendants()) do
    if part:IsA("BasePart") then
        part.Position = part.Position + Vector3.new(10099, 1000, 0)
    end
end

local player = game.Players.LocalPlayer
if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
    local modelPosition = ModelObject.PrimaryPart.Position
    player.Character.HumanoidRootPart.CFrame = CFrame.new(modelPosition.X, modelPosition.Y + 90, modelPosition.Z)
    wait(2)
    player.Character.HumanoidRootPart.CFrame = CFrame.new(modelPosition.X, modelPosition.Y + 90, modelPosition.Z)
end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Teleporte Brookhaven Fake",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(9189.8037109375, 797.5509033203125, -396.98638916015625)
print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
Name = "House",
Icon = "rbxassetid://18319058691",
PremiumOnly = false
})


local casaNumbers = {}
for i = 1, 35 do
if i ~= 8 and i ~= 9 and i ~= 10 then
table.insert(casaNumbers, tostring(i))
end
end

local selectedCasaNumber = nil

Tab:AddDropdown({
Name = "Escolha o número da casa",
Options = casaNumbers,
Callback = function(number)
selectedCasaNumber = tonumber(number)
end
})

Tab:AddButton({
Name = "Pegar Permissão",
Callback = function()
if selectedCasaNumber then
local args = {
[1] = "GivePermissionLoopToServer",
[2] = game:GetService("Players").LocalPlayer,
[3] = selectedCasaNumber
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))

else
print("Nenhum número de casa selecionado.")
end
end
})


local Section = Tab:AddSection({
    Name = "Loops "
})
local toggleState = false
local function toggleCurtains()
while toggleState do
local args = {
[1] = "Curtains"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(1) -- ajusta o tempo de espera conforme necessário
end
end

Tab:AddToggle({
Name = "Toggle Curtains",
Default = false,
Callback = function(value)
toggleState = value
if toggleState then
toggleCurtains()
end
end
})

local toggleState = false
local function togglePool()
while toggleState do
local args = {
[1] = "PoolOnOff"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(1) -- ajusta o tempo de espera conforme necessário
end
end

Tab:AddToggle({
Name = "Toggle Pool",
Default = false,
Callback = function(value)
toggleState = value
if toggleState then
togglePool()
end
end
})

local toggleState = false
local function toggleGarageDoor()
while toggleState do
local args = {
[1] = "GarageDoor"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(1) -- ajusta o tempo de espera conforme necessário
end
end

Tab:AddToggle({
Name = "Toggle Garage Door",
Default = false,
Callback = function(value)
toggleState = value
if toggleState then
toggleGarageDoor()
end
end
})
local Section = Tab:AddSection({
    Name = "Fire Function"
})
Tab:AddButton({
	Name = "Fire On",
	Callback = function()
      	local args = {
    [1] = "PlayerWantsFireOnFirePassNotShowingAnyone"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Fire Off",
	Callback = function()
      	local args = {
    [1] = "PlayerWantsFireOffFirePassNotShowingAnyone"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
  	end    
})

local toggleActive = false
local function repeatRemote()
while toggleActive do
local args = {
[1] = "PlayerWantsFireOnFirePassNotShowingAnyone"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(0.1) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Fire ",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
repeatRemote()
end
end
})

local toggleActive = false
local function repeatRemote()
while toggleActive do
--This is a simple roblox game crasher made by casanova
--Github cfreemepq
--fixed script*

while wait(0.6) do --// don't change it's the best
game:GetService("NetworkClient"):SetOutgoingKBPSLimit(math.huge)
local function getmaxvalue(val)
   local mainvalueifonetable = 499999
   if type(val) ~= "number" then
       return nil
   end
   local calculateperfectval = (mainvalueifonetable/(val+2))
   return calculateperfectval
end

local function bomb(tableincrease, tries)
local maintable = {}
local spammedtable = {}

table.insert(spammedtable, {})
z = spammedtable[1]

for i = 1, tableincrease do
    local tableins = {}
    table.insert(z, tableins)
    z = tableins
end

local calculatemax = getmaxvalue(tableincrease)
local maximum

if calculatemax then
     maximum = calculatemax
     else
     maximum = 999999
end

for i = 1, maximum do
     table.insert(maintable, spammedtable)
end

for i = 1, tries do
     game.RobloxReplicatedStorage.SetPlayerBlockList:FireServer(maintable)
end
end

bomb(250, 2) --// change values if client crashes.
end
wait(0.0) -- intervalo de 1 segundo entre cada repetição
end
end
local Section = Tab:AddSection({
	Name = "Doors"
})
Tab:AddButton({
Name = "DESTROY DOORS",
Callback = function()
local UserInputService = game:GetService("UserInputService")
local Mouse = game:GetService("Players").LocalPlayer:GetMouse()
local Folder = Instance.new("Folder", game:GetService("Workspace"))
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1
local Updated = Mouse.Hit + Vector3.new(0, 5, 0)
local NetworkAccess = coroutine.create(function()
    settings().Physics.AllowSleep = false
    while game:GetService("RunService").RenderStepped:Wait() do
        for _, Players in next, game:GetService("Players"):GetPlayers() do
            if Players ~= game:GetService("Players").LocalPlayer then
                Players.MaximumSimulationRadius = 0 
                sethiddenproperty(Players, "SimulationRadius", 0) 
            end 
        end
        game:GetService("Players").LocalPlayer.MaximumSimulationRadius = math.pow(math.huge,math.huge)
        setsimulationradius(math.huge) 
    end 
end) 
coroutine.resume(NetworkAccess)
local function ForcePart(v)
    if v:IsA("Part") and v.Anchored == false and v.Parent:FindFirstChild("Humanoid") == nil and v.Parent:FindFirstChild("Head") == nil and v.Name ~= "Handle" then
        Mouse.TargetFilter = v
        for _, x in next, v:GetChildren() do
            if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                x:Destroy()
            end
        end
        if v:FindFirstChild("Attachment") then
            v:FindFirstChild("Attachment"):Destroy()
        end
        if v:FindFirstChild("AlignPosition") then
            v:FindFirstChild("AlignPosition"):Destroy()
        end
        if v:FindFirstChild("Torque") then
            v:FindFirstChild("Torque"):Destroy()
        end
        v.CanCollide = false
        local Torque = Instance.new("Torque", v)
        Torque.Torque = Vector3.new(999999, 999999, 999999)
        local AlignPosition = Instance.new("AlignPosition", v)
        local Attachment2 = Instance.new("Attachment", v)
        Torque.Attachment0 = Attachment2
        AlignPosition.MaxForce = 99999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999
        AlignPosition.MaxVelocity = math.huge
        AlignPosition.Responsiveness = 200
        AlignPosition.Attachment0 = Attachment2 
        AlignPosition.Attachment1 = Attachment1
    end
end
for _, v in next, game:GetService("Workspace"):GetDescendants() do
    ForcePart(v)
end
game:GetService("Workspace").DescendantAdded:Connect(function(v)
    ForcePart(v)
end)
UserInputService.InputBegan:Connect(function(Key, Chat)
    if Key.KeyCode == Enum.KeyCode.E and not Chat then
       Updated = Mouse.Hit + Vector3.new(0, 5, 0)
    end
end)
spawn(function()
    while game:GetService("RunService").RenderStepped:Wait() do
        Attachment1.WorldCFrame = Updated
    end
end)
end
})
Tab:AddParagraph("How to use","You need to have permission from the person's house and get close to the house.The function will not work if the house is locked, but if you have permission you can unlock it, this function works like the Ice Hub's fling Doors")
Tab:AddParagraph("Como usar","Você precisa ter permissão da casa da pessoa e chegar perto da casa. A função não funcionará se a casa estiver trancada, mas se você tiver permissão, poderá desbloqueá-la.esta função funciona como as portas de lançamento do Ice Hub")
local Section = Tab:AddSection({
	Name = "Get Permission Houses"
})
Tab:AddButton({
	Name = "House 1",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 1
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 2",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 2
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 3",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 3
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 4",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 4
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 5",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 5
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 6",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 6
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 7",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 7
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 8",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 8
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 9",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 9
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 10",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 10
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 11",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 11
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 12",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 12
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 13",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 13
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 14",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 14
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 15",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 15
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 16",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 16
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 17",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 17
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 18",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 18
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 19",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 19
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 20",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 20
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 21",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 21
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 22",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 22
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 23",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 23
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 24",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 24
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})


Tab:AddButton({
    Name = "Tira ban De todas as casa",
    Callback = function()
                      if selectedHouseNumber then
            -- Defina o nome do lote
            local lotNumber = "001_Lots"

            -- Tente acessar o lote e percorrer todas as casas
            local lot = workspace:FindFirstChild(lotNumber)

            if lot then
                -- Percorre todas as casas dentro do lote
                for _, house in pairs(lot:GetChildren()) do
                    if house:FindFirstChild("HousePickedByPlayer") then
                        -- Tente encontrar e remover o BannedBlock com base na escolha
                        local bannedBlockName = "BannedBlock" .. selectedHouseNumber -- Nome do bloco banido
                        local bannedBlock = house.HousePickedByPlayer.HouseModel:FindFirstChild(bannedBlockName)

                        if bannedBlock then
                            bannedBlock:Destroy() -- Deletar a parte
                            print(bannedBlockName .. " deletado com sucesso em " .. house.Name)
                        else
                            print(bannedBlockName .. " nÃ£o encontrado em " .. house.Name)
                        end
                    end
                end
            else
                print("Lote " .. lotNumber .. " nÃ£o encontrado.")
            end
        else
            print("Nenhuma casa selecionada!") -- Aviso se nenhuma casa foi escolhida
        end
    end
})


local Tab = Window:MakeTab({
Name = "Car",
Icon = "rbxassetid://18319058691",
PremiumOnly = false
})
local Section = Tab:AddSection({
    Name = "Velocity"
})

-- Variables
local CarSpeed = 200

-- Textbox for Car Speed
Tab:AddTextbox({
Name = "Car Speed",
Default = "",
TextDisappear = true,
Callback = function(value)
CarSpeed = tonumber(value)
end
})

-- Button to Update Car Speed
Tab:AddButton({
Name = "Update Speed",
Callback = function()
local args = {
[1] = "PlayerGiveSpeedLower",
[2] = CarSpeed
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Loop"
})

local toggleActive = false
local function loopDuke()
while toggleActive do
local args = {
    [1] = "Duke"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Duke",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopDuke()
end
end
})

local toggleActive = false
local function loopFlip()
while toggleActive do
local args = {
    [1] = "Flip"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Flip",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFlip()
end
end
})

local toggleActive = false
local function loopSmoke()
while toggleActive do
local args = {
    [1] = "Smoke"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Smoke",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopSmoke()
end
end
})

local toggleActive = false
local function loopFire()
while toggleActive do
local args = {
    [1] = "Fire"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Fire",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFire()
end
end
})
local Section = Tab:AddSection({
    Name = "Delete Vehicle"
})
Tab:AddButton({
	Name = "Delete Vehicle",
	Callback = function()
      	local args = {
    [1] = "DeleteAllVehicles"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))	
  	end    
})
local Section = Tab:AddSection({
    Name = "Horse"
})
Tab:AddButton({
	Name = "Spawn Horse",
	Callback = function()
      	local args = {
    [1] = "PickingCar",
    [2] = "Horse"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
  	end    
})

local toggleActive = false
local function loopFire()
while toggleActive do
local args = {
    [1] = "BrownHorseFree"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Hors1eRemot1e"):FireServer(unpack(args))
wait(1.0)
local args = {
    [1] = "BlackHorseFree"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Hors1eRemot1e"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop color horse",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFire()
end
end
})
local Section = Tab:AddSection({
    Name = "Jumpscare Car - GamePass"
})
Tab:AddButton({
	Name = "Screaming Woman",
	Callback = function()
      	 local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-24.741954803466797, 3.0249993801116943, -66.39078521728516)
wait(0.1)
local args = {
    [1] = "PickingCar",
    [2] = "SchoolBus"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
wait(1)
 local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-35.15000534057617, 5.7094035148620605, -74.16535949707031)
wait(0.1)
local args = {
    [1] = "PickingCarMusicText",
    [2] = "892233254"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Truck"
})
Tab:AddButton({
	Name = "Spawn Truck",
	Callback = function()
      	local args = {
    [1] = "PickingCar",
    [2] = "Semi"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
  	end    
})


local toggled = false

local function FireEvent()
    while toggled do
        local args = {
            [1] = "PickingCar",
            [2] = "Semi"
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Ca1r"):FireServer(unpack(args))
        wait(0.1) -- Tempo entre cada execução, ajuste conforme necessário
    end
end


Tab:AddToggle({
    Name = "Spam Truck",
    Default = false,
    Callback = function(value)
        toggled = value
        if toggled then
            FireEvent()
        end
    end
})


local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local RE = ReplicatedStorage:FindFirstChild("RE")

local Target = nil
local PlayerList = {}

-- Função para obter a lista de jogadores
local function GetPlayerNames()
    local names = {}
    for _, player in ipairs(Players:GetPlayers()) do
        table.insert(names, player.Name)
    end
    return names
end

-- Criar a guia principal
local Tab = Window:MakeTab({
    Name = "Avatar",
    Icon = "rbxassetid://18319058691",
    PremiumOnly = false
})

-- Criar o dropdown (lista de jogadores)
local PlayerDropdown = Tab:AddDropdown({
    Name = "Selecionar Jogador",
    Options = GetPlayerNames(),
    Callback = function(selected)
        Target = selected
    end
})

-- Atualizar dropdown quando jogadores entram ou saem
local function UpdateDropdown()
    PlayerDropdown:Refresh(GetPlayerNames(), true)
end

Players.PlayerAdded:Connect(UpdateDropdown)
Players.PlayerRemoving:Connect(UpdateDropdown)

-- Botão para copiar o avatar do jogador selecionado
Tab:AddButton({
    Name = "Copiar Avatar",
    Callback = function()
        if not Target then
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Selecione um jogador primeiro!",
                Image = "rbxassetid://4483345998",
                Time = 3
            })
            return
        end

        local Player = Players:FindFirstChild(Target)
        if not Player or not Player.Character then
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Jogador não encontrado!",
                Image = "rbxassetid://4483345998",
                Time = 3
            })
            return
        end

        local Character = Player.Character
        local Humanoid = Character:FindFirstChildOfClass("Humanoid")
        if not Humanoid then return end

        local PDesc = Humanoid:GetAppliedDescription()
        local LPDesc = game.Players.LocalPlayer.Character.Humanoid:GetAppliedDescription()

        -- Remover acessórios do jogador local
        for _, v in ipairs(LPDesc:GetAccessories(true)) do
            if v.AssetId then
                task.wait(0.3)
                RE:FindFirstChild("1Updat1eAvata1r"):FireServer("wear", tonumber(v.AssetId))
            end
        end

        -- Copiar roupas
        task.wait(0.1)
        RE:FindFirstChild("1Updat1eAvata1r"):FireServer("wear", tonumber(PDesc.Shirt))
        task.wait(0.5)
        RE:FindFirstChild("1Updat1eAvata1r"):FireServer("wear", tonumber(PDesc.Pants))

        -- Copiar partes do corpo
        task.wait(0.5)
        RE:FindFirstChild("1Avata1rOrigina1l"):FireServer("CharacterChange", {
            PDesc.Torso, PDesc.RightArm, PDesc.LeftArm,
            PDesc.RightLeg, PDesc.LeftLeg, PDesc.Head
        }, "By Davi999 (Melhor Sub Dono)")

        -- Copiar rosto
        task.wait(0.5)
        RE:FindFirstChild("1Updat1eAvata1r"):FireServer("wear", tonumber(PDesc.Face))

        -- Copiar acessórios
        for _, v in ipairs(PDesc:GetAccessories(true)) do
            if v.AssetId then
                task.wait(0.3)
                RE:FindFirstChild("1Updat1eAvata1r"):FireServer("wear", tonumber(v.AssetId))
            end
        end

        -- Copiar cor da pele
        local SkinColor = Character:FindFirstChild("Body Colors")
        if SkinColor then
            task.wait(0.5)
            RE:FindFirstChild("1Updat1eAvata1r"):FireServer("skintone", tostring(SkinColor.HeadColor))
        end

        -- Copiar animação
        task.wait(0.5)
        RE:FindFirstChild("1Updat1eAvata1r"):FireServer("wearWalkStyle", tonumber(PDesc.IdleAnimation))

        -- Notificação de sucesso
        OrionLib:MakeNotification({
            Name = "Sucesso",
            Content = "Avatar copiado com sucesso!",
            Image = "rbxassetid://4483345998",
            Time = 3
        })
    end
})


local Section = Tab:AddSection({
	Name = "Avatares"
})


Tab:AddButton({
	Name = "Big avatar",
	Callback = function()
      		local args = {
    "CharacterChange",
    {
        130887057643589,
        88668275797583,
        79115019295211,
        130887057643589,
        80245769527311,
        106800882836405,
    },
    ""
}
game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Avata1rOrigina1l"):FireServer(unpack(args))
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Babi davimet",
	Callback = function()
      	local args = {
    "CharacterChange",
    {
        14731377941,
        14731377894,
        14731377875,
        14731384498,
        14731377938,
        0
    },
    ""
}
game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Avata1rOrigina1l"):FireServer(unpack(args))
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Mini Avatar",
	Callback = function()
      		local args = {
    "CharacterChange",
    {
        127031457048501,
        133265737142401,
        75333435611117,
        125434879410481,
        116071262888556,
        0
    },
    ""
}
game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Avata1rOrigina1l"):FireServer(unpack(args))
print("button pressed")
  	end    
})


local Section = Tab:AddSection({
	Name = "Names"
})


-- Variables
local name1 = ""
local name2 = ""
local name3 = ""
local repeatNames = false

-- Textbox for Name 1
Tab:AddTextbox({
Name = "Name 1",
Default = "",
TextDisappear = true,
Callback = function(value)
name1 = value
end
})

-- Textbox for Name 2
Tab:AddTextbox({
Name = "Name 2",
Default = "",
TextDisappear = true,
Callback = function(value)
name2 = value
end
})

-- Textbox for Name 3
Tab:AddTextbox({
Name = "Name 3",
Default = "",
TextDisappear = true,
Callback = function(value)
name3 = value
end
})

-- Toggle for Repeating Names
Tab:AddToggle({
Name = "Repeat Names",
Default = false,
Callback = function(value)
repeatNames = value
while repeatNames do
local args1 = {
[1] = "RolePlayName",
[2] = name1
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1RPNam1eTex1t"):FireServer(unpack(args1))

local args2 = {
[1] = "RolePlayName",
[2] = name2
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1RPNam1eTex1t"):FireServer(unpack(args2))

wait(1) -- Adjust the wait time as needed


local args3 = {
[1] = "RolePlayName",
[2] = name3
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1RPNam1eTex1t"):FireServer(unpack(args3))
end
end
})
local Section = Tab:AddSection({
    Name = "Limiteds"
})
local valks = {
["Valk timeless"] = 17517206952,
["Valk esmerald"] = 2830437685,
["Valk Shine Time"] = 1180433861
}

Tab:AddDropdown({
Name = "Select Valks",
Default = "",
Options = {"Valk timeless", "Valk esmerald", "Valk Shine Time"},
Callback = function(selected)
local args = {
[1] = "wear",
[2] = valks[selected]
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})

local dominus = {
["Dominus Frigidus"] = 48545806,
["Dominus Empyreus"] = 64444871,
["Dominus Astra"] = 162067148,
["Dominus Infernus"] = 31101391
}

Tab:AddDropdown({
Name = "Select Dominus",
Default = "",
Options = {"Dominus Frigidus", "Dominus Empyreus", "Dominus Astra", "Dominus Infernus"},
Callback = function(selected)
local args = {
[1] = "wear",
[2] = dominus[selected]
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Characters"
})
local characters = {
["Chef Tordet"] = {
[1] = 3657481497,
[2] = 3657478273,
[3] = 3657474549,
[4] = 3657479706,
[5] = 3745126840,
[6] = 1
},
["Chicken"] = {
[1] = 128157408,
[2] = 128157262,
[3] = 128157213,
[4] = 128157361,
[5] = 128157317,
[6] = 1
},
["Gang potato"] = {
[1] = 5392155773,
[2] = 5392150804,
[3] = 5392146467,
[4] = 5392152751,
[5] = 5392148570,
[6] = 1
},
["The overser"] = {
[1] = 81725326,
[2] = 81725366,
[3] = 81725392,
[4] = 1,
[5] = 1,
[6] = 1
},
["All korblox"] = {
[1] = 139607770,
[2] = 139607625,
[3] = 139607570,
[4] = 139607718,
[5] = 139607673,
[6] = 1
}
}

Tab:AddDropdown({
Name = "Characters",
Default = "",
Options = {"Chef Tordet", "Chicken", "Gang potato", "The overser", "All korblox"},
Callback = function(selected)
local args = {
[1] = "CharacterChange",
[2] = characters[selected],
[3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
end
})


local Section = Tab:AddSection({
    Name = "Bold animatiom"
})
Tab:AddButton({
	Name = "Idle",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744209868
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Run",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744214662
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Walk",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744219182
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Jump",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744212581
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Fall",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744207822
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Climb",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744204409
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "swim", 
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744217055
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Head"
})
Tab:AddButton({
	Name = "Headless",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 1,
        [6] = 134082579
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Cheek",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 1,
        [6] = 746767604
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Horror Skin"
})
Tab:AddButton({
	Name = "Michael Myers",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 15133320948
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Mario Victim 1",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 14732524763
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Scary",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 15036977826
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Scary dog",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 14761007249
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Jeff The Killer",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 14502327402
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Korblox Legs "
})
Tab:AddButton({
	Name = "Right",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 139607718,
        [5] = 1,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Left ",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 139607673,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Ice legs "
})
Tab:AddButton({
	Name = "Right",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 139572888,
        [5] = 1,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Left ",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 139572789,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Adidas Sport animation"
})
Tab:AddButton({
	Name = "Idle",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538150608
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Run",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538133604
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Walk",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538146480
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "jump",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538153691
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Fall",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538153691
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Climb",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538170170
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Zombie "
})
Tab:AddButton({
	Name = "zombie leg",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 37754710,
        [5] = 1,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})


local Tab = Window:MakeTab({
	Name = "Jogador",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Anti functions"
})


Tab:AddToggle({
    Name = "Ant Sit",
    Default = false,
    Callback = function(Value)
        local player = game.Players.LocalPlayer
        local humanoid = player.Character and player.Character.Humanoid
        
        if humanoid then
            if Value then
                -- Quando o toggle está ativado (Value é true), o humanoide não pode sentar em assentos
                humanoid:SetStateEnabled("Seated", false)
            else
                -- Quando o toggle está desativado (Value é false), o humanoide pode sentar em assentos normalmente
                humanoid:SetStateEnabled("Seated", true)
            end
        else
            print("Erro: Personagem não encontrado.")
        end
    end    
})


-- Variável de controle
local voidImmunityEnabled = false

-- Função para ativar/desativar a imunidade ao void
local function setVoidImmunity(state)
    if state then
        workspace.FallenPartsDestroyHeight = 0/0
    else
        workspace.FallenPartsDestroyHeight = -500 -- Valor padrão do Roblox
    end
end

-- Toggle para o Orion Lib
Tab:AddToggle({
    Name = "Anti Void",
    Default = false,
    Callback = function(State)
        voidImmunityEnabled = State
        setVoidImmunity(voidImmunityEnabled)
    end
})


-- Função para deletar o veículo específico de um jogador
local function deleteVehicleFromPlayer(player)
    local vehiclesFolder = workspace:FindFirstChild("Vehicles")
    if vehiclesFolder then
        local vehicleName = player.Name .. "Car"
        local vehicle = vehiclesFolder:FindFirstChild(vehicleName)
        if vehicle then
            vehicle:Destroy()
            print("Veículo deletado para: " .. player.Name)
        else
            warn("Veículo não encontrado para: " .. player.Name)
        end
    end
end

-- Função para deletar o veículo de todos os jogadores
local function deleteVehicleFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deleteVehicleFromPlayer(player)
    end
end

-- Função para deletar as parts associadas ao jogador
local function deletePartsFromPlayer(player)
    local admFolder = workspace:FindFirstChild(player.Name)
    if admFolder then
        -- Lista das parts a serem deletadas
        local partsToDelete = {"Couch", "Stretcher", "Wagon", "Stroller", "ShoppingCart", "LawnMower"}
        
        for _, partName in pairs(partsToDelete) do
            local part = admFolder:FindFirstChild(partName)
            if part then
                part:Destroy()
                print(partName .. " deletada para: " .. player.Name)
            else
                warn(partName .. " não encontrada para: " .. player.Name)
            end
        end
    end
end

-- Função para deletar as parts de todos os jogadores
local function deletePartsFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deletePartsFromPlayer(player)
    end
end

-- Variável de controle do loop
local isLooping = false

-- Função para controlar o loop
local function startLoop()
    while isLooping do
        deleteVehicleFromAllPlayers()       -- Deletar veículos de todos os jogadores
        deletePartsFromAllPlayers()         -- Deletar as parts de todos os jogadores
        wait(1) -- Tempo entre cada execução do loop (5 segundos neste exemplo)
    end
end

Tab:AddToggle({
    Name = "Anti Fling",
    Default = false,
    Callback = function(state)
        isLooping = state
        if isLooping then
            startLoop()
        end
    end    
})


local Section = Tab:AddSection({
	Name = "Notificar Saída e Entrada dos Jogadores"
})

local notifyPlayers = false

Tab:AddToggle({
    Name = "Ativar Notificações de Saída e Entrada dos Jogadores",
    Default = false,
    Callback = function(Value)
        notifyPlayers = Value
    end
})

game.Players.PlayerAdded:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) entrou no servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Entrada de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)

game.Players.PlayerRemoving:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) saiu do servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Saída de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)


Tab:AddButton({
	Name = "Freeze all [Visual]",
	Callback = function()
      	local Players = game:GetService("Players")
local speaker = game.Players.LocalPlayer -- Altere isso conforme necessário

for _, player in pairs(Players:GetPlayers()) do
    if player ~= speaker and player.Character then -- Verifica se o player NÃO é o speaker
        for _, part in ipairs(player.Character:GetDescendants()) do
            if part:IsA("BasePart") and not part.Anchored then
                part.Anchored = true
            end
        end
    end
end


-- Chat message (Updated for new chat system)
local TextChatService = game:GetService("TextChatService")

local function SendChatMessage(message)
    -- Verifica se o chat moderno (TextChatService) está disponível
    if TextChatService.ChatVersion == Enum.ChatVersion.TextChatService then
        local textChannel = TextChatService.TextChannels.RBXGeneral
        -- Envia a mensagem para o canal geral
        textChannel:SendAsync(message)
    else
        -- Caso contrário, usa o sistema de chat antigo
        game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(message, "All")
    end
end

-- Envia a mensagem no chat
SendChatMessage(";Freeze All")
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Unfreeze All[Beta]",
	Callback = function()
      local Players = game:GetService("Players")
local speaker = game.Players.LocalPlayer -- Altere isso conforme necessário

for _, player in pairs(Players:GetPlayers()) do
    if player ~= speaker and player.Character then -- Evita descongelar o próprio jogador
        for _, part in ipairs(player.Character:GetDescendants()) do
            if part:IsA("BasePart") and part.Anchored then
                part.Anchored = false -- Remove o freeze
            end
        end
    end
end


-- Chat message (Updated for new chat system)
local TextChatService = game:GetService("TextChatService")

local function SendChatMessage(message)
    -- Verifica se o chat moderno (TextChatService) está disponível
    if TextChatService.ChatVersion == Enum.ChatVersion.TextChatService then
        local textChannel = TextChatService.TextChannels.RBXGeneral
        -- Envia a mensagem para o canal geral
        textChannel:SendAsync(message)
    else
        -- Caso contrário, usa o sistema de chat antigo
        game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(message, "All")
    end
end

-- Envia a mensagem no chat
SendChatMessage(";UnFreeze All")
		print("button pressed")
  	end    
})


local toxicToggle = false -- Controla se o detector está ativado

-- Lista de palavras tóxicas
local toxicNames = {"itz", "poderoso", "poderosa", "PH", "mandrake", "its", "ltz", "lts", "blessed"}
local toxicWords = {
    "estrupar", "vagabundo", "procuro dono", "dono", "nam", "namorar", "vou te comer", 
    "20come", "cu", "pau", "pinto", "favela", "facção", "fac", "foda", "vai se fuder", 
    "fuder", "porra", "c.u", "dona", "nam", "namo","jeca", "zé buceta", "otário demais", "otária sem graça", "cara de pastel", "pateta", "mané burro",
    "retardado", "abestado", "moleque fedido", "fedorento", "rato de esgoto", "cabeça de bagre",
    "bichona", "maria vai com as outras", "mosca de padaria", "capivara humana", "tatu bola", 
    "marmota", "pangaré", "manézão", "babaca de marca maior", "fiasco ambulante", "lesado de tudo","pqp", "vai se f*", "vai tomar no **", "fdp demais", "seu trouxa de merda", "vai se ferrar",
    "saco de merda", "jogador de bosta", "bosta ambulante", "merdinha sem vida", "jogador lixo","burro", "idiota", "lixo", "fracassado", "otário", "trouxa", "inútil", "imbecil", "estúpido", "noob",
    "anta", "ridículo", "palhaço", "boboca", "banana", "mongol", "tapado", "jumento", "animal", "patético",
    "babaca", "verme", "ridícula", "cabeça oca", "sem talento", "burra", "chato", "falido", "lesado",
    "chucro", "sem futuro", "fracasso ambulante", "fedido", "irritante", "preguiçoso", "ignorante",
    "miserável", "nojento", "maldito", "praga", "asqueroso", "podre", "escroto", "peste", "ridiculamente ruim",
    "embuste", "fdp", "merda", "bosta", "seu bosta", "desgraçado", "vagabundo", "corno", "mula", "jegue",
    "zé ruela", "pé rapado", "merdinha", "bobalhão", "moleque", "otária", "tonto", "palhaçada", "trouxa",
    "zé mané", "abobado", "besta", "cretino", "babacão", "mentecapto", "manézão", "coitado", "incompetente","haha","arrombado",
}

-- Função para verificar palavras tóxicas em strings
local function isToxicMessage(message)
    for _, word in ipairs(toxicWords) do
        if string.match(message:lower(), "%f[%a]" .. word .. "%f[%A]") then
            return true
        end
    end
    return false
end

-- Função para verificar nomes tóxicos
local function isToxicName(name)
    for _, toxicName in ipairs(toxicNames) do
        if string.find(name:lower(), toxicName) then
            return true
        end
    end
    return false
end

-- Função para verificar nomes de jogadores em tempo real
local function checkPlayerName(player)
    local displayName = player.DisplayName
    local userName = player.Name

    -- Certifique-se de enviar apenas uma notificação por jogador
    if isToxicName(displayName) or isToxicName(userName) then
        OrionLib:MakeNotification({
            Name = "Nome Tóxico Detectado!",
            Content = "Jogador: " .. userName .. " (DisplayName: " .. displayName .. ")",
            Image = "rbxassetid://4483345998",
            Time = 5
        })
    end
end

-- Função para monitorar o chat de um jogador específico
local function monitorPlayerChat(player)
    player.Chatted:Connect(function(message)
        if isToxicMessage(message) then
            OrionLib:MakeNotification({
                Name = "Mensagem Tóxica Detectada!",
                Content = "Jogador: " .. player.Name .. "\nMensagem: " .. message,
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end)
end

-- Função para verificar RPName e RPBio iniciais e monitorar alterações
local function monitorPlayerProperties(player)
    local success, playerBag = pcall(function()
        return player:WaitForChild("PlayersBag", 5) -- Espera por PlayersBag
    end)
    
    if success and playerBag then
        local rpName = playerBag:FindFirstChild("RPName")
        local rpBio = playerBag:FindFirstChild("RPBio")

        -- Verificar RPName inicial e monitorar alterações
        if rpName and rpName:IsA("StringValue") then
            if isToxicMessage(rpName.Value) then
                OrionLib:MakeNotification({
                    Name = "Conteúdo Tóxico Detectado!",
                    Content = "Jogador: " .. player.Name .. " (RPName: " .. rpName.Value .. ")",
                    Image = "rbxassetid://4483345998",
                    Time = 5
                })
            end
            rpName:GetPropertyChangedSignal("Value"):Connect(function()
                if isToxicMessage(rpName.Value) then
                    OrionLib:MakeNotification({
                        Name = "Conteúdo Tóxico Detectado!",
                        Content = "Jogador: " .. player.Name .. " (RPName: " .. rpName.Value .. ")",
                        Image = "rbxassetid://4483345998",
                        Time = 5
                    })
                end
            end)
        end

        -- Verificar RPBio inicial e monitorar alterações
        if rpBio and rpBio:IsA("StringValue") then
            if isToxicMessage(rpBio.Value) then
                OrionLib:MakeNotification({
                    Name = "Conteúdo Tóxico Detectado!",
                    Content = "Jogador: " .. player.Name .. " (RPBio: " .. rpBio.Value .. ")",
                    Image = "rbxassetid://4483345998",
                    Time = 5
                })
            end
            rpBio:GetPropertyChangedSignal("Value"):Connect(function()
                if isToxicMessage(rpBio.Value) then
                    OrionLib:MakeNotification({
                        Name = "Conteúdo Tóxico Detectado!",
                        Content = "Jogador: " .. player.Name .. " (RPBio: " .. rpBio.Value .. ")",
                        Image = "rbxassetid://4483345998",
                        Time = 5
                    })
                end
            end)
        end
    end
end

-- Função para monitorar todos os jogadores
local function monitorPlayers()
    local Players = game:GetService("Players")

    -- Verificar nomes e monitorar jogadores já presentes
    for _, player in ipairs(Players:GetPlayers()) do
        checkPlayerName(player)
        monitorPlayerChat(player)
        monitorPlayerProperties(player)
    end

    -- Verificar nomes e monitorar novos jogadores
    Players.PlayerAdded:Connect(function(player)
        checkPlayerName(player)
        monitorPlayerChat(player)
        monitorPlayerProperties(player)
    end)
end


Tab:AddToggle({
    Name = "Ativar Detector",
    Default = false,
    Callback = function(value)
        toxicToggle = value
        if toxicToggle then
            monitorPlayers()
        end
    end
})


Tab:AddTextbox({
	Name = "Velocidade",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		local speed = tonumber(Value)
		if speed then
			local player = game.Players.LocalPlayer
			if player and player.Character and player.Character:FindFirstChild("Humanoid") then
				player.Character.Humanoid.WalkSpeed = speed
			else
				print("Personagem não encontrado ou sem componente Humanoid.")
			end
		else
			print("Por favor, insira um número válido para a velocidade.")
		end
	end	  
})


Tab:AddTextbox({
	Name = "Gravidade",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		local gravity = tonumber(Value)
		if gravity then
			game.Workspace.Gravity = gravity
		else
			print("Por favor, insira um número válido para a gravidade.")
		end
	end	  
})

Tab:AddTextbox({
	Name = "Poder de Salto",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		local jumpPower = tonumber(Value)
		if jumpPower then
			local player = game.Players.LocalPlayer
			if player and player.Character and player.Character:FindFirstChild("Humanoid") then
				player.Character.Humanoid.JumpPower = jumpPower
			else
				print("Personagem ou Humanoid não encontrado.")
			end
		else
			print("Por favor, insira um número válido para o poder de salto.")
		end
	end	  
})

Tab:AddButton({

    Name = "Redefinir Todos Para o Padrão",

    Callback = function()

        local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

-- Redefinindo a WalkSpeed para o padrão (16)
character.Humanoid.WalkSpeed = 16

-- Redefinindo o JumpPower para o padrão (50)
character.Humanoid.JumpPower = 50

-- Redefinindo a gravidade para o padrão (196.2)
workspace.Gravity = 196.2


    end

})

local Section = Tab:AddSection({

	Name = "R6"

})

Tab:AddButton({

    Name = "R6 Avatar",

    Callback = function()

        local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 17900005857,
        [2] = 17900005872,
        [3] = 17900006112,
        [4] = 17900006056,
        [5] = 17900006299,
        [6] = 0
    },
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))

loadstring(game:HttpGet("https://scriptblox.com/raw/Universal-Script-from-R15-to-R6-9639"))()

    end

})

local Section = Tab:AddSection({

	Name = "Teleportar Para Jogador"

})

Tab:AddTextbox({
    Name = "Teleportar Para Jogador (Insira o Nome do Jogador)",
    Default = "",
    TextDisappear = true,
    Callback = function(playerName)
        teleportToPlayer(playerName)
    end
})

Tab:AddParagraph("Hey!","Não Precisa colocar o nome completo do jogador, apenas colocando as letras iniciais do nome dele o teleporte ja funciona, coloque o Nome Original do Jogador. :D")

local Section = Tab:AddSection({

	Name = "Noclip"

})

Tab:AddToggle({
    Name = "Noclip",
    Default = false,  -- Noclip não ativado por padrão
    Callback = ToggleNoclip
})

local Section = Tab:AddSection({

	Name = "Espectar Jogador"

})

-- Função para retornar a visão normal da câmera
local function resetCameraView()
    -- Define o CameraSubject de volta para o jogador local
    game:GetService("Workspace").CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character
end

Tab:AddTextbox({
    Name = "Espectar Jogador (Insira o Nome do Jogador)",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        print("Valor digitado:", Value)  -- Debug: Verifica se o valor está sendo capturado corretamente
        
        -- Encontra o jogador com o nome fornecido
        local player = nil
        for _, ply in pairs(game.Players:GetPlayers()) do
            if string.lower(string.sub(ply.Name, 1, #Value)) == string.lower(Value) then
                player = ply
                break
            end
        end
        
        if player then
            print("Jogador encontrado:", player.Name)  -- Debug: Verifica se o jogador foi encontrado
            
            -- Define o jogador como o CameraSubject para mudar a visão
            game:GetService("Workspace").CurrentCamera.CameraSubject = player.Character
        else
            print("Jogador não encontrado!")
        end
    end
})

Tab:AddButton({
    Name = "Parar de Espectar Jogador",
    Callback = function()
        resetCameraView()
    end
})

Tab:AddParagraph("Hey!","Não Precisa colocar o nome completo do jogador, apenas colocando as letras iniciais do nome dele o Espectar Jogador ja funciona, coloque o Nome Original do Jogador. :D")


local Tab = Window:MakeTab({
	Name = "Chat",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


local Section = Tab:AddSection({

	Name = "Anti Tags (Estilo de Letras Inventado Por Pguel_01)"

})

-- Mapeamento dos caracteres para a conversão (incluindo maiúsculas)
local characterMap = {
    a = "â", b = "ɓ", c = "ĉ", d = "ď", e = "ê", f = "f", g = "ĝ", h = "ĥ",
    i = "î", j = "ĵ", k = "ƙ", l = "ľ", m = "m", n = "ň", o = "ô", p = "p",
    q = "q", r = "ř", s = "ŝ", t = "ť", u = "û", v = "v", w = "w", x = "x",
    y = "ŷ", z = "ž",
    A = "Â", B = "Ɓ", C = "Ĉ", D = "Ď", E = "Ê", F = "F", G = "Ĝ", H = "Ĥ",
    I = "Î", J = "Ĵ", K = "Ƙ", L = "Ľ", M = "M", N = "Ň", O = "Ô", P = "P",
    Q = "Q", R = "Ř", S = "Ŝ", T = "Ť", U = "Û", V = "V", W = "W", X = "X",
    Y = "Ŷ", Z = "Ž"
}

-- Função para converter a mensagem
local function convertMessage(message)
    local styledMessage = ""
    for i = 1, #message do
        local char = message:sub(i, i)
        styledMessage = styledMessage .. (characterMap[char] or char)
    end
    return styledMessage
end

Tab:AddTextbox({
    Name = "Anti Tags (Digite a Mensagem)",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        local styledMessage = convertMessage(Value)
        local TextChatService = game:GetService("TextChatService")
        TextChatService.TextChannels.RBXGeneral:SendAsync(styledMessage)
    end
})

local Section = Tab:AddSection({

	Name = "Spam"

})

-- Variáveis para controle do envio automático
local autoSend = false
local messageToSend = ""

-- Função para iniciar o envio automático
local function startAutoSend()
    while autoSend do
        local TextChatService = game:GetService("TextChatService")
        TextChatService.TextChannels.RBXGeneral:SendAsync(messageToSend) -- Envia a mensagem normal
        wait(1) -- Aguarda 1 segundo
    end
end

Tab:AddTextbox({
    Name = "Spam (Digite a Mensagem)",
    Default = "",
    TextDisappear = false,
    Callback = function(Value)
        messageToSend = Value
    end
})

Tab:AddToggle({
    Name = "Ativar Spam",
    Default = false,
    Callback = function(State)
        autoSend = State
        if State then
            startAutoSend()
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Funções Vip",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


Tab:AddButton({
    Name = "Selecionar Motor de Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarEngineBlower"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Escopo de Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarRaceScoopeVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Assas de Carro VIP 1",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarFullColorVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Assas de Carro VIP 2",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarWingHalfColorVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))
        
    end
})

Tab:AddButton({
    Name = "Selecionar Luzes de Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarTruckLightsOrange"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Mini Gun VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "MilitaryMiniGunVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Mini Gun Para Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "MilitaryCarMiniGunVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Balão de Pum VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "ToolsFart"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))
    end
})


local Tab = Window:MakeTab({
	Name = "Join Id",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


-- Variável para armazenar o ID do servidor
local ServerID = ""

-- Adicionar um botão para copiar o ID do servidor atual
Tab:AddButton({
    Name = "Copiar ID do Servidor",
    Callback = function()
        setclipboard(game.JobId) -- Copia o ID do servidor para a área de transferência
        OrionLib:MakeNotification({
            Name = "Copiado!",
            Content = "O ID do servidor foi copiado!",
            Image = "rbxassetid://4483345998",
            Time = 3
        })
    end
})

-- Adicionar um input para inserir o ID do servidor desejado
Tab:AddTextbox({
    Name = "ID do Servidor",
    Default = "",
    TextDisappear = false,
    Callback = function(Value)
        ServerID = Value
    end
})

-- Adicionar um botão para entrar no servidor desejado
Tab:AddButton({
    Name = "Entrar no Servidor",
    Callback = function()
        local TeleportService = game:GetService("TeleportService")
        local PlaceID = game.PlaceId -- Obtém o ID do jogo atual

        if ServerID ~= "" then
            TeleportService:TeleportToPlaceInstance(PlaceID, ServerID, game.Players.LocalPlayer)
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Insira um ID válido!",
                Image = "rbxassetid://4483345998",
                Time = 3
            })
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Scripts",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "Remote Spy",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-remote-spy-mobile-reupload-24466"))()
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Dex Explorer",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Dex-Explorer-No-Key-29915"))()
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Black Role gui By noly",
	Callback = function()
local Gui = Instance.new("ScreenGui")
local Main = Instance.new("Frame")
local Box = Instance.new("TextBox")
local UITextSizeConstraint = Instance.new("UITextSizeConstraint")
local Label = Instance.new("TextLabel")
local UITextSizeConstraint_2 = Instance.new("UITextSizeConstraint")
local Button = Instance.new("TextButton")
local UITextSizeConstraint_3 = Instance.new("UITextSizeConstraint")

--Propriedades:

Gui.Name = "Gui"
Gui.Parent = gethui()
Gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Main.Name = "Main"
Main.Parent = Gui
Main.BackgroundColor3 = Color3.fromRGB(75, 75, 75)
Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
Main.BorderSizePixel = 0
Main.Position = UDim2.new(0.335954279, 0, 0.542361975, 0)
Main.Size = UDim2.new(0.240350261, 0, 0.166880623, 0)
Main.Active = true
Main.Draggable = true

Box.Name = "Box"
Box.Parent = Main
Box.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Box.BorderColor3 = Color3.fromRGB(0, 0, 0)
Box.BorderSizePixel = 0
Box.Position = UDim2.new(0.0980926454, 0, 0.218712583, 0)
Box.Size = UDim2.new(0.801089942, 0, 0.364963502, 0)
Box.FontFace = Font.new("rbxasset://fonts/families/SourceSansSemibold.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Box.PlaceholderText = "nome do jogador aqui(iniciais do nome @ | Spawna blackhole na pessoa Cujo nome aqui)"
Box.Text = ""
Box.TextColor3 = Color3.fromRGB(255, 255, 255)
Box.TextScaled = true
Box.TextSize = 31.000
Box.TextWrapped = true

UITextSizeConstraint.Parent = Box
UITextSizeConstraint.MaxTextSize = 31

Label.Name = "Label"
Label.Parent = Main
Label.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
Label.BorderSizePixel = 0
Label.Size = UDim2.new(1, 0, 0.160583943, 0)
Label.FontFace = Font.new("rbxasset://fonts/families/Nunito.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Label.Text = "BlackHole | Police Brookhaven"
Label.TextColor3 = Color3.fromRGB(255, 255, 255)
Label.TextScaled = true
Label.TextSize = 14.000
Label.TextWrapped = true

UITextSizeConstraint_2.Parent = Label
UITextSizeConstraint_2.MaxTextSize = 21

Button.Name = "Button"
Button.Parent = Main
Button.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Button.BorderColor3 = Color3.fromRGB(0, 0, 0)
Button.BorderSizePixel = 0
Button.Position = UDim2.new(0.183284417, 0, 0.656760991, 0)
Button.Size = UDim2.new(0.629427791, 0, 0.277372271, 0)
Button.Font = Enum.Font.Nunito
Button.Text = "BlackHole | Off"
Button.TextColor3 = Color3.fromRGB(255, 255, 255)
Button.TextScaled = true
Button.TextSize = 28.000
Button.TextWrapped = true

UITextSizeConstraint_3.Parent = Button
UITextSizeConstraint_3.MaxTextSize = 28

-- Scripts:

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local UserInputService = game:GetService("UserInputService")
local Workspace = game:GetService("Workspace")

local character
local humanoidRootPart

mainStatus = true
UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
	if input.KeyCode == Enum.KeyCode.RightControl and not gameProcessedEvent then
		mainStatus = not mainStatus
		Main.Visible = mainStatus
	end
end)

local Folder = Instance.new("Folder", Workspace)
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1

if not getgenv().Network then
	getgenv().Network = {
		BaseParts = {},
		Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
	}

	Network.RetainPart = function(Part)
		if Part:IsA("BasePart") and Part:IsDescendantOf(Workspace) then
			table.insert(Network.BaseParts, Part)
			Part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
			Part.CanCollide = false
		end
	end

	local function EnablePartControl()
		LocalPlayer.ReplicationFocus = Workspace
		RunService.Heartbeat:Connect(function()
			sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
			for _, Part in pairs(Network.BaseParts) do
				if Part:IsDescendantOf(Workspace) then
					Part.Velocity = Network.Velocity
				end
			end
		end)
	end

	EnablePartControl()
end

local function ForcePart(v)
	if v:IsA("BasePart") and not v.Anchored and not v.Parent:FindFirstChildOfClass("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
		for _, x in ipairs(v:GetChildren()) do
			if x:IsA("BodyMover") or x:IsA("RocketPropulsion") then
				x:Destroy()
			end
		end
		if v:FindFirstChild("Attachment") then
			v:FindFirstChild("Attachment"):Destroy()
		end
		if v:FindFirstChild("AlignPosition") then
			v:FindFirstChild("AlignPosition"):Destroy()
		end
		if v:FindFirstChild("Torque") then
			v:FindFirstChild("Torque"):Destroy()
		end
		v.CanCollide = false
		local Torque = Instance.new("Torque", v)
		Torque.Torque = Vector3.new(100000, 100000, 100000)
		local AlignPosition = Instance.new("AlignPosition", v)
		local Attachment2 = Instance.new("Attachment", v)
		Torque.Attachment0 = Attachment2
		AlignPosition.MaxForce = math.huge
		AlignPosition.MaxVelocity = math.huge
		AlignPosition.Responsiveness = 200
		AlignPosition.Attachment0 = Attachment2
		AlignPosition.Attachment1 = Attachment1
	end
end

local blackHoleActive = false
local DescendantAddedConnection

local function toggleBlackHole()
	blackHoleActive = not blackHoleActive
	if blackHoleActive then
		Button.Text = "Blackhole | On"
		for _, v in ipairs(Workspace:GetDescendants()) do
			ForcePart(v)
		end

		DescendantAddedConnection = Workspace.DescendantAdded:Connect(function(v)
			if blackHoleActive then
				ForcePart(v)
			end
		end)

		spawn(function()
			while blackHoleActive and RunService.RenderStepped:Wait() do
				Attachment1.WorldCFrame = humanoidRootPart.CFrame
			end
		end)
	else
		Button.Text = "Blackhole | Off"
		if DescendantAddedConnection then
			DescendantAddedConnection:Disconnect()
		end
	end
end

local function getPlayer(name)
	local lowerName = string.lower(name)
	for _, p in pairs(Players:GetPlayers()) do
		local lowerPlayer = string.lower(p.Name)
		if string.find(lowerPlayer, lowerName) then
			return p
		elseif string.find(string.lower(p.DisplayName), lowerName) then
			return p
		end
	end
end

local player = nil

local function VDOYZQL_fake_script() -- Box.Script 
	local script = Instance.new('Script', Box)

	script.Parent.FocusLost:Connect(function(enterPressed)
		if enterPressed then
			player = getPlayer(Box.Text)
			if player then
				Box.Text = player.Name
				print("Player found:", player.Name)
			else
				print("Player not found")
			end
		end
	end)
end
coroutine.wrap(VDOYZQL_fake_script)()
local function JUBNQKI_fake_script() -- Button.Script 
	local script = Instance.new('Script', Button)

	script.Parent.MouseButton1Click:Connect(function()
		if player then
			character = player.Character or player.CharacterAdded:Wait()
			humanoidRootPart = character:WaitForChild("HumanoidRootPart")
			toggleBlackHole()
		else
			print("Player is not selected")
		end
	end)
end
coroutine.wrap(JUBNQKI_fake_script)()

print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Nameles Adm",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Nameless-Admin-V2-24856"))()
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Nameles V 11.3",
	Callback = function()
      		loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Nameless-admin-30209"))()
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "PB Hub V8.1",
	Callback = function()
      		loadstring(game:HttpGet("https://raw.githubusercontent.com/kiwi541/PB-Hub-obsfucando-v2/refs/heads/main/README.md"))()
print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "OutDoors",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "OutDoor 1 Teleport",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(444.0184631347656, 64.14906311035156, 511.88665771484375)
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Outdoor 2 Teleport",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-632.8937377929688, 26.354162216186523, 360.3209228515625)
print("button pressed")
  	end 
})


Tab:AddButton({
	Name = "Outdoor 3 Teleport",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-240.04434204101562, 89.30069732666016, -546.7059326171875)
print("button pressed")
  	end    
})


local Section = Tab:AddSection({
	Name = "Text Outdoor Chegue Perto de cada Outdoor"
})


Tab:AddButton({
	Name = "aplica text serve dominado[outdoor 3]",
	Callback = function()
      	local args = {
    [1] = "ReturningCommercialWords",
    [2] = 3,
    [4] = "Serve dominado"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Aplica Texto Serve dominado [Outdoor 2]",
	Callback = function()
      		local args = {
    [1] = "ReturningCommercialWords",
    [2] = 2,
    [4] = "serve dominado"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Aplica Texto Serve dominado [Outdoor 1]",
	Callback = function()
      		local args = {
    [1] = "ReturningCommercialWords",
    [2] = 1,
    [4] = "serve dominado"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "aplica text Police Brookhaven Domina[outdoor 3]",
	Callback = function()
      	local args = {
    [1] = "ReturningCommercialWords",
    [2] = 3,
    [4] = "Police Brookhaven Domina"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Aplica Texto Police Brookhaven Domina[Outdoor 2]",
	Callback = function()
      		local args = {
    [1] = "ReturningCommercialWords",
    [2] = 2,
    [4] = "Police Brookhaven Domina"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Aplica Texto Police Brookhaven Domina[Outdoor 1]",
	Callback = function()
      		local args = {
    [1] = "ReturningCommercialWords",
    [2] = 1,
    [4] = "Police Brookhaven Domina"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "Troll Version",
	Icon = "rbxassetid://18319058691",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "Troll Version",
	Callback = function()
      		local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- Lista de usuários autorizados
local authorizedUsers = {
    ["AdmBrookhaven4"] = true,
    ["sr_greg81"] = true,
    ["TwT_perdiminhaconta"] = true,
    ["scarys_cary66666"] = true,
    ["AdmBrookhaven5"] = true,
    ["kdjdhwie12"] = true,
    ["admbughaven4"] = true,
    ["Pguel_01"] = true,
    ["fazolpguel2"] = true,
    ["kdjdhwie14"] = true,
    ["kdjdhwie13"] = true,
    ["TemplariosHub"] = true,
    ["j3ffwoods"] = true,
    ["Ink_sannes13"] = true,
    ["juninho126501"] = true,
    ["baconbadass6"] = true,
    ["Johnatan_FF95"] = true,
    ["Nego_Doce144"] = true,
    ["joaoantonio1997"] = true,
    ["contadefarme12"] = true,
    ["sr_greg26"] = true,
    ["sirtjfoxy123"] = true,
    ["samuel123456game1"] = true,
    ["thekjahwn"] = true,
    ["bypassadonis"] = true,
    ["PerfFectBx4483"] = true,
    ["breno628e5"] = true,
    ["kdjdhwie"] = true,
    ["SCARYS_CARY66666"] = true,
    ["davigemes300617"] = true,
    ["ERROR887282"] = true,
    ["Meliodas1234328"] = true,
    ["ajudante_Claudio"] = true,
    ["hdqnwsn"] = true,
    ["thek01890"] = true,
    ["mano_shark6"] = true,
    ["volvinhr"] = true,
    ["KAIO_XTY"] = true,
    ["djekejsn"] = true,
    ["D99SHOP"] = true,
    ["cotryball8"] = true,
    ["ADMBROOKHAVEN6676"] = true,
    ["cuidado_025"] = true,
    ["PerfFectBx4483"] = true,
    ["Mateuszinban"] = true,
    ["nolyhaha"] = true,
    ["mTADORDEWEB666"] = true,
    ["contasecundariamrred"] = true,
    ["novacontapolicebrook"] = true,
    ["Nego_doce144"] = true,
    ["amandabrfofinhagam2"] = true,
    ["uehdutududgetd"] = true,
    ["PROBLEMATICOGAMES3"] = true,
    ["Tubers93_seculus"] = true,
}

-- Caso o jogador não seja autorizado, ele será kickado
if not authorizedUsers[LocalPlayer.Name] then
    LocalPlayer:Kick("❌️ Você não tem Permissão para Executar esse Script, fale com o criador dele para que ele libere seu acesso.")
    return
end


local Intro = Instance.new("ScreenGui")
local Logo = Instance.new("ImageLabel")
local Circle = Instance.new("UICorner")

Intro.Name = "Intro"
Intro.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
Intro.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Logo.Name = "Logo"
Logo.Parent = Intro
Logo.AnchorPoint = Vector2.new(0.5, 0.5)
Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Logo.BackgroundTransparency = 1.000
Logo.BorderColor3 = Color3.fromRGB(0, 0, 0)
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0.5, 0, 0.5, 0)
Logo.Size = UDim2.new(0, 400, 0, 400)
Logo.Image = "rbxassetid://86898373680592"
Logo.ImageTransparency = 0
Logo.ScaleType = Enum.ScaleType.Crop

Circle.CornerRadius = UDim.new(110235, 0)
Circle.Name = "Circle"
Circle.Parent = Logo

-- Timer de 3 segundos antes de desaparecer
task.wait(3) -- Aguarda 3 segundos
Logo:TweenSizeAndPosition(
    UDim2.new(0, 0, 0, 0), -- Diminui o logo
    UDim2.new(0.5, 0, 0.5, 0), -- Mantém no centro
    Enum.EasingDirection.Out,
    Enum.EasingStyle.Quad,
    1, -- Tempo da animação
    true,
    function()
        Intro:Destroy() -- Remove a tela de introdução
    end
)


local OrionLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/kiwi541/Libray-do-PB/refs/heads/main/README.md"))()
local Window = OrionLib:MakeWindow({
    Name = "PB HUB Troll Version V9.0",
    HidePremium = false, 
    SaveConfig = true, 
    ConfigFolder = "PBHubConfigs",
    IntroEnabled = true,
    IntroText = "Team Police Brookhaven",
    IntroIcon = "rbxassetid://86898373680592",
    Icon = "rbxassetid://86898373680592",
    CloseCallback = function() 
        print("PB hub fechado")
    end
})


local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "ScreenGui"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

local Toggle = Instance.new("ImageButton")
Toggle.Name = "Toggle"
Toggle.Parent = ScreenGui
Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Toggle.BackgroundTransparency = 0.5
Toggle.Position = UDim2.new(0, 0, 0.454706937, 0)
Toggle.Size = UDim2.new(0, 50, 0, 50)
Toggle.Image = "rbxassetid://86898373680592"
Toggle.Draggable = true

local Corner = Instance.new("UICorner")
Corner.CornerRadius = UDim.new(0.1, 0)
Corner.Parent = Toggle

local isOn = false
local selectedPlayerName = nil

local function onButtonClicked()
    if gethui():FindFirstChild("Orion") then
        gethui().Orion.Enabled = not gethui().Orion.Enabled
    end
end

local function offButtonClicked()
    if gethui():FindFirstChild("Orion") then
        gethui().Orion.Enabled = not gethui().Orion.Enabled
    end
end

Toggle.MouseButton1Click:Connect(function()
    isOn = not isOn
    if isOn then
        Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        onButtonClicked()
    else
        Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        offButtonClicked()
    end
end)


local playerName = game.Players.LocalPlayer.Name

OrionLib:MakeNotification({
    Name = "Bem-vindo(a)!",
    Content = "Olá " .. playerName,
    Image = "rbxassetid://132225387260946",
    Time = 5
})


local Tab = Window:MakeTab({
	Name = "Fling",
	Icon = "rbxassetid://10734975486",
	PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Fling"
})

local Targets = {""} -- Nome será preenchido pela TextBox
local LoopAtivo = false

-- TextBox para capturar o nome do jogador e armazenar em Targets[1]
Tab:AddTextbox({
    Name = "Digite o nome do Jogador",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        Targets[1] = Value
    end
})

-- Botão com a função completa no Callback e loop infinito usando RunService
Tab:AddToggle({
	Name = "Fling",
	Default = false,
	Callback = function(Value)
		if Value then
            -- Ativa o loop quando a toggle é ligada
            LoopAtivo = true
            task.spawn(function()
                while LoopAtivo do
                    local player = game.Players.LocalPlayer
 local mouse = player:GetMouse()
 local Targets = {Targets[1]}
 
 local Players = game:GetService("Players")
 local Player = Players.LocalPlayer
 
 local AllBool = false
 
 local GetPlayer = function(Name)
	Name = Name:lower()
	if Name == "all" or Name == "others" then
		AllBool = true
		return
	elseif Name == "random" then
		local GetPlayers = Players:GetPlayers()
		if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
		return GetPlayers[math.random(#GetPlayers)]
	elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
		for _,x in next, Players:GetPlayers() do
			if x ~= Player then
				if x.Name:lower():match("^"..Name) then
					return x;
				elseif x.DisplayName:lower():match("^"..Name) then
					return x;
				end
			end
		end
	else
		return
	end
 end
 
 local Message = function(_Title, _Text, Time)
	print(_Title)
	print(_Text)
	print(Time)
end

local SkidFling = function(TargetPlayer)
	local Character = Player.Character
	local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
	local RootPart = Humanoid and Humanoid.RootPart
 
	local TCharacter = TargetPlayer.Character
	local THumanoid
	local TRootPart
	local THead
	local Accessory
	local Handle
 
	if TCharacter:FindFirstChildOfClass("Humanoid") then
		THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
	end
	if THumanoid and THumanoid.RootPart then
		TRootPart = THumanoid.RootPart
	end
	if TCharacter:FindFirstChild("Head") then
		THead = TCharacter.Head
	end
	if TCharacter:FindFirstChildOfClass("Accessory") then
		Accessory = TCharacter:FindFirstChildOfClass("Accessory")
	end
	if Accessoy and Accessory:FindFirstChild("Handle") then
		Handle = Accessory.Handle
	end
 
	if Character and Humanoid and RootPart then
		if RootPart.Velocity.Magnitude < 50 then
			getgenv().OldPos = RootPart.CFrame
		end
		if THumanoid and THumanoid.Sit and not AllBool then
		end
		if THead then
			workspace.CurrentCamera.CameraSubject = THead
		elseif not THead and Handle then
			workspace.CurrentCamera.CameraSubject = Handle
		elseif THumanoid and TRootPart then
			workspace.CurrentCamera.CameraSubject = THumanoid
		end
		if not TCharacter:FindFirstChildWhichIsA("BasePart") then
			return
		end
		
		local FPos = function(BasePart, Pos, Ang)
			RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
			Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
			RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
			RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
		end
		
		local SFBasePart = function(BasePart)
			local TimeToWait = 1
			local Time = tick()
			local Angle = 0
 
			repeat
				if RootPart and THumanoid then
					if BasePart.Velocity.Magnitude < 80 then
						Angle = Angle + 100
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
					else
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
						
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
					end
				else
					break
				end
			until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
		end
		
		workspace.FallenPartsDestroyHeight = 0/0
		
		local BV = Instance.new("BodyVelocity")
		BV.Name = "EpixVel"
		BV.Parent = RootPart
		BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
		BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
		
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
		
		if TRootPart and THead then
			if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
				SFBasePart(THead)
			else
				SFBasePart(TRootPart)
			end
		elseif TRootPart and not THead then
			SFBasePart(TRootPart)
		elseif not TRootPart and THead then
			SFBasePart(THead)
		elseif not TRootPart and not THead and Accessory and Handle then
			SFBasePart(Handle)
		else
		end
		
		BV:Destroy()
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
		workspace.CurrentCamera.CameraSubject = Humanoid
	
		workspace.FallenPartsDestroyHeight = getgenv().FPDH
	else
	end
 end
 
 getgenv().Welcome = true
 if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end
 
 if AllBool then
	for _,x in next, Players:GetPlayers() do
		SkidFling(x)
	end
 end
 
 for _,x in next, Targets do
	if GetPlayer(x) and GetPlayer(x) ~= Player then
		if GetPlayer(x).UserId ~= 1414978355 then
			local TPlayer = GetPlayer(x)
			if TPlayer then
				SkidFling(TPlayer)
			end
		else
		end
	elseif not GetPlayer(x) and not AllBool then
	end
 end
                    task.wait(0.1)
                end
            end)
        else
            -- Desativa o loop quando a toggle é desligada
            LoopAtivo = false
        end
	end    
})

Tab:AddButton({
	Name = "Pegar Sofá",
	Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Couch"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Super Fling All",
	Callback = function()
      		local player = game.Players.LocalPlayer
 local mouse = player:GetMouse()
 local Targets = {"all"}
 
 local Players = game:GetService("Players")
 local Player = Players.LocalPlayer
 
 local AllBool = false
 
 local GetPlayer = function(Name)
	Name = Name:lower()
	if Name == "all" or Name == "others" then
		AllBool = true
		return
	elseif Name == "random" then
		local GetPlayers = Players:GetPlayers()
		if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
		return GetPlayers[math.random(#GetPlayers)]
	elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
		for _,x in next, Players:GetPlayers() do
			if x ~= Player then
				if x.Name:lower():match("^"..Name) then
					return x;
				elseif x.DisplayName:lower():match("^"..Name) then
					return x;
				end
			end
		end
	else
		return
	end
 end
 
 local Message = function(_Title, _Text, Time)
	print(_Title)
	print(_Text)
	print(Time)
end
 
 local SkidFling = function(TargetPlayer)
	local Character = Player.Character
	local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
	local RootPart = Humanoid and Humanoid.RootPart
 
	local TCharacter = TargetPlayer.Character
	local THumanoid
	local TRootPart
	local THead
	local Accessory
	local Handle
 
	if TCharacter:FindFirstChildOfClass("Humanoid") then
		THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
	end
	if THumanoid and THumanoid.RootPart then
		TRootPart = THumanoid.RootPart
	end
	if TCharacter:FindFirstChild("Head") then
		THead = TCharacter.Head
	end
	if TCharacter:FindFirstChildOfClass("Accessory") then
		Accessory = TCharacter:FindFirstChildOfClass("Accessory")
	end
	if Accessoy and Accessory:FindFirstChild("Handle") then
		Handle = Accessory.Handle
	end
 
	if Character and Humanoid and RootPart then
		if RootPart.Velocity.Magnitude < 50 then
			getgenv().OldPos = RootPart.CFrame
		end
		if THumanoid and THumanoid.Sit and not AllBool then
		end
		if THead then
			workspace.CurrentCamera.CameraSubject = THead
		elseif not THead and Handle then
			workspace.CurrentCamera.CameraSubject = Handle
		elseif THumanoid and TRootPart then
			workspace.CurrentCamera.CameraSubject = THumanoid
		end
		if not TCharacter:FindFirstChildWhichIsA("BasePart") then
			return
		end
		
		local FPos = function(BasePart, Pos, Ang)
			RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
			Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
			RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
			RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
		end
		
		local SFBasePart = function(BasePart)
			local TimeToWait = 2
			local Time = tick()
			local Angle = 0
 
			repeat
				if RootPart and THumanoid then
					if BasePart.Velocity.Magnitude < 50 then
						Angle = Angle + 100
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
					else
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
						
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
					end
				else
					break
				end
			until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
		end
		
		workspace.FallenPartsDestroyHeight = 0/0
		
		local BV = Instance.new("BodyVelocity")
		BV.Name = "EpixVel"
		BV.Parent = RootPart
		BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
		BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
		
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
		
		if TRootPart and THead then
			if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
				SFBasePart(THead)
			else
				SFBasePart(TRootPart)
			end
		elseif TRootPart and not THead then
			SFBasePart(TRootPart)
		elseif not TRootPart and THead then
			SFBasePart(THead)
		elseif not TRootPart and not THead and Accessory and Handle then
			SFBasePart(Handle)
		else
		end
		
		BV:Destroy()
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
		workspace.CurrentCamera.CameraSubject = Humanoid
		
		repeat
			RootPart.CFrame = getgenv().OldPos * CFrame.new(0, .5, 0)
			Character:SetPrimaryPartCFrame(getgenv().OldPos * CFrame.new(0, .5, 0))
			Humanoid:ChangeState("GettingUp")
			table.foreach(Character:GetChildren(), function(_, x)
				if x:IsA("BasePart") then
					x.Velocity, x.RotVelocity = Vector3.new(), Vector3.new()
				end
			end)
			task.wait()
		until (RootPart.Position - getgenv().OldPos.p).Magnitude < 25
		workspace.FallenPartsDestroyHeight = getgenv().FPDH
	else
	end
 end
 
 getgenv().Welcome = true
 if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end
 
 if AllBool then
	for _,x in next, Players:GetPlayers() do
		SkidFling(x)
	end
 end
 
 for _,x in next, Targets do
	if GetPlayer(x) and GetPlayer(x) ~= Player then
		if GetPlayer(x).UserId ~= 1414978355 then
			local TPlayer = GetPlayer(x)
			if TPlayer then
				SkidFling(TPlayer)
			end
		else
		end
	elseif not GetPlayer(x) and not AllBool then
	end
 end
  	end    
})


local playerTextbox

local function findPlayerByName(partialName)
    for _, player in pairs(game.Players:GetPlayers()) do
        if string.find(player.Name:lower(), partialName:lower()) or 
           string.find(player.DisplayName:lower(), partialName:lower()) then
            return player
        end
    end
    return nil
end

local function changeCharacterSize(sizeType, sizeValue)
    local args = {
        [1] = sizeType,
        [2] = sizeValue
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
end

local function equipAllItems()
    local myPlayer = game.Players.LocalPlayer
    local myCharacter = myPlayer.Character

    for _, tool in pairs(myPlayer.Backpack:GetChildren()) do
        if tool:IsA("Tool") then
            tool.Parent = myCharacter
            wait(0.1)
        end
    end
end

local function invokeServer()
    local args = {
        [1] = "PickingTools",
        [2] = "Couch"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
end

local function clearAllTools()
    local args = {
        [1] = "ClearAllTools"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))
end

local function isPlayerMoving(player)
    local character = player.Character
    if character then
        local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
        if humanoidRootPart then
            return humanoidRootPart.Velocity.Magnitude > 0.1
        end
    end
    return false
end

local function teleportToPlayer(targetPlayer, mode)
    local myPlayer = game.Players.LocalPlayer
    local myCharacter = myPlayer.Character
    local targetCharacter = targetPlayer.Character

    if not myCharacter or not targetCharacter then return end

    local originalPosition = myCharacter.PrimaryPart.CFrame
    local myHumanoid = myCharacter:FindFirstChildWhichIsA("Humanoid")

    local function executeTeleport()
        while true do
            if not targetPlayer.Parent then
                OrionLib:MakeNotification({
                    Name = "Player left",
                    Content = "The player has left the game.",
                    Time = 5
                })
                break
            end

            local humanoid = targetCharacter:FindFirstChildWhichIsA("Humanoid")
            if humanoid and humanoid:GetState() == Enum.HumanoidStateType.Seated then
                if mode == "fling" then
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(1e8, 1e8, 1e8))
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                elseif mode == "kill" then
                    local distantPosition = CFrame.new(176.308655, -496.272827, 153.928467, 0.444366872, 0.485874146, 0.75263828, -2.14771028e-08, 0.840143502, -0.54236412, -0.895844877, 0.240143502, 0.54236412)
                    myCharacter:SetPrimaryPartCFrame(distantPosition)
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                elseif mode == "bring" then
                    wait(0.01)
                    myCharacter:SetPrimaryPartCFrame(originalPosition)
                    if myHumanoid then
                        myHumanoid.PlatformStand = true
                        wait(1)
                        myHumanoid.PlatformStand = false
                    end
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                end
                break
            end

            local targetPosition = targetCharacter.PrimaryPart.Position
            local forwardDirection = targetCharacter.PrimaryPart.CFrame.LookVector
            local rightDirection = targetCharacter.PrimaryPart.CFrame.RightVector
            local upwardAdjustment = Vector3.new(0, 1, 0)

            if isPlayerMoving(targetPlayer) then
                local newPosition = targetPosition + forwardDirection * 25 + upwardAdjustment
                myCharacter:SetPrimaryPartCFrame(CFrame.new(newPosition))
                wait(0.1)
            else
                if mode == "kill" then
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - forwardDirection * 2 + upwardAdjustment))
                    wait(0.05)
                else
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                end
            end
        end
    end

    spawn(function()
        changeCharacterSize("CharacterSizeDown", 0.55)
        invokeServer()
        wait(1)
        equipAllItems()
        if myHumanoid then
            myHumanoid.PlatformStand = false
        end
        executeTeleport()
    end)
end

Tab:AddTextbox({
    Name = "Nick do player",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        playerTextbox = value
    end
})

Tab:AddButton({
    Name = "Bring Player",
    Callback = function()
        local targetPlayer = findPlayerByName(playerTextbox)
        if targetPlayer then
            teleportToPlayer(targetPlayer, "bring")
        else
            OrionLib:MakeNotification({
                Name = "Player not found",
                Content = "The player is not in the game.",
                Time = 5
            })
        end
    end
})


local Section = Tab:AddSection({
	Name = "Fling no Jogador que Descer do Sofá"
})

Tab:AddButton({
	Name = "Fling no Jogador que Descer do Sofá",
	Callback = function()
      		loadstring(game:HttpGet(('https://raw.githubusercontent.com/0Ben1/fe/main/obf_5wpM7bBcOPspmX7lQ3m75SrYNWqxZ858ai3tJdEAId6jSI05IOUB224FQ0VSAswH.lua.txt'),true))()
  	end    
})

local Section = Tab:AddSection({
	Name = "Infinite Yield"
})

Tab:AddButton({
	Name = "Infinite Yield FE",
	Callback = function()
      		loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()
  	end    
})


local Section = Tab:AddSection({
	Name = "View/Goto"
})


-- Lista de seleção de jogadores para "Goto"
local gotoPlayerList = {}
local selectedGotoPlayer = nil
local avisoToggle = false

local function updatePlayerList()
gotoPlayerList = {}
for _, player in ipairs(game.Players:GetPlayers()) do
table.insert(gotoPlayerList, player.Name)
end
end

updatePlayerList()


Tab:AddDropdown({
Name = "Lista de Jogadores",
Description = "Selecione o jogador alvo para o Goto (couch)",
Options = gotoPlayerList,
Callback = function(playerName)
selectedGotoPlayer = playerName
end
})

-- Adicionar botão para resetar a lista de jogadores
Tab:AddButton({
Name = "Reset Player List",
Callback = function()
updatePlayerList()
playerDropdown:Refresh(gotoPlayerList, true)
end
})

-- Adicionar toggle para view
Tab:AddToggle({
Name = "View",
Default = false,
Callback = function(state)
viewToggle = state
if viewToggle and selectedGotoPlayer then
local player = game.Players:FindFirstChild(selectedGotoPlayer)
if player then
game.Workspace.CurrentCamera.CameraSubject = player.Character.Humanoid
else
print("Jogador não encontrado.")
end
else
game.Workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
end
end
})

-- Adicionar toggle para follow
Tab:AddToggle({
Name = "Follow",
Default = false,
Callback = function(state)
followToggle = state
while followToggle do
if selectedGotoPlayer then
local player = game.Players:FindFirstChild(selectedGotoPlayer)
if player then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
else
print("Jogador não encontrado.")
end
end
wait(0.1)
end
end
})

-- Adicionar o botão "Goto" à seção "View/Goto"
Tab:AddButton({
Name = "Goto",
Description = "This player is not on the list",
Callback = function()
if selectedGotoPlayer then
local player = game.Players:FindFirstChild(selectedGotoPlayer)
if player then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
else
print("Jogador não encontrado.")
end
else
print("Nenhum jogador selecionado para o Goto.")
end
end
})


local Section = Tab:AddSection({
    Name = "all"
})


-- Variável para controlar o toggle
local teleportToggle = false

-- Função de teletransporte
local function teleportToPlayers()
    local localPlayer = game.Players.LocalPlayer
    local players = game.Players:GetPlayers()
    
    for _, player in pairs(players) do
        if not teleportToggle then break end -- Para se o toggle for desativado
        if player ~= localPlayer then
        --Ficar pequeno antes
        local args = {
[1] = "CharacterSizeDown",
[2] = 5
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
            -- Teleporta para o jogador
            local character = player.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                local hrp = character.HumanoidRootPart
                localPlayer.Character.HumanoidRootPart.CFrame = hrp.CFrame
                wait(1) -- Aguarda 1 segundo para evitar problemas de sincronia
            end
        end
        -- Teleporta para (-8.657157897949219, -222.3133087158203, -23.58349609375)
        localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-8.657157897949219, -222.3133087158203, -23.58349609375)
        wait(1) -- Aguarda antes de passar para o próximo jogador
    end
end

Tab:AddToggle({
    Name = "Kill All",
    Default = false,
    Callback = function(value)
        teleportToggle = value
        if teleportToggle then
            teleportToPlayers()
        end
    end
})

-- Variável para controlar o toggle
local teleportToggle = false

-- Função de teletransporte
local function teleportToSky()


--xaet

local args = {
[1] = "PickingTools",
[2] = "ShoppingCart"
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--xaetttttt

local args = {
[1] = "PickingTools",
[2] = "Stretcher"
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--Couch

local args = {
[1] = "PickingTools",
[2] = "Couch"
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--Equip itens

local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Couch")
equiparItem("ShoppingCart")
equiparItem("Stretcher")

    local localPlayer = game.Players.LocalPlayer
    local players = game.Players:GetPlayers()
    
    for _, player in pairs(players) do
        if not teleportToggle then break end -- Para se o toggle for desativado
        if player ~= localPlayer then
        --Ficar pequeno antes
        local args = {
[1] = "CharacterSizeDown",
[2] = 5
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
            -- Teleporta para o jogador
            local character = player.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                local hrp = character.HumanoidRootPart
                localPlayer.Character.HumanoidRootPart.CFrame = hrp.CFrame
                wait(1) -- Aguarda 1 segundo para evitar problemas de sincronia
            end
        end
        -- Teleporta para (9999999827968, 9999999827968, 9999999827968)
        localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(9999999827968, 9999999827968, 9999999827968)
        wait(1) -- Aguarda antes de passar para o próximo jogador
    end
end

Tab:AddToggle({
    Name = "Bug All",
    Default = false,
    Callback = function(value)
        teleportToggle = value
        if teleportToggle then
            teleportToSky()
        end
    end
})

-- Variáveis e serviços
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local TeleportToggle = false
local OriginalPosition

-- Função para teletransportar e voltar à posição original
local function TeleportToPlayers()
    while TeleportToggle do
        -- Salva a posição original do jogador
        if not OriginalPosition then
            OriginalPosition = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart").CFrame
        end
        
        for _, player in ipairs(Players:GetPlayers()) do
            -- Ignora o jogador local
            if player ~= LocalPlayer and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
                -- Teleporta para o jogador
                LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
                wait(1) -- Espera 1 segundo antes de ir para o próximo jogador
                
                -- Retorna para a posição original
                if OriginalPosition then
                    LocalPlayer.Character.HumanoidRootPart.CFrame = OriginalPosition
                end
                wait(1) -- Espera 1 segundo antes de continuar
            end
        end
        
        -- Reseta a posição original se todos foram visitados
        OriginalPosition = nil
    end
end


Tab:AddToggle({
    Name = "Bring all",
    Default = false,
    Callback = function(Value)
        TeleportToggle = Value
        if TeleportToggle then
            TeleportToPlayers()
        end
    end
})


local Tab = Window:MakeTab({
    Name = "Tools/Lag Server",
    Icon = "rbxassetid://10709769508",
    PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Duplicar Lanternas"
})

local countValue = 0

Tab:AddTextbox({
	Name = "Insira o Número de Lanternas",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		countValue = tonumber(Value)
        if not countValue then
            print("TemplariosHub")
        end
	end	  
})

Tab:AddButton({
	Name = "Duplicar Lanternas",
	Callback = function()
      		if countValue and countValue > 0 then
        -- Define referências
        local player = game.Players.LocalPlayer
        local initialPosition = player.Character.HumanoidRootPart.Position
        local targetPart = workspace["001_Lots"][player.Name .. "House"].HousePickedByPlayer.HouseModel.ToolsFlashLight.Touch

        -- Verifica se a parte existe
        if targetPart then
            -- Teleporta o jogador para a part e reduz a velocidade
            player.Character.HumanoidRootPart.CFrame = targetPart.CFrame
            player.Character.Humanoid.WalkSpeed = 0

            -- Executa o fireclickdetector o número de vezes especificado
            for i = 1, countValue do
                fireclickdetector(workspace["001_Lots"][player.Name .. "House"].HousePickedByPlayer.HouseModel.ToolsFlashLight.Tools.FlashLight.ClickDetector)
                wait(0.5)
            end

            -- Retorna o jogador ao local original e restaura a velocidade
            player.Character.HumanoidRootPart.CFrame = CFrame.new(initialPosition)
            player.Character.Humanoid.WalkSpeed = 16
        else
            -- Notificação com imagem caso a part não exista
            game.StarterGui:SetCore("SendNotification", {
                Title = "Templarios Hub",
                Text = "Falha ao Duplicar Lanternas, Verifique se Colocou essa Casa. (Casa da Agency)",
                Duration = 5,
                Icon = "rbxassetid://78517296345487" -- Substitua pelo ID da imagem desejada
            })
        end
    else
        print("TemplariosHub")
    end
  	end    
})

Tab:AddParagraph("Atenção!","Lembre-se que você deve pegar a Casa da Agency Para o Duplicar Lanternas Funcionar!")

local Section = Tab:AddSection({
	Name = "Duplicar Extintores"
})

local player = game.Players.LocalPlayer
local dupeCount -- Variável para armazenar o número digitado

Tab:AddTextbox({
	Name = "Insira o Número de Extintores",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		dupeCount = tonumber(Value) -- Converte o valor digitado para número
		if not dupeCount or dupeCount <= 0 then
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
	end	  
})

local function getCharacterComponents()
	local character = player.Character or player.CharacterAdded:Wait()
	return character:WaitForChild("Humanoid"), character:WaitForChild("HumanoidRootPart")
end

local function findClickDetector()
	-- Verifica se o objeto FireX e seus filhos existem no novo caminho
	local fireX = workspace.WorkspaceCom["001_DayCare"].Tools:FindFirstChild("FireX")
	if fireX then
		-- Procura por um ClickDetector dentro de FireX
		for _, child in ipairs(fireX:GetChildren()) do
			if child:IsA("ClickDetector") then
				return child -- Retorna o ClickDetector encontrado
			end
		end
	end
	return nil -- Retorna nil se nenhum ClickDetector for encontrado
end

Tab:AddButton({
	Name = "Duplicar Extintores",
	Callback = function()
		local humanoid, rootPart = getCharacterComponents() -- Obtém componentes atualizados
		local clickDetector = findClickDetector() -- Obtém o ClickDetector dentro de FireX

		if dupeCount and dupeCount > 0 and clickDetector then
			local originalPosition = rootPart.Position -- Armazena a posição inicial do jogador
			local originalSpeed = humanoid.WalkSpeed -- Armazena a velocidade original do jogador

			-- Teleporta o jogador para a nova posição e define a velocidade para 0
			rootPart.CFrame = CFrame.new(433.39031982421875, -107.79502868652344, 101.17525482177734)
			humanoid.WalkSpeed = 0

			-- Executa o fireclickdetector a quantidade de vezes desejada
			for i = 1, dupeCount do
				fireclickdetector(clickDetector)
				wait(0.5) -- Intervalo entre execuções
			end

			-- Aguarda 3 segundos antes de restaurar a posição e a velocidade
			wait(3)
			rootPart.CFrame = CFrame.new(originalPosition)
			humanoid.WalkSpeed = originalSpeed
		else
			print("Por favor, insira um número válido ou verifique se o ClickDetector existe.") -- Mensagem de erro se não for um número válido ou o ClickDetector não for encontrado
		end
	end    
})

-- Reatribui componentes após o reset
player.CharacterAdded:Connect(function()
	player.Character:WaitForChild("Humanoid").Changed:Connect(function()
		humanoid, rootPart = getCharacterComponents()
	end)
end)

local Section = Tab:AddSection({
	Name = "Duplicar Guitarras"
})

local player = game.Players.LocalPlayer
local humanoid = player.Character:WaitForChild("Humanoid")
local rootPart = player.Character:WaitForChild("HumanoidRootPart")
local dupeCount -- Variável para armazenar o número digitado

Tab:AddTextbox({
	Name = "Insira o Número de Guitarras",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		dupeCount = tonumber(Value) -- Converte o valor digitado para número
		if not dupeCount or dupeCount <= 0 then
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
	end	  
})

Tab:AddButton({
	Name = "Duplicar Guitarras",
	Callback = function()
      		-- Verifica se o valor é válido
		if dupeCount and dupeCount > 0 then
			local originalPosition = rootPart.Position -- Armazena a posição inicial do jogador
			local originalSpeed = humanoid.WalkSpeed -- Armazena a velocidade original do jogador

			-- Teleporta o jogador para a nova posição e define a velocidade para 0
			rootPart.CFrame = CFrame.new(-379.8940124511719, 18.473968505859375, 211.9053955078125)
			humanoid.WalkSpeed = 0
			
			-- Executa o fireclickdetector a quantidade de vezes desejada
			for i = 1, dupeCount do
				fireclickdetector(workspace.WorkspaceCom["001_GiveTools"].ElectricGuitar.ClickDetector)
				game:GetService("VirtualInputManager"):SendKeyEvent(true,Enum.KeyCode.F,false,game)
				wait(0.5) -- Intervalo entre execuções
			end

			-- Aguarda 3 segundos antes de restaurar a posição e a velocidade
			wait(3)
			rootPart.CFrame = CFrame.new(originalPosition)
			humanoid.WalkSpeed = originalSpeed
		else
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
  	end    
})

local Section = Tab:AddSection({
	Name = "Duplicar Violões"
})

local player = game.Players.LocalPlayer
local humanoid = player.Character:WaitForChild("Humanoid")
local rootPart = player.Character:WaitForChild("HumanoidRootPart")
local dupeCount -- Variável para armazenar o número digitado

Tab:AddTextbox({
	Name = "Insira o Número de Violões",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		dupeCount = tonumber(Value) -- Converte o valor digitado para número
		if not dupeCount or dupeCount <= 0 then
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
	end	  
})

Tab:AddButton({
	Name = "Duplicar Violões",
	Callback = function()
      		-- Verifica se o valor é válido
		if dupeCount and dupeCount > 0 then
			local originalPosition = rootPart.Position -- Armazena a posição inicial do jogador
			local originalSpeed = humanoid.WalkSpeed -- Armazena a velocidade original do jogador

			-- Teleporta o jogador para a nova posição e define a velocidade para 0
			rootPart.CFrame = CFrame.new(-379.8940124511719, 18.473968505859375, 211.9053955078125)
			humanoid.WalkSpeed = 0
			
			-- Executa o fireclickdetector a quantidade de vezes desejada
			for i = 1, dupeCount do
				fireclickdetector(workspace.WorkspaceCom["001_GiveTools"].Guitar.ClickDetector)
				game:GetService("VirtualInputManager"):SendKeyEvent(true,Enum.KeyCode.F,false,game)
				wait(0.5) -- Intervalo entre execuções
			end

			-- Aguarda 3 segundos antes de restaurar a posição e a velocidade
			wait(3)
			rootPart.CFrame = CFrame.new(originalPosition)
			humanoid.WalkSpeed = originalSpeed
		else
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
  	end    
})

local Section = Tab:AddSection({
	Name = "Equipar todos os items"
})

Tab:AddButton({
    Name = "Equipar Todos os Items",
    Callback = function()
local function equiptool()
  for i,v in ipairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
    if v:IsA("Tool") then
      v.Parent = game.Players.LocalPlayer.Character
    end
  end
end
equiptool()

    end
})

local Section = Tab:AddSection({
	Name = "Lag Server"
})

-- Variáveis
local isLooping = false -- Controle do loop
local originalPosition = nil -- Para armazenar a posição original do jogador
local player = game.Players.LocalPlayer -- Referência ao jogador local
local selectedDevice = "Celular" -- Valor padrão do dispositivo

Tab:AddDropdown({
    Name = "Selecionar o Que Vai Usar Para Lagar o Servidor",
    Default = "Celular",
    Options = {"Laptop", "Celular", "Caça Fantasmas", "Celular e Laptop"},
    Callback = function(Value)
        selectedDevice = Value -- Atualiza o dispositivo selecionado com base na escolha do usuário
    end
})

-- Função para iniciar o loop
local function startLoop()
    if not isLooping then
        isLooping = true
        originalPosition = player.Character and player.Character:FindFirstChild("HumanoidRootPart") and player.Character.HumanoidRootPart.Position

        -- Define coordenadas baseadas no dispositivo selecionado
        local teleportPosition
        if selectedDevice == "Laptop" then
            teleportPosition = Vector3.new(-123.742, 20.074, 251.402)
        elseif selectedDevice == "Celular" then
            teleportPosition = Vector3.new(-123.742, 20.074, 251.402)
        elseif selectedDevice == "Caça Fantasmas" then
            teleportPosition = Vector3.new(-320.216, 7.4, -112.32)
        elseif selectedDevice == "Celular e Laptop" then
            teleportPosition = Vector3.new(-123.742, 20.074, 251.402)
        end

        -- Teleporta o jogador para a nova posição
        if teleportPosition then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(teleportPosition)
        end

        -- Define a velocidade para 0
        player.Character.Humanoid.WalkSpeed = 0

        -- Loop principal
        while isLooping do
            -- Verifica o dispositivo selecionado e executa o ClickDetector correspondente
            if selectedDevice == "Laptop" then
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools.Laptop.ClickDetector)
            elseif selectedDevice == "Celular" then
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools:GetChildren()[3].ClickDetector)
            elseif selectedDevice == "Caça Fantasmas" then
                fireclickdetector(workspace.WorkspaceCom["001_GiveTools"].GhostMeter.ClickDetector)
            elseif selectedDevice == "Celular e Laptop" then
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools:GetChildren()[3].ClickDetector)
                wait(0.1)
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools.Laptop.ClickDetector)
            end
            wait(0.01) -- Espera 0.01 segundo
        end
    end
end

-- Função para parar o loop e voltar à posição original
local function stopLoop()
    if isLooping then
        isLooping = false -- Para o loop
        wait(0.1) -- Espera um pouco antes de voltar

        -- Teleporta de volta para a posição original
        if originalPosition then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(originalPosition)
        end

        -- Restaura a velocidade para 16
        player.Character.Humanoid.WalkSpeed = 16
    end
end

-- Reinicializa as variáveis em caso de reset do personagem
player.CharacterAdded:Connect(function()
    isLooping = false -- Garante que o loop seja parado ao resetar
    originalPosition = nil -- Reseta a posição original
end)

-- Botão para iniciar o loop
Tab:AddButton({
    Name = "Lagar Servidor",
    Callback = function()
        startLoop()
    end
})

-- Botão para parar o loop
Tab:AddButton({
    Name = "Parar de Lagar",
    Callback = function()
        stopLoop()
    end
})

Tab:AddParagraph("Atenção", "Caso seu Celular não Seja Muito Bom não é Recomendado que use o Lagar Servidor!")

local Section = Tab:AddSection({
    Name = "Áudio"
})

Tab:AddButton({
	Name = "Pegar Sniper (Necessário)",
	Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

  	end    
})

-- TextBox para inserir o ID
Tab:AddTextbox({
    Name = "Digite o ID do Áudio",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        Value = value
    end
})

-- Botão para executar a função uma vez
Tab:AddButton({
    Name = "Tocar Áudio",
    Callback = function()
        if Value then
            local args = {
                [1] = game:GetService("Players").LocalPlayer.Character.Sniper.Handle,
                [2] = Value,
                [3] = 1
            }
            game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s"):FireServer(unpack(args))
            
            local soundId = "rbxassetid://" .. Value
            local sound = Instance.new("Sound")
            sound.SoundId = soundId
            sound.Parent = game.Workspace
            sound.Volume = 0.3
            
            sound:Play()
            wait(3)
            sound:Stop()
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Insira um ID válido antes de executar.",
                Image = "rbxassetid://132225387260946",
                Time = 5
            })
        end
    end
})

-- Toggle para ativar/desativar o loop
Tab:AddToggle({
    Name = "Loop Audio",
    Default = false,
    Callback = function(value)
        looping = value
        
        while looping do
            if Value then
                local args = {
                    [1] = game:GetService("Players").LocalPlayer.Character.Sniper.Handle,
                    [2] = Value,
                    [3] = 1
                }
                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s"):FireServer(unpack(args))
                
                local soundId = "rbxassetid://" .. Value
                local sound = Instance.new("Sound")
                sound.SoundId = soundId
                sound.Parent = game.Workspace
                sound.Volume = 0.1
                
                sound:Play()
                wait(3)
                sound:Stop()
            else
                OrionLib:MakeNotification({
                    Name = "Erro",
                    Content = "Insira um ID antes de ativar o loop som.",
                    Image = "rbxassetid://132225387260946",
                    Time = 5
                })
                break
            end
            wait(1) -- Intervalo entre execuções
        end
    end
})

Tab:AddParagraph("Atenção","Você deve segurar a <font color='rgb(0, 255, 0)'>Sniper</font> para que o áudio seja executado corretamente de forma FE, suporta o som por 3 segundos")

local Section = Tab:AddSection({
    Name = "Áudio All"
})

Tab:AddButton({
	Name = "Pegar Sniper (Necessário)",
	Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

  	end    
})

-- Variáveis
local Value = ""  -- ID do som será inserido pelo usuário
local Speed = 1   -- Velocidade padrão (pode ser ajustada)
local isPlaying = false  -- Estado do toggle
local interval = 0.1  -- Tempo padrão entre execuções

-- Função para tocar o som localmente
local function playSoundLocally(Value, Speed)
    local soundId = "rbxassetid://" .. Value
    local sound = Instance.new("Sound")
    sound.SoundId = soundId
    sound.Parent = game.Workspace
    sound.Volume = 0.3
    sound.PlaybackSpeed = Speed  -- Velocidade do som

    sound:Play()

    -- O som será destruído após 3 segundos, mas isso não impede a execução contínua
    game:GetService("Debris"):AddItem(sound, 3)
end

-- Função para enviar o evento ao servidor
local function playSoundServer(Value, Speed)
    local args = {
        [1] = workspace,
        [2] = Value,
        [3] = Speed
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s"):FireServer(unpack(args))
end

-- TextBox para inserir o ID do som
Tab:AddTextbox({
    Name = "ID do Áudio",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        Value = value  -- Atualizando o ID do som
    end
})

-- TextBox para inserir a velocidade do som
Tab:AddTextbox({
    Name = "Velocidade do Áudio",
    Default = "1",
    TextDisappear = true,
    Callback = function(value)
        Speed = tonumber(value) or 1  -- Garantindo que a velocidade seja um número, se não for, usa 1
    end
})

-- Botão para tocar o som uma vez
Tab:AddButton({
    Name = "Tocar Áudio",
    Callback = function()
        if Value == "" then
            print("Você não colocou nemhum ID de Áudio")
        else
            playSoundLocally(Value, Speed)  -- Toca o som localmente
            playSoundServer(Value, Speed)  -- Envia o evento ao servidor
        end
    end
})

-- Toggle para tocar o som repetidamente
Tab:AddToggle({
    Name = "Loop Áudio All",
    Default = false,
    Callback = function(state)
        isPlaying = state  -- Atualizando o estado do toggle
        if isPlaying then
            -- Loop para tocar o som enquanto o toggle estiver ativado
            coroutine.wrap(function()
                while isPlaying do
                    if Value ~= "" then
                        playSoundLocally(Value, Speed)  -- Toca o som localmente
                        playSoundServer(Value, Speed)  -- Envia o evento ao servidor
                    else
                        print("Você não colocou nemhum ID de Áudio")
                        break
                    end
                    wait(interval)  -- Usa o intervalo definido pelo usuário
                end
            end)()
        end
    end
})

-- TextBox para ajustar o intervalo do toggle
Tab:AddTextbox({
    Name = "Intervalo para o Loop Áudio All",
    Default = "0.5",
    TextDisappear = true,
    Callback = function(value)
        interval = tonumber(value) or 0.5  -- Atualiza o intervalo, valor padrão é 0.1
        if interval <= 0 then
            interval = 0.5  -- Garante que o intervalo não seja zero ou negativo
            print("Intervalo do Loop Áudio All Definido")
        end
    end
})

Tab:AddParagraph("Atenção","No áudio all, você não precisa segurar a sniper na mão para funcionar mas deve ter ela no seu inventário. Também suporta 3 segundos.")


local Section = Tab:AddSection({
	Name = "Wall Items"
})


Tab:AddButton({
	Name = "Wall Box",
	Callback = function()
      		local function fragiotakis() local Player = game.Players.LocalPlayer local Character = Player.Character or Player.CharacterAdded:Wait() local RootPart = Character:WaitForChild("HumanoidRootPart") local Clone = game:GetService("Workspace"):FindFirstChild("WorkspaceCom") and game:GetService("Workspace").WorkspaceCom:FindFirstChild("001_GiveTools") and game:GetService("Workspace").WorkspaceCom["001_GiveTools"]:FindFirstChild("Box")

if Clone and Clone:FindFirstChild("ClickDetector") then
    local OldPos = RootPart.CFrame

    for i = 1, 12 do
        RootPart.CFrame = Clone.CFrame
        fireclickdetector(Clone.ClickDetector)
        task.wait(0)
    end

    RootPart.CFrame = OldPos
else
    warn("tu deve ter bugado ou o mapa deu algum bo!")
end

end

for i = 1, 50 do fragiotakis() task.wait(0.0) end

local function BundaGorda() 
local args
 = { [1] = "PickingTools",
 [2] = "Box" }

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

local tools = {}
for _, tool in pairs(backpack:GetChildren()) do
    if tool.Name == "Box" then
        table.insert(tools, tool)
    end
end

local startPosition = Vector3.new(0, 4, 0)
local spacingX, spacingY = 1, 2
local columns = 5

for i, tool in ipairs(tools) do
    local row = math.floor((i - 1) / columns)
    local column = (i - 1) % columns
    tool.Parent = player.Character
    tool.GripPos = startPosition + Vector3.new(column * spacingX, -row * spacingY, 0)
    tool.Grip = CFrame.new(startPosition + Vector3.new(column * spacingX, -row * spacingY, 0)) * CFrame.Angles(math.rad(90), 0, 0)
end

end

BundaGorda()
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Wall Extinto",
	Callback = function()
      		local function fragiotakis()
    local Player = game.Players.LocalPlayer
    local Character = Player.Character or Player.CharacterAdded:Wait()
    local RootPart = Character:WaitForChild("HumanoidRootPart")
    local Clone = game:GetService("Workspace"):FindFirstChild("WorkspaceCom") 
        and game:GetService("Workspace").WorkspaceCom:FindFirstChild("001_GiveTools") 
        and game:GetService("Workspace").WorkspaceCom["001_GiveTools"]:FindFirstChild("FireX")

    if Clone and Clone:FindFirstChild("ClickDetector") then
        local OldPos = RootPart.CFrame

        for i = 1, 21 do
            RootPart.CFrame = Clone.CFrame
            fireclickdetector(Clone.ClickDetector)
            task.wait(0)
        end

        RootPart.CFrame = OldPos
    else
        warn("tu deve ter bugado ou o ClickDetector deu algum erro!")
    end
end

for i = 1, 20 do
    fragiotakis()
    task.wait(0.0)
end

local function Cugostoso()
    local args = {
        [1] = "PickingTools",
        [2] = "FireX"
    }

    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
    wait(0.1)
    local player = game.Players.LocalPlayer
    local backpack = player:WaitForChild("Backpack")
    
    local tools = {}
    for _, tool in pairs(backpack:GetChildren()) do
        if tool.Name == "FireX" then
            table.insert(tools, tool)
        end
    end

    local startPosition = Vector3.new(0, 3, 0)
    local spacing = 1

    for i, tool in ipairs(tools) do
        tool.Parent = player.Character
        tool.GripPos = startPosition + Vector3.new(i * spacing, 0, 0)
        tool.Grip = CFrame.new(startPosition + Vector3.new(i * spacing, 0, 0)) * CFrame.Angles(math.rad(90), 0, 0)
    end
end

Cugostoso()
print("button pressed")
  	end    
})


local Section = Tab:AddSection({
	Name = "Lag Botões"
})


Tab:AddButton({
	Name = "Lag Taser",
	Callback = function()
      		local function duplicarTaser()
    local Player = game.Players.LocalPlayer
    local Character = Player.Character or Player.CharacterAdded:Wait()
    local RootPart = Character:WaitForChild("HumanoidRootPart")
    local TaserPath = game:GetService("Workspace"):FindFirstChild("WorkspaceCom") 
        and game:GetService("Workspace").WorkspaceCom["001_GiveTools"]:FindFirstChild("Taser")

    if TaserPath and TaserPath:FindFirstChild("ClickDetector") then
        local OldPos = RootPart.CFrame

        for i = 1, 12 do
            RootPart.CFrame = TaserPath.CFrame
            fireclickdetector(TaserPath:FindFirstChild("ClickDetector"))
            task.wait(0)
        end

        RootPart.CFrame = OldPos
    else
        warn("Erro ao encontrar o Taser! Tente novamente.")
    end
end

-- Loop infinito para duplicação
while true do
    duplicarTaser()
    task.wait(0.001)
end
print("button pressed")
  	end    
})


local toggles = {
    DupeBasketball = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeBasketball do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
            clickNormally(itemPath)
            teleportCount = teleportCount + 1
            wait(0.01) -- Tempo de espera para evitar travamento
        end
    else
        warn("Item não encontrado.")
    end
end

Tab:AddToggle({
	Name = "Lag basketball",
	Default = false,
	Callback = function(state)
		toggles.DupeBasketball = state
        if state then
            local basketballPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_GiveTools"):FindFirstChild("Basketball")
            spawn(function()
                dupeItem(basketballPath, 9999999999999999999999999999999999999)
            end)
        else
            print("Dupe Basketball desligado.")
        end
	end    
})

local toggles = {
    DupeExtintor = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeExtintor do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
            clickNormally(itemPath)
            teleportCount = teleportCount + 1
            wait(0.01) -- Tempo de espera para evitar travamento
        end
    else
        warn("Item não encontrado.")
    end
end


Tab:AddToggle({
	Name = "Lag extinto",
	Default = false,
	Callback = function(state)
		toggles.DupeExtintor = state
        if state then
            local fireXPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_GiveTools"):FindFirstChild("FireX")
            spawn(function()
                dupeItem(fireXPath, 999999999999999999999999999999999999999)
            end)
        else
            print("Dupe Extintor desligado.")
        end
	end    
})


local toggles = {
    DupeBook = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeBook do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
            clickNormally(itemPath)
            teleportCount = teleportCount + 1
            wait(0.01) -- Tempo de espera para evitar travamento
        end
    else
        warn("Item não encontrado.")
    end
end

Tab:AddToggle({
	Name = "Lag Book",
	Default = false,
	Callback = function(state)
		toggles.DupeBook = state
        if state then
            local bookPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_DayCare"):FindFirstChild("Tools"):FindFirstChild("Book")
            spawn(function()
                dupeItem(bookPath, 99999999999999999999999999999999999)
            end)
        else
            print("Dupe Book desligado.")
        end
	end    
})


local toggles = {
    DupeStretcher = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeStretcher do
            if game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
                clickNormally(itemPath)
                teleportCount = teleportCount + 1
                wait(0.01) -- Tempo de espera para evitar travamento
            else
                warn("Personagem do jogador não encontrado.")
                break
            end
        end
    else
        warn("ItemPath inválido.")
    end
end

local function dupeStretcher()
    local stretcherPath = workspace:FindFirstChild("WorkspaceCom")
        and workspace.WorkspaceCom:FindFirstChild("001_GiveTools")
        and workspace.WorkspaceCom["001_GiveTools"]:FindFirstChild("Stretcher")
    
    if stretcherPath then
        dupeItem(stretcherPath, 9999999999999999999999999999999999999999999999999999999999) -- Duplicar 300 vezes
    else
        warn("Item Stretcher não encontrado.")
    end
end


Tab:AddToggle({
	Name = "Lag Stretcher",
	Default = false,
	Callback = function(state)
		toggles.DupeStretcher = state
        if state then
            spawn(function()
                while toggles.DupeStretcher do
                    dupeStretcher()
                    wait(0.1) -- Espera entre duplicações
                end
            end)
        else
            print("Dupe Stretcher desligado.")
        end
	end    
})


local Tab = Window:MakeTab({
    Name = "Outros/Trolar",
    Icon = "rbxassetid://10734888000",
    PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Blackhole V2"
})

Tab:AddToggle({
    Name = "Blackhole V2",
    Default = false,
    Callback = function(Value)
        if Value then
            -- Quando a toggle estiver ativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Blackhole1/raw/refs/heads/main/Blackhole1Obfuscate.txt"))()
        else
            -- Quando a toggle estiver desativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Blackhole2/raw/refs/heads/main/Blackhole2Obfuscate.txt"))()
        end
    end
})

local Section = Tab:AddSection({
	Name = "Anti Void"
})

-- Variável de controle
local voidImmunityEnabled = false

-- Função para ativar/desativar a imunidade ao void
local function setVoidImmunity(state)
    if state then
        workspace.FallenPartsDestroyHeight = 0/0
    else
        workspace.FallenPartsDestroyHeight = -500 -- Valor padrão do Roblox
    end
end

-- Toggle para o Orion Lib
Tab:AddToggle({
    Name = "Anti Void",
    Default = false,
    Callback = function(State)
        voidImmunityEnabled = State
        setVoidImmunity(voidImmunityEnabled)
    end
})

local Section = Tab:AddSection({
	Name = "Tornado"
})

Tab:AddToggle({
    Name = "Tornado",
    Default = false,
    Callback = function(Value)
        if Value then
            -- Quando a toggle estiver ativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Tornado/raw/refs/heads/main/TornadoObfuscate.txt"))()
        else
            -- Quando a toggle estiver desativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Blackhole2/raw/refs/heads/main/Blackhole2Obfuscate.txt"))()
        end
    end
})

local Section = Tab:AddSection({
	Name = "Não Sentar em Carros/Items/Etc"
})

-- Tabela para armazenar o estado original dos assentos
local originalSeatStates = {}
-- Tabela para armazenar as conexões dos eventos
local connections = {}

-- Função que desabilita a habilidade de sentar
local function disableSeating()
    for _, seat in pairs(workspace:GetDescendants()) do
        if seat:IsA("Seat") or seat:IsA("VehicleSeat") then
            originalSeatStates[seat] = seat.Disabled
            seat.Disabled = true
        end
    end

    table.insert(connections, workspace.DescendantAdded:Connect(function(descendant)
        if descendant:IsA("Seat") or descendant:IsA("VehicleSeat") then
            originalSeatStates[descendant] = descendant.Disabled
            descendant.Disabled = true
        end
    end))

    for _, player in pairs(game:GetService("Players"):GetPlayers()) do
        table.insert(connections, player.CharacterAdded:Connect(function(character)
            table.insert(connections, character.DescendantAdded:Connect(function(descendant)
                if descendant:IsA("SeatWeld") then
                    descendant:Destroy()
                end
            end))
        end))
    end
end

-- Função que reativa a habilidade de sentar
local function enableSeating()
    for seat, originalState in pairs(originalSeatStates) do
        if seat and seat.Parent then
            seat.Disabled = originalState
        end
    end

    -- Desconecta todos os eventos
    for _, connection in pairs(connections) do
        connection:Disconnect()
    end
    connections = {}

    -- Certifica-se de que todos os assentos estejam habilitados
    for _, seat in pairs(workspace:GetDescendants()) do
        if seat:IsA("Seat") or seat:IsA("VehicleSeat") then
            seat.Disabled = false
        end
    end

    -- Remove qualquer conexão de assento existente
    for _, player in pairs(game:GetService("Players"):GetPlayers()) do
        if player.Character then
            for _, descendant in pairs(player.Character:GetDescendants()) do
                if descendant:IsA("SeatWeld") then
                    descendant:Destroy()
                end
            end
        end
    end
end

Tab:AddToggle({
    Name = "Não Sentar em Carros/Items/Etc",
    Default = false,
    Callback = function(value)
        if value then
            disableSeating()
        else
            enableSeating()
        end
    end
})

local Section = Tab:AddSection({
	Name = "Anti Fling"
})

-- Função para deletar o veículo específico de um jogador
local function deleteVehicleFromPlayer(player)
    local vehiclesFolder = workspace:FindFirstChild("Vehicles")
    if vehiclesFolder then
        local vehicleName = player.Name .. "Car"
        local vehicle = vehiclesFolder:FindFirstChild(vehicleName)
        if vehicle then
            vehicle:Destroy()
            print("Veículo deletado para: " .. player.Name)
        else
            warn("Veículo não encontrado para: " .. player.Name)
        end
    end
end

-- Função para deletar o veículo de todos os jogadores
local function deleteVehicleFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deleteVehicleFromPlayer(player)
    end
end

-- Função para deletar as parts associadas ao jogador
local function deletePartsFromPlayer(player)
    local admFolder = workspace:FindFirstChild(player.Name)
    if admFolder then
        -- Lista das parts a serem deletadas
        local partsToDelete = {"Couch", "Stretcher", "Wagon", "Stroller", "ShoppingCart", "LawnMower"}
        
        for _, partName in pairs(partsToDelete) do
            local part = admFolder:FindFirstChild(partName)
            if part then
                part:Destroy()
                print(partName .. " deletada para: " .. player.Name)
            else
                warn(partName .. " não encontrada para: " .. player.Name)
            end
        end
    end
end

-- Função para deletar as parts de todos os jogadores
local function deletePartsFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deletePartsFromPlayer(player)
    end
end

-- Variável de controle do loop
local isLooping = false

-- Função para controlar o loop
local function startLoop()
    while isLooping do
        deleteVehicleFromAllPlayers()       -- Deletar veículos de todos os jogadores
        deletePartsFromAllPlayers()         -- Deletar as parts de todos os jogadores
        wait(1) -- Tempo entre cada execução do loop (5 segundos neste exemplo)
    end
end

Tab:AddToggle({
    Name = "Anti Fling",
    Default = false,
    Callback = function(state)
        isLooping = state
        if isLooping then
            startLoop()
        end
    end    
})


local Section = Tab:AddSection({
	Name = "Anti Lag Server"
})

local Players = game:GetService("Players")

local PlayerName = ""

Tab:AddTextbox({
    Name = "Nome do Jogador que está lagando",
    Default = "",
    TextDisappear = false,
    Callback = function(value)
        PlayerName = value
    end
})

Tab:AddButton({
    Name = "Ativar Anti Lag Server",
    Callback = function()
        if PlayerName and PlayerName ~= "" then
            for _, player in ipairs(Players:GetPlayers()) do
                if string.find(player.Name:lower(), PlayerName:lower()) then
                    local character = workspace:FindFirstChild(player.Name)
                    if character then
                        character:Destroy()
                    end
                    local playerInstance = Players:FindFirstChild(player.Name)
                    if playerInstance then
                        playerInstance:Destroy()
                    end
                end
            end
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Jogador não encontrado",
                Image = "rbxassetid://132225387260946",
                Time = 5
            })
        end
    end
})

local Section = Tab:AddSection({
	Name = "Notificar Saída e Entrada dos Jogadores"
})

local notifyPlayers = false

Tab:AddToggle({
    Name = "Ativar Notificações de Saída e Entrada dos Jogadores",
    Default = false,
    Callback = function(Value)
        notifyPlayers = Value
    end
})

game.Players.PlayerAdded:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) entrou no servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Entrada de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)

game.Players.PlayerRemoving:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) saiu do servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Saída de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)

local Section = Tab:AddSection({
	Name = "Bebe que Segue Jogador"
})

local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local followToggle = false
local originalCFrame

-- Função para suavizar a movimentação até o jogador alvo
local function smoothFollow(targetHumanoidRootPart)
    local bodyPosition = Instance.new("BodyPosition")
    bodyPosition.MaxForce = Vector3.new(1e6, 1e6, 1e6)
    bodyPosition.P = 1e5
    bodyPosition.D = 1e3
    bodyPosition.Position = targetHumanoidRootPart.Position + Vector3.new(1, 0, 0) -- Gruda na lateral direita
    bodyPosition.Parent = LocalPlayer.Character.HumanoidRootPart

    task.wait(0.5) -- Aguarda até o personagem se alinhar

    -- Após o alinhamento, cria o Weld
    local weld = Instance.new("Weld")
    weld.Part0 = LocalPlayer.Character.HumanoidRootPart
    weld.Part1 = targetHumanoidRootPart
    weld.C0 = CFrame.new(0.1, 0, 0) -- Ajusta a posição para grudar na lateral direita
    weld.Parent = LocalPlayer.Character.HumanoidRootPart

    bodyPosition:Destroy()
end

-- Função para conectar ao jogador e executar comandos
local function connectToPlayer(playerName)
    for _, player in pairs(Players:GetPlayers()) do
        if string.find(player.Name:lower(), playerName:lower()) and player ~= LocalPlayer then
            local character = player.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                -- Salvar posição e orientação originais
                originalCFrame = LocalPlayer.Character.HumanoidRootPart.CFrame

                -- Suavizar movimentação até o alvo
                smoothFollow(character.HumanoidRootPart)

                -- Executar funções adicionais ao ativar
                local args1 = { "CharacterFollowSpawnPlayer", "BabyBoy" }
                ReplicatedStorage.RE:FindFirstChild("1Bab1yFollo1w"):FireServer(unpack(args1))

                local args2 = { "CharacterSizeDown", 4 }
                ReplicatedStorage.RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args2))

                return true
            end
        end
    end
    return false
end

-- Função para desconectar e voltar ao normal
local function disconnect()
    if originalCFrame then
        -- Remover conexões (Welds) e voltar ao normal
        for _, weld in pairs(LocalPlayer.Character.HumanoidRootPart:GetChildren()) do
            if weld:IsA("Weld") then
                weld:Destroy()
            end
        end

        -- Voltar à posição original
        LocalPlayer.Character.HumanoidRootPart.CFrame = originalCFrame

        -- Executar funções adicionais ao desativar
        local args1 = { "DeleteFollowCharacter" }
        ReplicatedStorage.RE:FindFirstChild("1Bab1yFollo1w"):FireServer(unpack(args1))

        local args2 = { "CharacterSizeUp", 1 }
        ReplicatedStorage.RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args2))

        originalCFrame = nil
    end
end

local playerName = ""

Tab:AddTextbox({
    Name = "Digite o Nome do Jogador",
    Default = "",
    TextDisappear = true,
    Callback = function(input)
        playerName = input
    end
})

Tab:AddToggle({
    Name = "Ativar",
    Default = false,
    Callback = function(value)
        followToggle = value

        if followToggle then
            if playerName ~= "" and connectToPlayer(playerName) then
                -- Sucesso ao seguir o jogador
            else
                followToggle = false
                -- Falha ao encontrar o jogador
            end
        else
            disconnect()
            -- Jogador desconectado
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Pull Player",
	Icon = "rbxassetid://10734920149",
	PremiumOnly = false
})


-- Variáveis para armazenar dados
local fakeIP = ""
local playerName = ""

-- Gerador de Fake IP
local function generateFakeIP()
    fakeIP = playerName .. "'s IP: " .. math.random(0, 255) .. "." .. math.random(0, 255) .. "." .. math.random(0, 255) .. "." .. math.random(0, 255)
    OrionLib:MakeNotification({
        Name = "IP Capturado",
        Content = fakeIP,
        Image = "rbxassetid://4483345998",
        Time = 5
    })
end

-- Caixa de Texto para Inserir o Nome do Jogador
Tab:AddTextbox({
    Name = "Nome do Jogador",
    Default = "",
    TextDisappear = false,
    Callback = function(Value)
        if #Value <= 20 then
            playerName = Value
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "O nome não pode ter mais de 20 caracteres!",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

-- Botão para Gerar IP
Tab:AddButton({
    Name = "Gerar Ip",
    Callback = function()
        if playerName ~= "" then
            generateFakeIP()
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Por favor, insira um nome de jogador.",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

-- Botão para Copiar o IP
Tab:AddButton({
    Name = "Copiar IP",
    Callback = function()
        if fakeIP ~= "" then
            setclipboard(fakeIP) -- Copia para a área de transferência
            OrionLib:MakeNotification({
                Name = "Copiado",
                Content = "O IP foi copiado para a área de transferência.",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Nenhum IP foi gerado ainda.",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})


local selectedPlayer = nil

local function getPlayerId(player)
    return player.UserId
end

local function getJoinDate(player)
    return player.AccountAge
end

local function copyName(player)
    setclipboard(player.Name)
end

local function createESP(player)
    local esp = Instance.new("Highlight")
    esp.Parent = player.Character
    esp.Adornee = player.Character
    esp.FillColor = Color3.new(1, 0, 0)
    esp.FillTransparency = 0.5
    esp.OutlineColor = Color3.new(1, 1, 1)
    esp.OutlineTransparency = 0
end

local function updateDropdown()
    local players = game:GetService("Players"):GetPlayers()
    local playerNames = {}
    for _, player in ipairs(players) do
        table.insert(playerNames, player.Name)
    end
    return playerNames
end

Tab:AddDropdown({
    Name = "Players",
    Default = "",
    Options = updateDropdown(),
    Callback = function(value)
        selectedPlayer = game:GetService("Players"):FindFirstChild(value)
    end
})

Tab:AddButton({
    Name = "Player id",
    Callback = function()
        if selectedPlayer then
            OrionLib:MakeNotification({
                Name = "Player ID",
                Content = "ID: " .. getPlayerId(selectedPlayer),
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

Tab:AddButton({
    Name = "JoinDate (see when the player entered the game)",
    Callback = function()
        if selectedPlayer then
            OrionLib:MakeNotification({
                Name = "Join Date",
                Content = "Account Age: " .. getJoinDate(selectedPlayer) .. " days",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

Tab:AddButton({
    Name = "Copyname",
    Callback = function()
        if selectedPlayer then
            copyName(selectedPlayer)
            OrionLib:MakeNotification({
                Name = "Copy Name",
                Content = "Name copied to clipboard",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Break Home",
	Icon = "rbxassetid://10723407389",
	PremiumOnly = false
})


local Section = Tab:AddSection({
    Name = "Select and Manage House"
})

-- Variável para armazenar o estado do loop
local toggles = { HouseLoop = false }

-- Variável para armazenar a casa selecionada
local selectedHouse = nil

-- Dropdown para selecionar a casa
Tab:AddDropdown({
    Name = "Target House",
    Options = {
        "Casa 7", "Casa 8", "Casa 9", "Casa 10", "Casa 11",
        "Casa 12", "Casa 13", "Casa 14", "Casa 15", "Casa 16",
        "Casa 17","Casa 18","Casa 19","Casa 20","Casa 21"
    },
    Callback = function(selectedOption)
        selectedHouse = tonumber(selectedOption:match("Casa (%d+)"))
        if selectedHouse then
            print("Casa selecionada: " .. selectedOption)
        else
            print("Erro ao selecionar a casa.")
        end
    end
})

-- Botão para iniciar o loop baseado na casa selecionada
Tab:AddButton({
    Name = "Start Selling and Picking House",
    Callback = function()
        if not selectedHouse then
            print("Por favor, selecione uma casa primeiro.")
            return
        end

        toggles.HouseLoop = true
        print("Loop iniciado para a Casa: " .. selectedHouse)

        spawn(function()
            while toggles.HouseLoop and task.wait(0.1) do
                local ReplicatedStorage = game:GetService("ReplicatedStorage")
                ReplicatedStorage.RE["1Gettin1gHous1e"]:FireServer("PickingCustomHouse", "015_House", selectedHouse)
                ReplicatedStorage.RE["1Player1sHous1eChoic1e"]:FireServer("PlayerSellHouse")
            end
        end)
    end
})

-- Botão para parar o loop
Tab:AddButton({
    Name = "Stop Selling and Picking House",
    Callback = function()
        if toggles.HouseLoop then
            toggles.HouseLoop = false
            print("Loop parado.")
        else
            print("Nenhum loop está ativo.")
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Visual",
	Icon = "rbxassetid://10723346959",
	PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "ESP"
})

local espEnabled = false -- Variável para rastrear o estado do ESP
local playerConnections = {} -- Tabela para rastrear conexões dos jogadores

-- Função para criar o ESP
local function createESP(player)
    if player == game.Players.LocalPlayer then return end -- Ignorar o jogador local

    local function setupESP(character)
        if not character:FindFirstChild("Head") then
            character:WaitForChild("Head") -- Garante que a cabeça exista
        end
        if not character:FindFirstChildOfClass("Humanoid") then
            character:WaitForChild("Humanoid") -- Garante que o humanoide exista
        end

        -- Criando o Highlight
        local highlight = Instance.new("Highlight")
        highlight.Name = "ESP_Highlight"
        highlight.FillColor = Color3.new(1, 1, 1) -- Branco
        highlight.FillTransparency = 0.5 -- Transparência no contorno
        highlight.OutlineTransparency = 0 -- Contorno sólido
        highlight.Parent = character

        -- Tornando o jogador branco transparente
        for _, part in pairs(character:GetDescendants()) do
            if part:IsA("BasePart") and part.Transparency < 1 then
                part:SetAttribute("OriginalTransparency", part.Transparency) -- Salva a transparência original
                part.Transparency = 0.5 -- Define transparência para 50%
                part.Color = Color3.new(1, 1, 1) -- Deixa a cor branca
            end
        end

        -- Criando o BillboardGui
        local billboardGui = Instance.new("BillboardGui")
        billboardGui.Name = "ESP_Info"
        billboardGui.Size = UDim2.new(0, 150, 0, 30)
        billboardGui.StudsOffset = Vector3.new(0, 3, 0)
        billboardGui.Adornee = character:FindFirstChild("Head")
        billboardGui.AlwaysOnTop = true
        billboardGui.Parent = character

        -- Criando o Texto
        local textLabel = Instance.new("TextLabel")
        textLabel.Size = UDim2.new(1, 0, 1, 0)
        textLabel.BackgroundTransparency = 1
        textLabel.TextColor3 = Color3.new(1, 1, 1)
        textLabel.TextStrokeTransparency = 1 -- Remover o contorno preto
        textLabel.TextScaled = true
        textLabel.Font = Enum.Font.SourceSans -- Fonte alterada para SourceSans
        textLabel.Parent = billboardGui

        -- Atualizar as informações imediatamente
        local function updateInfo()
            if character and character:FindFirstChild("Humanoid") and character.PrimaryPart then
                local humanoid = character:FindFirstChildOfClass("Humanoid")
                local distance = math.floor((character.PrimaryPart.Position - game.Players.LocalPlayer.Character.PrimaryPart.Position).Magnitude)
                textLabel.Text = string.format("%s | Vida: %d | Distância: %d", player.Name, math.floor(humanoid.Health), distance)
            end
        end

        -- Atualizar as informações em loop
        task.spawn(function()
            while espEnabled and character and character:FindFirstChild("Humanoid") do
                updateInfo()
                task.wait(1)
            end
        end)

        -- Atualizar imediatamente ao criar
        updateInfo()
    end

    if player.Character then
        setupESP(player.Character)
    end

    player.CharacterAdded:Connect(function(character)
        if espEnabled then
            setupESP(character)
        end
    end)
end

-- Função para remover o ESP de um jogador
local function removeESP(player)
    if player.Character then
        -- Remover Highlight
        if player.Character:FindFirstChild("ESP_Highlight") then
            player.Character.ESP_Highlight:Destroy()
        end
        -- Remover BillboardGui
        if player.Character:FindFirstChild("ESP_Info") then
            player.Character.ESP_Info:Destroy()
        end
        -- Restaurar transparência original
        for _, part in pairs(player.Character:GetDescendants()) do
            if part:IsA("BasePart") and part:GetAttribute("OriginalTransparency") then
                part.Transparency = part:GetAttribute("OriginalTransparency") -- Restaurar transparência
                part:SetAttribute("OriginalTransparency", nil) -- Remover atributo
            end
        end
    end
end

-- Função para ativar o ESP
local function enableESP()
    espEnabled = true
    for _, player in pairs(game.Players:GetPlayers()) do
        -- Criar ESP imediatamente quando o jogador já está no jogo
        if player.Character then
            createESP(player)
        end
        -- Conexão para futuros personagens do jogador
        playerConnections[player] = player.CharacterAdded:Connect(function(character)
            if espEnabled then
                createESP(player)
            end
        end)
    end

    -- Conexão para novos jogadores
    playerConnections["PlayerAdded"] = game.Players.PlayerAdded:Connect(function(player)
        if espEnabled then
            -- Criar ESP imediatamente para novos jogadores
            if player.Character then
                createESP(player)
            end
            -- Conectar ao evento CharacterAdded
            playerConnections[player] = player.CharacterAdded:Connect(function(character)
                createESP(player)
            end)
        end
    end)
end

-- Função para desativar o ESP
local function disableESP()
    espEnabled = false
    for _, player in pairs(game.Players:GetPlayers()) do
        removeESP(player)
        -- Desconectar eventos associados ao jogador
        if playerConnections[player] then
            playerConnections[player]:Disconnect()
            playerConnections[player] = nil
        end
    end

    -- Desconectar o evento de novos jogadores
    if playerConnections["PlayerAdded"] then
        playerConnections["PlayerAdded"]:Disconnect()
        playerConnections["PlayerAdded"] = nil
    end
end

-- Toggle para ativar/desativar o ESP
Tab:AddToggle({
    Name = "ESP",
    Default = false,
    Callback = function(state)
        if state then
            enableESP()
        else
            disableESP()
        end
    end
})

print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "Créditos",
	Icon = "rbxassetid://10709752405",
	PremiumOnly = false
})


Tab:AddParagraph("Update Log 📄","<font color='rgb(66, 3, 255)'>Novos Tabs,Bugs Corrigidos, funções Nova,Codigo Testando e Revisando Melhor Desempenho.</font>")

local Section = Tab:AddSection({
	Name = "Créditos"
})

Tab:AddParagraph("Créditos 📃","Créditos: <font color='rgb(66, 3, 255)'>Noly, sr_greg81, ADMbrookhaven</font>")
