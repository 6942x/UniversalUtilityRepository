Config = {
    api = "2bc06ccb-13d7-4450-9ace-d9fe981de37a", 
    service = "NovaService",
    provider = "NovaProvider"
}

local function main()
    loadstring(game:HttpGet("https://github.com/6942x/NovaHub/blob/main/NovaHub_AnimeFight"))()
end

if getgenv().RedExecutorKeySys then return end
getgenv().RedExecutorKeySys = true

local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")
local CoreGui = game:GetService("CoreGui")
local HttpService = game:GetService("HttpService")

local KeySystemData = {
    Name = "Nova Hub",
    Colors = {
        Background = Color3.fromRGB(15, 15, 20),
        Secondary = Color3.fromRGB(22, 22, 28),
        Accent = Color3.fromRGB(138, 43, 226),
        AccentHover = Color3.fromRGB(155, 65, 245),
        Border = Color3.fromRGB(138, 43, 226),
        Text = Color3.fromRGB(245, 245, 250),
        TextDim = Color3.fromRGB(160, 160, 170),
        Error = Color3.fromRGB(239, 68, 68),
        Success = Color3.fromRGB(34, 197, 94),
        Discord = Color3.fromRGB(88, 101, 242)
    },
    Service = "redexecutor",
    SilentMode = false,
    DiscordInvite = "https://discord.gg/GhhAMF7B",
    WebsiteURL = "https://yourwebsite.com/",
    FileName = "redexecutor/key.txt"
}

local function CreateObject(class, props)
    local obj = Instance.new(class)
    for prop, value in pairs(props) do 
        if prop ~= "Parent" then
            obj[prop] = value
        end
    end
    if props.Parent then
        obj.Parent = props.Parent
    end
    return obj
end

local function SmoothTween(obj, time, properties)
    local tween = TweenService:Create(obj, TweenInfo.new(time, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), properties)
    tween:Play()
    return tween
end

local ScreenGui = CreateObject("ScreenGui", {
    Name = "RedExecutorKeySystem", 
    Parent = CoreGui, 
    ResetOnSpawn = false,
    ZIndexBehavior = Enum.ZIndexBehavior.Sibling,
    DisplayOrder = 999
})

local Blur = CreateObject("Frame", {
    Name = "BlurBackground",
    Parent = ScreenGui,
    BackgroundColor3 = Color3.fromRGB(0, 0, 0),
    BackgroundTransparency = 0.3,
    BorderSizePixel = 0,
    Size = UDim2.new(1, 0, 1, 0),
    ZIndex = 1
})

local MainFrame = CreateObject("Frame", {
    Name = "MainFrame",
    Parent = ScreenGui,
    BackgroundColor3 = KeySystemData.Colors.Background,
    BorderSizePixel = 0,
    Position = UDim2.new(0.5, 0, 0.5, 0),
    AnchorPoint = Vector2.new(0.5, 0.5),
    Size = UDim2.new(0, 380, 0, 280),
    ClipsDescendants = true,
    ZIndex = 2
})
CreateObject("UICorner", {CornerRadius = UDim.new(0, 12), Parent = MainFrame})

local Glow = CreateObject("ImageLabel", {
    Name = "Glow",
    Parent = MainFrame,
    BackgroundTransparency = 1,
    Position = UDim2.new(0.5, 0, 0, -50),
    Size = UDim2.new(1, 100, 0, 100),
    AnchorPoint = Vector2.new(0.5, 0),
    Image = "rbxasset://textures/ui/GuiImagePlaceholder.png",
    ImageColor3 = KeySystemData.Colors.Accent,
    ImageTransparency = 0.8,
    ZIndex = 1
})

local BorderGlow = CreateObject("UIStroke", {
    Parent = MainFrame,
    Color = KeySystemData.Colors.Border,
    Thickness = 2,
    Transparency = 0.5
})

local TitleBar = CreateObject("Frame", {
    Name = "TitleBar",
    Parent = MainFrame,
    BackgroundTransparency = 1,
    Size = UDim2.new(1, 0, 0, 60),
    BorderSizePixel = 0,
    Position = UDim2.new(0, 0, 0, 0)
})

