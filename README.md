-- Delta IPA Provider Script
local StarterGui = game:GetService("StarterGui")

-- Show a popup on their screen
StarterGui:SetCore("SendNotification", {
    Title = "Delta IPA Found!",
    Text = "Check your chat/console for the link.",
    Duration = 8
})

-- The link to the official Delta GitHub Releases
local downloadLink = "https://github.com/deltarobloxexec/Delta/releases"

-- Print it so they can copy it from the console
print("====================================")
print("DELTA IPA DOWNLOAD LINK:")
print(downloadLink)
print("====================================")

-- Send it to the chat (so others see it too)
local chatEvents = game:GetService("ReplicatedStorage"):FindFirstChild("DefaultChatSystemChatEvents")
if chatEvents then
    chatEvents.SayMessageRequest:FireServer("Get Delta IPA here: " .. downloadLink, "All")
end
