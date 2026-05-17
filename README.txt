Hello! Thanks for using my project KB Lib!

How to use:

1. Load the library

local KBLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/KiBenYT/KB-Lib/refs/heads/main/KB_lib"))()

2. Create a window

local Window = KBLib:CreateWindow("Any Name")

3. (OPTIONAL) Create a minimize button

Window:CreateMinimizeButton("Name")

OR

Janela:CreateMinimizeButton("Name", 1234567) -- The number must be an ID to a decal/image

4. Create a tab

local MainTab = Window:CreateTab("Main")

OR

local MainTab = Window:CreateTab("Main", 1234567) -- The number must be an ID to a decal/image

Questions:

How can i create a button?

MainTab:CreateButton("Print", function()
	print("Hello World!")
end)

How can i create a toggle?

MainTab:CreateToggle("Toggle Name", false, function(state) -- The second argument is the default state of the toggle
    if state then
        print("Toggle is ON")
    else
        print("Toggle is OFF")
    end
end)

How can i create a dropdown/list?

local items = {"Option 1", "Option 2", "Option 3"}

local MyDropdown = MainTab:CreateDropdown("Select Player", items, function(selectedOption)
    print("Selected: " .. selectedOption)
end)

OR

local MyDropdown = MainTab:CreateDropdown("Select Player", {"Option 1", "Option 2", "Option 3"}, function(selectedOption)
    print("Selected: " .. selectedOption)
end)

How can i refresh the dropdown/list?

local newItems = {"New Option A", "New Option B"}
MyDropdown:Refresh(newItems)

How can i send a notification?

KBLib:Notify("Title", "Your message here!", 3) -- The third argument is the duration of the notification

How can i create a slider?

MainTab:CreateSlider("Example", 10, 100, 50, function(value) -- The first argument is the min value, second is the max value, third is the default value
    local char = game.Players.LocalPlayer.Character
    local hum = char and char:FindFirstChildOfClass("Humanoid")
    if hum then
        hum.JumpPower = value
    end
end)

How can i create a text/label?

MainTab:CreateLabel("Developed by: KiBenBlox / KiBen_devv")

How can i update a label?

local StatusLabel = MainTab:CreateLabel("Waiting...")

-- Update it inside a button, event, or loop:
StatusLabel:UpdateText("OK")

How can i create a textbox?

MainTab:CreateTextBox("Text here...", function(textEntered, enterPressed) -- The first argument is the placeholder text
    if textEntered ~= "" then
        KBLib:Notify("TextBox", "Typed: " .. textEntered, 3)
    end
end)

How can i create a warning?

Window:Warn("Warning", "Are you sure?", function()
    print("Action confirmed by the player.")
end)

Developed with ❤️ by KiBenBlox / KiBen_devv