local Icon = CreateObject("Frame", {
    Name = "Icon",
    Parent = TitleBar,
    BackgroundColor3 = KeySystemData.Colors.Accent,
    Position = UDim2.new(0.5, 0, 0.5, 0),
    Size = UDim2.new(0, 40, 0, 40),
    AnchorPoint = Vector2.new(0.5, 0.5)
})
CreateObject("UICorner", {CornerRadius = UDim.new(0, 8), Parent = Icon})
CreateObject("UIStroke", {
    Parent = Icon,
    Color = KeySystemData.Colors.Border,
    Thickness = 2
})

local IconText = CreateObject("TextLabel", {
    Parent = Icon,
    BackgroundTransparency = 1,
    Size = UDim2.new(1, 0, 1, 0),
    Text = "N",
    Font = Enum.Font.GothamBold,
    TextColor3 = Color3.fromRGB(255, 255, 255),
    TextSize = 22
})

local Title = CreateObject("TextLabel", {
    Name = "Title",
    Parent = MainFrame,
    BackgroundTransparency = 1,
    Text = KeySystemData.Name,
    Position = UDim2.new(0.5, 0, 0, 70),
    Size = UDim2.new(0, 300, 0, 25),
    Font = Enum.Font.GothamBold,
    TextColor3 = KeySystemData.Colors.Text,
    TextSize = 18,
    TextXAlignment = Enum.TextXAlignment.Center,
    AnchorPoint = Vector2.new(0.5, 0)
})

local Subtitle = CreateObject("TextLabel", {
    Name = "Subtitle",
    Parent = MainFrame,
    BackgroundTransparency = 1,
    Text = "Enter your verification key",
    Position = UDim2.new(0.5, 0, 0, 95),
    Size = UDim2.new(0, 300, 0, 18),
    Font = Enum.Font.Gotham,
    TextColor3 = KeySystemData.Colors.TextDim,
    TextSize = 12,
    TextXAlignment = Enum.TextXAlignment.Center,
    AnchorPoint = Vector2.new(0.5, 0)
})

local KeyInput = CreateObject("TextBox", {
    Name = "KeyInput",
    Parent = MainFrame,
    BackgroundColor3 = KeySystemData.Colors.Secondary,
    Text = "",
    PlaceholderText = "Paste your key here...",
    Position = UDim2.new(0.5, 0, 0, 130),
    Size = UDim2.new(0, 320, 0, 42),
    Font = Enum.Font.Gotham,
    TextSize = 13,
    TextColor3 = KeySystemData.Colors.Text,
    PlaceholderColor3 = KeySystemData.Colors.TextDim,
    TextXAlignment = Enum.TextXAlignment.Left,
    AnchorPoint = Vector2.new(0.5, 0),
    ClipsDescendants = true,
    ClearTextOnFocus = false
})
CreateObject("UICorner", {CornerRadius = UDim.new(0, 8), Parent = KeyInput})
CreateObject("UIStroke", {
    Parent = KeyInput,
    Color = KeySystemData.Colors.Border,
    Thickness = 1.5,
    Transparency = 0.7
})
CreateObject("UIPadding", {
    Parent = KeyInput,
    PaddingLeft = UDim.new(0, 15),
    PaddingRight = UDim.new(0, 15)
})

local ButtonContainer = CreateObject("Frame", {
    Name = "ButtonContainer",
    Parent = MainFrame,
    BackgroundTransparency = 1,
    Position = UDim2.new(0.5, 0, 0, 185),
    Size = UDim2.new(0, 320, 0, 38),
    AnchorPoint = Vector2.new(0.5, 0)
})

local SubmitButton = CreateObject("TextButton", {
    Name = "ValidateButton",
    Parent = ButtonContainer,
    BackgroundColor3 = KeySystemData.Colors.Accent,
    BorderSizePixel = 0,
    Position = UDim2.new(0, 0, 0, 0),
    Size = UDim2.new(0.48, 0, 1, 0),
    Text = "✓ Verify",
    Font = Enum.Font.GothamBold,
    TextSize = 14,
    TextColor3 = Color3.fromRGB(255, 255, 255),
    AutoButtonColor = false
})
CreateObject("UICorner", {CornerRadius = UDim.new(0, 8), Parent = SubmitButton})

