-- Starter UI
local WindUI = loadstring(game:HttpGet("https://github.com/Footagesus/WindUI/releases/latest/download/main.lua"))()

-- Create main window
local Window = WindUI:CreateWindow({
    Title = "XXĒ",
    Author = "zixxy",
    Size = UDim2.new(0, 520, 0, 420),
    Position = UDim2.new(0.5, -260, 0.5, -210),
    OpenButton = {
        Title = "Open UI",
        Enabled = true,
        Draggable = true,
    },
})

-- Tabs
local MainTab = Window:Tab({ Title = "Main", Icon = "home" })
local VisualTab = Window:Tab({ Title = "Visual", Icon = "eye" })
local MiscTab = Window:Tab({ Title = "Misc", Icon = "person-standing" })

-- Sections
local MainSection = MainTab:Section({ Title = "Main" })
local VisualSection = VisualTab:Section({ Title = "Visuals" })
local MiscSection = MiscTab:Section({ Title = "Misc" })

-- Example toggle
MainSection:Toggle({
    Title = "Admin Detect",
    Default = false,
    Callback = function(state)
        print("Admin Detect toggled:", state)
    end
})

-- Config system
local ConfigManager = Window.ConfigManager
local MyConfig = ConfigManager:CreateConfig("MyConfig")

-- Save config example
MyConfig:Save()

-- Load config example
MyConfig:Load()
