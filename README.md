local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("KAJOK HUB -- ฟรีไอควาย", "DarkTheme")
local Tab = Window:NewTab("ABOUT")
local Section = Tab:NewSection("SCRIPT //HACK// MADE BY เทพ บน")
local Section = Tab:NewSection("สคริบ ฟรีไอโง่ แจกพ่องตาย")
Section:NewKeybind("ALTย่อไอสัส", "ย่อไอสัส", Enum.KeyCode.LeftAlt, function()
	Library:ToggleUI()
end)

----------------FUNCTION--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

local Tab = Window:NewTab("FUNCTION")

local Section = Tab:NewSection("FLY")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local player = Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
local flying = false
local flySpeed = 200

Section:NewSlider("Fly speed", "SliderInfo", 1000, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    flySpeed = s
end)


Section:NewButton("Press to fly", "บินไงไอ้โง่", function()
    print("Fly")
    flying = not flying
        while flying do
            local moveDir = Vector3.new(0, 0, 0)
            local cam = workspace.CurrentCamera

            if UserInputService:IsKeyDown(Enum.KeyCode.W) then
                moveDir = moveDir + cam.CFrame.LookVector
            end
            if UserInputService:IsKeyDown(Enum.KeyCode.S) then
                moveDir = moveDir - cam.CFrame.LookVector
            end
            if UserInputService:IsKeyDown(Enum.KeyCode.A) then
                moveDir = moveDir - cam.CFrame.RightVector
            end
            if UserInputService:IsKeyDown(Enum.KeyCode.D) then
                moveDir = moveDir + cam.CFrame.RightVector
            end
            if UserInputService:IsKeyDown(Enum.KeyCode.RightShift) then
                moveDir = moveDir + Vector3.new(0, 1, 0)
            end
            if UserInputService:IsKeyDown(Enum.KeyCode.RightControl) then
                moveDir = moveDir - Vector3.new(0, 1, 0)
            end
            if moveDir.Magnitude > 0 then
                moveDir = moveDir.Unit * flySpeed
            end

            humanoidRootPart.Velocity = moveDir
            RunService.RenderStepped:Wait()
        end
end)