local GetKeyButton = CreateObject("TextButton", {
    Name = "GetKeyButton",
    Parent = ButtonContainer,
    BackgroundColor3 = KeySystemData.Colors.Secondary,
    BorderSizePixel = 0,
    Position = UDim2.new(0.52, 0, 0, 0),
    Size = UDim2.new(0.48, 0, 1, 0),
    Text = "🔑 Get Key",
    Font = Enum.Font.GothamBold,
    TextSize = 14,
    TextColor3 = KeySystemData.Colors.Text,
    AutoButtonColor = false
})
CreateObject("UICorner", {CornerRadius = UDim.new(0, 8), Parent = GetKeyButton})
CreateObject("UIStroke", {
    Parent = GetKeyButton,
    Color = KeySystemData.Colors.Border,
    Thickness = 1.5,
    Transparency = 0.7
})

local DiscordButton = CreateObject("TextButton", {
    Name = "DiscordButton",
    Parent = MainFrame,
    BackgroundColor3 = KeySystemData.Colors.Discord,
    Position = UDim2.new(0.5, 0, 0, 235),
    Size = UDim2.new(0, 320, 0, 35),
    Text = "💬 Join Discord",
    Font = Enum.Font.GothamBold,
    TextSize = 13,
    TextColor3 = Color3.fromRGB(255, 255, 255),
    AutoButtonColor = false,
    AnchorPoint = Vector2.new(0.5, 0)
})
CreateObject("UICorner", {CornerRadius = UDim.new(0, 8), Parent = DiscordButton})

local StatusLabel = CreateObject("TextLabel", {
    Name = "StatusLabel",
    Parent = ScreenGui,
    BackgroundColor3 = KeySystemData.Colors.Secondary,
    Position = UDim2.new(0.5, 0, 0.88, 0),
    Size = UDim2.new(0, 0, 0, 45),
    Font = Enum.Font.GothamBold,
    Text = "",
    TextColor3 = Color3.fromRGB(255, 255, 255),
    TextSize = 14,
    TextXAlignment = Enum.TextXAlignment.Center,
    AnchorPoint = Vector2.new(0.5, 0),
    Transparency = 1,
    ZIndex = 5
})
CreateObject("UICorner", {CornerRadius = UDim.new(0, 10), Parent = StatusLabel})
CreateObject("UIPadding", {
    Parent = StatusLabel,
    PaddingLeft = UDim.new(0, 20),
    PaddingRight = UDim.new(0, 20)
})
CreateObject("UIStroke", {
    Parent = StatusLabel,
    Color = Color3.fromRGB(255, 255, 255),
    Thickness = 1,
    Transparency = 0.85
})

local function ShowStatusMessage(text, bgColor)
    StatusLabel.Text = text
    StatusLabel.BackgroundColor3 = bgColor
    StatusLabel.UIStroke.Color = bgColor
    
    SmoothTween(StatusLabel, 0.3, {
        Size = UDim2.new(0, 350, 0, 45),
        Transparency = 0
    })
    
    local textLabel = StatusLabel
    SmoothTween(textLabel, 0.3, {TextTransparency = 0})
    SmoothTween(StatusLabel.UIStroke, 0.3, {Transparency = 0.85})
    
    task.spawn(function()
        task.wait(3.5)
        if StatusLabel.Text == text then
            SmoothTween(StatusLabel, 0.4, {
                Size = UDim2.new(0, 0, 0, 45),
                Transparency = 1
            })
            SmoothTween(textLabel, 0.4, {TextTransparency = 1})
            SmoothTween(StatusLabel.UIStroke, 0.4, {Transparency = 1})
        end
    end)
end

local function AddHoverEffect(button, hoverColor)
    local originalColor = button.BackgroundColor3
    
    button.MouseEnter:Connect(function()
        SmoothTween(button, 0.2, {
            BackgroundColor3 = hoverColor or KeySystemData.Colors.AccentHover
        })
    end)
    
    button.MouseLeave:Connect(function()
        SmoothTween(button, 0.2, {
            BackgroundColor3 = originalColor
        })
    end)
end

AddHoverEffect(SubmitButton, KeySystemData.Colors.AccentHover)
AddHoverEffect(GetKeyButton, Color3.fromRGB(30, 30, 38))
AddHoverEffect(DiscordButton, Color3.fromRGB(100, 113, 255))

KeyInput.Focused:Connect(function()
    SmoothTween(KeyInput.UIStroke, 0.2, {
        Color = KeySystemData.Colors.Accent, 
        Transparency = 0.3
    })
end)

