local VLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/vep1032/VepStuff/main/VL"))()
local s = VLib:Window("Pylwt Hub", "Multi Exploit", "PLT")
local ss = s:Tab("Main")
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
ss:Button("No Clip (Press B)",function()
pcall(loadstring(game:HttpGet("https://pastebin.com/raw/kt3Nxzw1")))
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
ss:Slider("Walk Speed",0,1000,16,function(t)
print(t)
end)
ss:Slider("Jump Power",0,1000,50,function(t)
print(t)
end)
ss:Label("- -Visual Section- -")
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
ss:Button("Force Field",function()
print("Pressed!")
end)
local ss = s:Tab("All Tools")
ss:Label("- -Here Are All The Tools We Have- -")
ss:Label("- -Some Might Not Work- -")
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
ss:Label("- -Guns- -")
ss:Button("Pistol",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/SeRxrgci", true))()
end)
ss:Button("AK-47",function()
    game:GetObjects("rbxassetid://149948769")[1].Parent=game.Players.LocalPlayer.Backpack
end)
ss:Label("- -Broken Stuff- -")
ss:Button("Rocket Spin",function() 
power = 1000 -- change this to make it more or less powerful
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
ss:Button("Clones",function()
    loadstring(game:GetObjects('rbxassetid://7339698872')[1].Source)() 
end)
ss:Button("Sword",function()
    game:GetObjects("rbxassetid://169934427")[1].Parent=game.Players.LocalPlayer.Backpack
end)
ss:Button("Swords",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/80juE2kw", true))()
end)
ss:Label("- -Avatar Forms- -")
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
local ss = s:Tab("Games")
ss:Label("- -Joine the game you want & Click the buttons below- -")
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
    loadstring(game:HttpGet('https://raw.githubusercontent.com/TrixAde/scripts/main/DaHood-DoomWare.lua', true))()
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
    loadstring(game:HttpGet("https://www.scriptblox.com/raw/Project-Meow_421"))()
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
ss:Label("- -None of the scripts above are mine- -")
local ss = s:Tab("Hubs")
ss:Label("- -These Are Hubs From Other People- -")

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
local ss = s:Tab("Credits")
ss:Label("Made By Tim")
ss:Label("Discord: @Pylwt#6567")
ss:Label("Stapchat: @tfr.p")
ss:Label("Server: .gg/QnbxmxMrJG")
ss:Label("Thank you for choosing Pylwt Hub!")