local Section = Tab:NewSection("WALK SPEED")
Section:NewSlider("WalkSpeed", "Normal = 20", 300, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
Section:NewTextBox("WALK SPEED", "WALK SPEED", function(s)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
	print(s)
end)


local Section = Tab:NewSection("JUMP POWER")
Section:NewSlider("JumpPower", "Normal = 50", 300, 0, function(a) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = a
end)
Section:NewTextBox("JUMP POWER", "JUMP POWER", function(a)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = a
	print(a)
end)

local Section = Tab:NewSection("Auto click//Click race")
Section:NewToggle("On", "ToggleInfo", function(state)
    if state then
        print("Toggle On")
        _G.auto = true


        while _G.auto do
        game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("ClickService"):WaitForChild("RF"):WaitForChild("Click"):InvokeServer()
        wait(0.01)

        end
    else
        print("Toggle Off")
        _G.auto = false

        while _G.auto do
        game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Knit"):WaitForChild("Services"):WaitForChild("ClickService"):WaitForChild("RF"):WaitForChild("Click"):InvokeServer()

         wait(0.01)

        end
    end
end)

--------ARISE CROSSOVER-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
local Tab = Window:NewTab("ARISE CROSSOVER")

local Section = Tab:NewSection("AUTO ATTACK/ไม่เสร็จ")
Section:NewToggle("ON", "AUTO ARISE", function(state)
    if state then
        print("Toggle On")
        _G.auto = true


        while _G.auto do
        local args = {
    [1] = {
        [1] = {
            ["PetPos"] = {
                ["RedAntfd03042"] = Vector3.new(-2947.45703125, 61.77288055419922, -2090.490478515625),
                ["RedAnt2b45783"] = Vector3.new(-2941.8896484375, 60.94636535644531, -2082.3115234375),
                ["RedAnte0a97c7"] = Vector3.new(-2952.690185546875, 61.60506057739258, -2090.349853515625),
                ["RedAnt317bffc"] = Vector3.new(-2943.25732421875, 61.51674270629883, -2087.36474609375)
            },
            ["AttackType"] = "All",
            ["Event"] = "Attack",
            ["Enemy"] = "917be04d57064a17863e7133b799d90c"
        },
        [2] = "\t"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))

        



       
        wait(0.1)

        end
    else
        print("Toggle Off")
        _G.auto = false


        while _G.auto do
        local args = {
    [1] = {
        [1] = {
            ["PetPos"] = {
                ["RedAntfd03042"] = Vector3.new(-2947.45703125, 61.77288055419922, -2090.490478515625),
                ["RedAnt2b45783"] = Vector3.new(-2941.8896484375, 60.94636535644531, -2082.3115234375),
                ["RedAnte0a97c7"] = Vector3.new(-2952.690185546875, 61.60506057739258, -2090.349853515625),
                ["RedAnt317bffc"] = Vector3.new(-2943.25732421875, 61.51674270629883, -2087.36474609375)
            },
            ["AttackType"] = "All",
            ["Event"] = "Attack",
        },
        [2] = "\t"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))

        


       
        wait(0.1)

        end
        

    end
end)

local Section = Tab:NewSection("AUTO ARISE/ไม่เสร็จ")
Section:NewToggle("On", "ToggleInfo", function(state)
    _G.auto = true

    if state then
        print("Toggle On")

        _G.Auto = true

        while _G.Auto do
        local args = {
    [1] = {
        [1] = {
            ["Event"] = "EnemyCapture",
            ["Enemy"] = "917be04d57064a17863e7133b799d90c"
        },
        [2] = "\4"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))






        wait(0.1)

        end



    else
        print("Toggle Off")
         _G.Auto = false

        while _G.Auto do
        local args = {
    [1] = {
        [1] = {
            ["Event"] = "EnemyCapture",
            ["Enemy"] = "917be04d57064a17863e7133b799d90c"
        },
        [2] = "\4"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))

       


        wait(0.1)

        end
    end
end)

local Section = Tab:NewSection("AUTO CLICK/ไม่เสร็จ" )
Section:NewToggle("On", "ToggleInfo", function(state)
    _G.auto = true

    if state then
        print("Toggle On")

        _G.Auto = true

        while _G.Auto do
        local args = {
    [1] = {
        [1] = {
            ["Event"] = "PunchAttack",

        },
        [2] = "\4"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))




        wait(0.1)

        end



    else
        print("Toggle Off")
         _G.Auto = false

        while _G.Auto do
        local args = {
    [1] = {
        [1] = {
            ["Event"] = "PunchAttack",

        },
        [2] = "\4"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))



       


        wait(0.1)

        end
    end
end)







local Section = Tab:NewSection("CODE" )
Section:NewButton("REDEEM ALLCODE", "ButtonInfo", function()
    print("Clicked")
    local codes = {"RUNES", "DRAGONBLUE", "UPDATE", "BETA"}
for _, autocode in ipairs(codes) do
    local args = {
        [1] = {
            [1] = {
                ["Event"] = "UseCode",
                ["Code"] = autocode
            },
            [2] = "\n"
        }
    }
    game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))
    task.wait(0.5)
end
    
end)


    



local Section = Tab:NewSection("TELEPORT")
--sololeveling--
    Section:NewButton("Teleport to Solo Leveling", "Warp", function()

player.Character:BreakJoints()

local args = {
    [1] = {
        [1] = {
            ["Event"] = "ChangeSpawn",
            ["Spawn"] = "SoloWorld"
        },
        [2] = "\n"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))


end)
--naruto--
    Section:NewButton("Teleport to Naruto", "Warp", function()

player.Character:BreakJoints()

local args = {
    [1] = {
        [1] = {
            ["Event"] = "ChangeSpawn",
            ["Spawn"] = "NarutoWorld"
        },
        [2] = "\n"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))



end)
--onepiece--
Section:NewButton("Teleport to One Piece", "Warp", function()

 player.Character:BreakJoints()
local args = {
    [1] = {
        [1] = {
            ["Event"] = "ChangeSpawn",
            ["Spawn"] = "OPWorld"
        },
        [2] = "\n"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))

end)
--bleach--
Section:NewButton("Teleport to Bleach", "Warp", function()

player.Character:BreakJoints()

local args = {
    [1] = {
        [1] = {
            ["Event"] = "ChangeSpawn",
            ["Spawn"] = "BleachWorld"
        },
        [2] = "\n"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))

end)
--blackclover--
Section:NewButton("Teleport to Black Clover", "Warp", function()

player.Character:BreakJoints()
local args = {
    [1] = {
        [1] = {
            ["Event"] = "ChangeSpawn",
            ["Spawn"] = "BCWorld"
        },
        [2] = "\n"
    }
}

game:GetService("ReplicatedStorage"):WaitForChild("BridgeNet2"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))

