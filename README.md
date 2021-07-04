--[[
CREDITS

V3rm Thread: https://v3rmillion.net/showthread.php?pid=7756556#pid7756556
V3rm User: https://v3rmillion.net/member.php?action=profile&uid=1347047
UI Library Docs: https://xheptcofficial.gitbook.io/kavo-library/#creating-section
--]]

--Addition

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("A_Mystery#0110 | A Bizarre Journey", "DarkTheme")

--Windows
local Tab = Window:NewTab("Character")
local Fun = Window:NewTab("FunStuff")
local Other = Window:NewTab("Others")
local Info = Window:NewTab("Information")


--Cosmetics tab (Character)

local Cosmetics = Tab:NewSection("Walkspeed & Jumppower")

Cosmetics:NewKeybind("KeybindText", "KeybindInfo", Enum.KeyCode.RightAlt, function()
Library:ToggleUI()
end)

Cosmetics:NewSlider("WalkSpeed", "Set's users walkspeed", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
   game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

Cosmetics:NewSlider("JumpPower", "Set's users jumppower", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
   game.Players.LocalPlayer.Character.Humanoid.JumpPower = s
end)

Cosmetics:NewButton("SCR Outfit", "Gives SCR Outfit To LocalPlayer", function()
 game:GetService("ReplicatedStorage").SCR:FireServer()
 print("SCR Worn")
end)

Cosmetics:NewButton("Sakuya Earrape", "Spam this multiple times for earrape, once for normal music.", function()
   game:GetService("ReplicatedStorage").SakuyaIzayoi:FireServer()
end)

Cosmetics:NewButton("Weird Hat", "Gives the hat for One More Time.", function()
   game:GetService("ReplicatedStorage").OneMoreTime:FireServer()
end)

Cosmetics:NewButton("Gaster Effect", "Gives you a pretty cool Gaster effect.", function()
   local args = {
   [1] = true,
}
game:GetService("ReplicatedStorage").gastereffect:FireServer(unpack(args))
end)

Cosmetics:NewButton("Oni", "Gives the Oni outfit.", function()
game:GetService("ReplicatedStorage").Oni:FireServer()
end)

--Funstuff
local Fun = Fun:NewSection("FunStuff")

Fun:NewButton("Invis All", "Make people go invisible.", function()
  local plr = game.Players.LocalPlayer
local plrs = game.Players:getChildren()
local ch = plr.Character
for _, c in pairs(plrs) do
for i, v in pairs(c.Character:GetDescendants()) do
game.ReplicatedStorage.Transparency:FireServer(v, 1)
if v.Name == "Stand" then
   for _, p in pairs(v:GetDescendants()) do
game.ReplicatedStorage.Transparency:FireServer(0, 1)
end
end
end
end
end)

Fun:NewButton("God Mode", "Makes you unkillable.", function(god)
game:GetService("ReplicatedStorage").Stand:FireServer("GoldExperienceRequiemStand", math.huge, math.huge)
end)

--Others

local Stuff = Other:NewSection("Stuff")

Stuff:NewButton("Rejoin", "Rejoins", function()
   local tp = game:GetService("TeleportService")
local plr = game:GetService("Players").LocalPlayer
local Id = game.PlaceId
tp:Teleport(Id, p)
end)

Stuff:NewButton("Chat Translator", "Translates Chat.", function()
   loadstring(game:HttpGet("https://pastebin.com/raw/w5k3WvXH",true))()
end)

Stuff:NewButton("Remote Spy", "Feel free to use idk.", function()
   loadstring(game:HttpGet("https://pastebin.com/raw/s82p7XX6",true))()
end)

--Info

local Inf = Info:NewSection("Information")

Inf:NewButton("Commands (Console)", "Prints commands.", function()
print("!kill plr, !kill me, !kill others, !kill all")
print("!heal plr, !heal me, !heal others, !heal all")
print("!goto plr, !goto me, !goto others, !goto all")
print("!invis plr, !invis me, !invis others, !invis all")
print("!vis plr, !vis me, !vis others, !vis all")
print("!ghostify plr, !ghostify me, !ghostify others, !ghostify all")
print("!god me")
print("!explode plr")
print("!superexplode plr")
print("!void plr")
print("!fling plr")
print("!freeze plr, !freeze me, !freeze others, !freeze all")
print("!unfreeze plr, !unfreeze me, !unfreeze others, !unfreeze all")
print("!admin plr  Only gives plrs admin - heal plr, kill plr, invis plr, vis plr, ghostify plr, freeze plr,unfreeze plr")
print("note give player admin is slightly buggy.")
print("!crash NEEDS ROCKET LAUNCHER SPEC")
end)
