-- General Phone & Game Helper Hub
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local UIListLayout = Instance.new("UIListLayout")
local Title = Instance.new("TextLabel")

ScreenGui.Parent = game.CoreGui
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
Frame.Position = UDim2.new(0.5, -110, 0.3, 0)
Frame.Size = UDim2.new(0, 220, 0, 220)
Frame.Active = true
Frame.Draggable = true

UIListLayout.Parent = Frame
UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
UIListLayout.Padding = UDim.new(0, 4)

Title.Parent = Frame
Title.Size = UDim2.new(1, 0, 0, 35)
Title.Text = "Phone & Game Fixes"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.BackgroundColor3 = Color3.fromRGB(40, 40, 40)

local function addFix(label, fixText)
    local btn = Instance.new("TextButton")
    btn.Parent = Frame
    btn.Size = UDim2.new(1, 0, 0, 35)
    btn.Text = label
    btn.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
    btn.TextColor3 = Color3.new(1, 1, 1)
    
    btn.MouseButton1Click:Connect(function()
        print("--- HELP: " .. label .. " ---")
        print(fixText)
        game:GetService("StarterGui"):SetCore("SendNotification", {
            Title = label,
            Text = "Solution sent to Console (F9)",
            Duration = 5
        })
    end)
end

-- Useful fixes for Phone users
addFix("Fix Lag / FPS Drop", "Lower Graphics to 1, turn off 'Bloom' in settings, and close background apps like Safari.")
addFix("Fix High Ping", "Toggle Airplane Mode on/off. If on iOS 26, ensure 'Private Relay' is OFF in iCloud settings.")
addFix("Phone Heating Up", "Remove phone case, lower screen brightness, and turn off 'Background App Refresh' in iPhone settings.")
addFix("Clear Game Cache", "Rejoin the game or clear 'Website Data' in Safari settings to speed up loading.")
addFix("Battery Saving", "Turn on 'Low Power Mode' and reduce Roblox volume to 0 (uses less CPU).")