end)

Section:NewButton("Teleport to Ant Island", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(10, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(3934.61816, 59.1383743, 3200.93066, 0.798636198, 5.10940197e-08, 0.601814091, -2.59595225e-07, 1, 2.59595311e-07, -0.601814091, -3.63550299e-07, 0.798636198)}):Play()


    

end)


-----------------BLOXFRUIT-------------------------------------------------------------------------------------------------------------------------------------------------------

local Tab = Window:NewTab("BLOXFRUIT")
local Section = Tab:NewSection("Auto Farm[ยังไม่เสร็จ]")



local Section = Tab:NewSection("Auto Equip")
local Weaponlist = {}
local Weapon = nil
for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end
Section:NewDropdown("select weapon", " ", Weaponlist, function(currentOption)
    Weapon = currentOption
end)
Section:NewToggle("Auto Equip", " ", function(a)
AutoEquiped = a
end)
spawn(function()
while wait() do
if AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end
end)

local Section = Tab:NewSection("TELEPORT TO ISLAND")
Section:NewButton("STARTER ISLAND", "1", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(940.701477, 16.5515461, 1426.72595, -0.138429299, 8.69872068e-08, 0.9903723, 4.34884306e-09, 1, -8.72249686e-08, -0.9903723, -7.76751818e-09, -0.138429299)}):Play()
end)

Section:NewButton("MIDDLE ISLAND", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(-628.089111, 7.88705158, 1573.77283, 0.227064386, -7.6093464e-08, 0.973879755, 1.88153386e-08, 1, 7.37474721e-08, -0.973879755, 1.57845292e-09, 0.227064386)}):Play()   
end)
Section:NewButton("PIRATE ISLAND", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(-1195.09143, 4.7866621, 3808.15234, -0.907208323, -4.49012294e-09, -0.420681685, 2.25225865e-08, 1, -5.92438454e-08, 0.420681685, -6.32213499e-08, -0.907208323)}):Play()
end)

Section:NewButton("MARINE ISLAND", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(-2593.80737, 6.92355728, 2058.55054, -0.261095673, 1.2797048e-07, 0.965312898, 5.46200702e-08, 1, -1.17795395e-07, -0.965312898, 2.19695924e-08, -0.261095673)}):Play()
end)

Section:NewButton("DESERT ISLAND", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(895.359131, 3.43647742, 4105.71533, 0.989967942, -5.30099342e-08, 0.141291961, 5.55059998e-08, 1, -1.37249785e-08, -0.141291961, 2.1429841e-08, 0.989967942)}):Play()
end)

Section:NewButton("VOLCANO ISLAND", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(-5236.35791, 8.62558937, 8448.75684, 0.787198603, 2.16337326e-09, -0.616699576, 3.66238311e-08, 1, 5.02572135e-08, 0.616699576, -6.21483096e-08, 0.787198603)}):Play()
end)

Section:NewButton("MARINE FORTRESS", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(-4831.71289, 20.6870441, 4395.32275, -0.0721002072, -8.78489175e-08, -0.997397423, -3.22146114e-08, 1, -8.57494058e-08, 0.997397423, 2.59482213e-08, -0.0721002072)}):Play()
end)

Section:NewButton("SKYLAND", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(30, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(-4610.0874, 872.577087, -1672.0033, 0.825689495, -1.5591711e-08, 0.564124823, 1.01532747e-08, 1, 1.27777735e-08, -0.564124823, -4.82275864e-09, 0.825689495)}):Play()
end)

