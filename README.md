_G.Toggle = false

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("Build A Boat For Treasure", "Serpent")

local MainTab = Window:NewTab("Main")

local MainSection = MainTab:NewSection("Main")

MainSection:NewToggle("Auto Gift Everyone", "buys everyone gifts!", function(state)
    if state then
        _G.Toggle = true
        while true do wait()
            if _G.Toggle == true then
                local ohString1 = "Gift4Group"
                local ohNumber2 = 1

                workspace.ItemBoughtFromShop:InvokeServer(ohString1, ohNumber2) 
            end
        end
    else
        _G.Toggle = false
    end
end)

MainSection:NewButton("Auto Farm", "auto farms gold!", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Build-A-Boat-For-Treasure/main/AutoFarm.lua", true))()
end)