KeyInput.FocusLost:Connect(function()
    SmoothTween(KeyInput.UIStroke, 0.2, {
        Color = KeySystemData.Colors.Border, 
        Transparency = 0.7
    })
end)

local function openGetKey()
    local JunkieKeySystem = loadstring(game:HttpGet("https://junkie-development.de/sdk/JunkieKeySystem.lua"))()
    
    local API_KEY = Config.api
    local PROVIDER = Config.provider
    local SERVICE = Config.service
    
    local link = JunkieKeySystem.getLink(API_KEY, PROVIDER, SERVICE)
    if link then
        if setclipboard then
            setclipboard(link)
            ShowStatusMessage("✓ Link copied to clipboard!", KeySystemData.Colors.Success)
        else
            ShowStatusMessage(link, KeySystemData.Colors.Success)
        end
    else
        ShowStatusMessage("✗ Failed to generate link", KeySystemData.Colors.Error)
    end
end

local function validateKey()
    local userKey = KeyInput.Text:gsub("%s+", "")
    if not userKey or userKey == "" then
        ShowStatusMessage("✗ Please enter a key", KeySystemData.Colors.Error)
        return
    end

    ShowStatusMessage("⏳ Validating key...", KeySystemData.Colors.Accent)
    
    local JunkieKeySystem = loadstring(game:HttpGet("https://junkie-development.de/sdk/JunkieKeySystem.lua"))()
    
    local API_KEY = Config.api
    local SERVICE = Config.service
    
    local isValid = JunkieKeySystem.verifyKey(API_KEY, userKey, SERVICE)
    if isValid then
        ShowStatusMessage("✓ Success! Loading...", KeySystemData.Colors.Success)
        
        SmoothTween(MainFrame, 0.5, {
            Position = UDim2.new(0.5, 0, -0.5, 0),
            Transparency = 1
        })
        SmoothTween(Blur, 0.5, {BackgroundTransparency = 1})
        
        task.wait(0.5)
        ScreenGui:Destroy()
        
        main()
    else
        ShowStatusMessage("✗ Invalid key. Please try again", KeySystemData.Colors.Error)
        
        SmoothTween(MainFrame, 0.05, {Position = UDim2.new(0.5, -10, 0.5, 0)})
        task.wait(0.05)
        SmoothTween(MainFrame, 0.05, {Position = UDim2.new(0.5, 10, 0.5, 0)})
        task.wait(0.05)
        SmoothTween(MainFrame, 0.05, {Position = UDim2.new(0.5, 0, 0.5, 0)})
    end
end

SubmitButton.MouseButton1Click:Connect(validateKey)
GetKeyButton.MouseButton1Click:Connect(openGetKey)

local dragging, dragInput, dragStart, startPos
local function onInputChanged(input)
    if input == dragInput and dragging then
        local delta = input.Position - dragStart
        MainFrame.Position = UDim2.new(
            startPos.X.Scale, 
            startPos.X.Offset + delta.X, 
            startPos.Y.Scale, 
            startPos.Y.Offset + delta.Y
        )
    end
end

TitleBar.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        dragging = true
        dragStart = input.Position
        startPos = MainFrame.Position
        
        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

TitleBar.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement then
        dragInput = input
    end
end)

UserInputService.InputChanged:Connect(onInputChanged)

DiscordButton.MouseButton1Click:Connect(function()
    if setclipboard then
        setclipboard(KeySystemData.DiscordInvite)
        ShowStatusMessage("✓ Discord link copied!", KeySystemData.Colors.Discord)
    else
        ShowStatusMessage(KeySystemData.DiscordInvite, KeySystemData.Colors.Discord)
    end
end)

KeyInput.FocusLost:Connect(function(enterPressed)
    if enterPressed then
        validateKey()
    end
end)

MainFrame.Position = UDim2.new(0.5, 0, 0.4, 0)
MainFrame.Size = UDim2.new(0, 0, 0, 0)
MainFrame.Transparency = 1
Blur.BackgroundTransparency = 1

SmoothTween(Blur, 0.4, {BackgroundTransparency = 0.3})
SmoothTween(MainFrame, 0.5, {
    Size = UDim2.new(0, 380, 0, 280), 
    Position = UDim2.new(0.5, 0, 0.5, 0),
    Transparency = 0
})