Section:NewButton("COLOSSEUM", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(-1448.90808, 7.32245731, -2834.10107, -0.903441608, 1.32113515e-10, -0.428711146, -5.72693537e-09, 1, 1.2376784e-08, 0.428711146, 1.36369023e-08, -0.903441608)}):Play()
end)

Section:NewButton("UNDERWATER CITY", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(4049.62964, 31.1530895, -1810.81946, 0.914685786, -2.79064172e-09, -0.404165715, 9.31737021e-10, 1, -4.79604045e-09, 0.404165715, 4.01029387e-09, 0.914685786)}):Play()
end)

Section:NewButton("PRISON ISLAND", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(4842.05469, 5.686903, 739.865906, -0.365995079, -6.2209196e-08, 0.930616796, -6.74692657e-08, 1, 4.03128126e-08, -0.930616796, -4.80337441e-08, -0.365995079)}):Play()
end)

Section:NewButton("WATER7", "ButtonInfo", function()
    print("Clicked")
    local TweenService = game:GetService("TweenService")

local Tw = TweenService:Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(15, Enum.EasingStyle.Linear, Enum.EasingDirection.Out,0,false,0), 
{CFrame = CFrame.new(5049.28027, 1.53604579, 4055.02344, -0.999747694, -5.08908382e-09, -0.0224620812, -4.17041113e-09, 1, -4.09456611e-08, 0.0224620812, -4.08416518e-08, -0.999747694)}):Play()
end)


-----------------PLAYER--------------------------------------------------------------------------------------------------------------------------------------------

local Tab = Window:NewTab("PLAYER")
local Section = Tab:NewSection("TP TO PLAYER")
Plr = {}
for i,v in pairs(game:GetService("Players"):GetChildren()) do
    
    table.insert(Plr,v.Name)
end
local drop = Section:NewDropdown("SELECT PLAYER","TP TO PLAYER", Plr,function(t)
    PlayerTP = t
end)
Section:NewButton("TP","TP", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[PlayerTP].Character.HumanoidRootPart.CFrame
end)
Section:NewButton("RESFRESH PLAYER","REFRESH PLAYER", function()
    Plr = {}
    for i,v in pairs(game:GetService("Players"):GetChildren()) do
        table.insert(Plr,v.Name) 
    end
  drop:Refresh(Plr)
end)
Section:NewToggle("AUTO TP","",function(t)
_G.TPPlayer = t
while _G.TPPlayer do wait()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[PlayerTP].Character.HumanoidRootPart.CFrame
end
end)



local Section = Tab:NewSection("ESP PLAYER")
Section:NewButton("ESP ไอควายปิดไม่ได้", "ESP ไอควยปิดไม่ได้", function()
    print("Clicked")
    while wait() do
     pcall(function()
       for i,v in pairs(game.Players:GetChildren()) do
            if not v.Character.Head:FindFirstChild("ESP") then
                local BillboardGui = Instance.new("BillboardGui")
                local TextLabel = Instance.new("TextLabel")
                BillboardGui.Parent = v.Character.Head
                BillboardGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
                BillboardGui.Active = true
                BillboardGui.Name = "ESP"
                BillboardGui.AlwaysOnTop = true
                BillboardGui.LightInfluence = 1.000
                BillboardGui.Size = UDim2.new(0, 200, 0, 50)
                BillboardGui.StudsOffset = Vector3.new(0, 2.5, 0)
                TextLabel.Parent = BillboardGui
                TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                TextLabel.BackgroundTransparency = 1.000
                TextLabel.Size = UDim2.new(0, 200, 0, 50)
                TextLabel.Font = Enum.Font.GothamBold
                TextLabel.Text = v.Name
                TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                TextLabel.TextScaled = true
                TextLabel.TextSize = 14.000
                TextLabel.TextStrokeTransparency = 0.000
                TextLabel.TextWrapped = true
            end
        end
    end) 
end


end)


local Tab = Window:NewTab("SETTING")
local Section = Tab:NewSection("Cframe, Position")
Section:NewButton("Click to copy Cframe", "Cframe of user", function()
    print("Copy success!")
    setclipboard(tostring(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame))
end)
Section:NewButton("Click to copy Position", "Postion of user", function()
    print("Copy success!")
    setclipboard(tostring(game.Players.LocalPlayer.Character.HumanoidRootPart.Position))
end)
