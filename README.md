print("deobf by discord.gg/speedhub and neymarish the goat")
print("deobf by discord.gg/speedhub and neymarish the goat")
print("deobf by discord.gg/speedhub and neymarish the goat")
print("deobf by discord.gg/speedhub and neymarish the goat")
print("deobf by discord.gg/speedhub and neymarish the goat")

local BACKGROUND_ID = ""

local win, autoPlayButton, tpBatButton

local TweenService, UserInputService, RunService, Players, Lighting, flag18, Assets, findDescendant, flag19
local inputMatches, Config, saveConfig, index, ReplicatedStorage, WorkspaceService, LocalPlayer, playerGui, color, Keybinds
local fn32, fn33, fn34, fn35, fn36, fn37, fn38, fn39, fn40, v84
local tbl22, lagger, custom, carry, v85, v86, v87, tbl23, flag20, flag21
local fn41, fn42, fn43, fn44, fn45, fn46, fn47
local Tween, Components

do
  local v88, tbl24, fn48, v89, v90, v91, tbl25, n32, v92, now2
  local v93, v94, n33, fn49, fn50, fn51, n34, fn52

  do
    local fn53, fn54

    do
      local v95

      do
        local localPlayer, fn55, Theme, fn56, fn57, fn58, tbl26, tbl27, tbl28, fn59
        local fn60

        do
          do
            do
              repeat
                task.wait()
              until game:IsLoaded()

              TweenService = game:GetService("TweenService")
              UserInputService = game:GetService("UserInputService")
              RunService = game:GetService("RunService")
              Players = game:GetService("Players")
              Lighting = game:GetService("Lighting")
              localPlayer = Players.LocalPlayer
              flag18 = false

              fn55 = function(arg, arg2)
                local str8 = arg2 or "hookduels_bg_custom.png"
                local getCustomAsset = getcustomasset or getsynasset or syn and syn.get_custom_asset
                if not getCustomAsset then
                  return ""
                end

                if isfile and isfile(str8) then
                  local ok, result = pcall(getCustomAsset, str8)
                  if ok and result and result ~= "" then
                    return result
                  end
                end

                if writefile then
                  pcall(function()
                    local request_ = syn and syn.request or http and http.request or http_request
                    local request_2

                    if request_ then
                      request_2 = request_
                    else
                      request_2 = fluxus and fluxus.request
                    end

                    request_2 = request_2 or request
                    local body = nil

                    if request_2 then
                      local v96 = request_2({ Url = arg, Method = "GET" })
                      local body2 = v96 and (v96.Body or v96.body)
                      body = nil

                      if body2 then
                        body = v96.Body or v96.body
                      end
                    end

                    if not body and game.HttpGet then
                      body = game:HttpGet(arg)
                    end

                    if body and #body > 0 then
                      writefile(str8, body)
                    end
                  end)

                  if isfile and isfile(str8) then
                    local ok, result = pcall(getCustomAsset, str8)
                    if ok and result and result ~= "" then
                      return result
                    end
                  end
                end

                return ""
              end

              do
                local function fn61(arg)
                  local str8 = arg or "hookduels_bg_custom.png"
                  local v96 = getcustomasset or getsynasset
                  local getCustomAsset

                  if v96 then
                    getCustomAsset = v96
                  else
                    getCustomAsset = syn and syn.get_custom_asset
                  end

                  if not getCustomAsset then
                    return ""
                  end

                  if isfile and isfile(str8) then
                    local ok, result = pcall(getCustomAsset, str8)
                    if ok and result and result ~= "" then
                      return result
                    end
                  end

                  return ""
                end

                local backgroundImage = tostring(BACKGROUND_ID)

                if backgroundImage ~= "" and not backgroundImage:find("rbxasset") then
                  backgroundImage = "rbxassetid://" .. backgroundImage
                end

                Assets = {
                  Circle = "rbxassetid://266543268",
                  Backgrounds = { backgroundImage ~= "" and backgroundImage or fn61("hookduels_bg_custom.png") },
                }
              end
            end

            do
              task.spawn(function()
                if Assets.Backgrounds[1] == "" then
                  local png = fn55("https://files.catbox.moe/a2goit.png", "hookduels_bg_custom.png")

                  if png and png ~= "" then
                    Assets.Backgrounds[1] = png
                  end
                end
              end)

              Theme = {}
              Theme.__index = Theme

              Theme.Themes = {
                Midnight = {
                  Bg = Color3.fromRGB(12, 8, 16),
                  Panel = Color3.fromRGB(20, 11, 32),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(192, 132, 252),
                  Accent = Color3.fromRGB(168, 85, 247),
                },
                ["Abyss Cyan"] = {
                  Bg = Color3.fromRGB(6, 10, 22),
                  Panel = Color3.fromRGB(12, 20, 38),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(148, 163, 184),
                  Accent = Color3.fromRGB(34, 211, 238),
                },
                Cyberpunk = {
                  Bg = Color3.fromRGB(8, 10, 15),
                  Panel = Color3.fromRGB(18, 12, 30),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(185, 140, 240),
                  Accent = Color3.fromRGB(168, 85, 247),
                },
                ["Neon Violet"] = {
                  Bg = Color3.fromRGB(7, 4, 16),
                  Panel = Color3.fromRGB(18, 9, 36),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(192, 132, 252),
                  Accent = Color3.fromRGB(192, 38, 211),
                },
                ["Graphite"] = {
                  Bg = Color3.fromRGB(12, 8, 14),
                  Panel = Color3.fromRGB(20, 14, 24),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(160, 165, 200),
                  Accent = Color3.fromRGB(168, 85, 247),
                },
                ["OLED Pure Dark"] = {
                  Bg = Color3.fromRGB(0, 0, 0),
                  Panel = Color3.fromRGB(12, 8, 20),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(150, 150, 160),
                  Accent = Color3.fromRGB(175, 65, 255),
                },
                ["Velvet Rose"] = {
                  Bg = Color3.fromRGB(12, 2, 12),
                  Panel = Color3.fromRGB(26, 6, 22),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(170, 162, 190),
                  Accent = Color3.fromRGB(175, 65, 255),
                },
                ["Blood Red"] = {
                  Bg = Color3.fromRGB(16, 4, 8),
                  Panel = Color3.fromRGB(32, 8, 12),
                  Text = Color3.fromRGB(255, 240, 240),
                  Sub = Color3.fromRGB(170, 140, 145),
                  Accent = Color3.fromRGB(255, 45, 70),
                },
                ["Galaxy Indigo"] = {
                  Bg = Color3.fromRGB(8, 6, 20),
                  Panel = Color3.fromRGB(20, 14, 40),
                  Text = Color3.fromRGB(240, 240, 255),
                  Sub = Color3.fromRGB(150, 150, 170),
                  Accent = Color3.fromRGB(165, 85, 255),
                },
                Carbon = {
                  Bg = Color3.fromRGB(12, 12, 14),
                  Panel = Color3.fromRGB(24, 24, 28),
                  Text = Color3.fromRGB(238, 238, 242),
                  Sub = Color3.fromRGB(150, 151, 161),
                  Accent = Color3.fromRGB(90, 208, 188),
                },
                Ocean = {
                  Bg = Color3.fromRGB(8, 16, 26),
                  Panel = Color3.fromRGB(18, 32, 48),
                  Text = Color3.fromRGB(224, 238, 250),
                  Sub = Color3.fromRGB(136, 164, 192),
                  Accent = Color3.fromRGB(64, 156, 255),
                },
                Purple = {
                  Bg = Color3.fromRGB(16, 8, 26),
                  Panel = Color3.fromRGB(32, 20, 50),
                  Text = Color3.fromRGB(238, 232, 242),
                  Sub = Color3.fromRGB(192, 132, 252),
                  Accent = Color3.fromRGB(168, 85, 247),
                },
                Sunset = {
                  Bg = Color3.fromRGB(20, 8, 22),
                  Panel = Color3.fromRGB(28, 14, 40),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(200, 140, 180),
                  Accent = Color3.fromRGB(217, 70, 239),
                },
                ["Golden Sunset"] = {
                  Bg = Color3.fromRGB(20, 10, 6),
                  Panel = Color3.fromRGB(36, 18, 16),
                  Text = Color3.fromRGB(255, 250, 240),
                  Sub = Color3.fromRGB(215, 170, 140),
                  Accent = Color3.fromRGB(255, 175, 40),
                },
                ["Cotton Candy"] = {
                  Bg = Color3.fromRGB(18, 10, 22),
                  Panel = Color3.fromRGB(34, 18, 42),
                  Text = Color3.fromRGB(255, 245, 255),
                  Sub = Color3.fromRGB(210, 160, 220),
                  Accent = Color3.fromRGB(255, 130, 180),
                },
                ["Hot Pink"] = {
                  Bg = Color3.fromRGB(12, 2, 8),
                  Panel = Color3.fromRGB(26, 6, 18),
                  Text = Color3.fromRGB(255, 255, 255),
                  Sub = Color3.fromRGB(215, 130, 190),
                  Accent = Color3.fromRGB(225, 35, 140),
                },
                ["Forest"] = {
                  Bg = Color3.fromRGB(8, 18, 14),
                  Panel = Color3.fromRGB(18, 34, 27),
                  Text = Color3.fromRGB(230, 246, 238),
                  Sub = Color3.fromRGB(150, 188, 170),
                  Accent = Color3.fromRGB(52, 216, 153),
                },
                ["Rose Quartz"] = {
                  Bg = Color3.fromRGB(22, 12, 18),
                  Panel = Color3.fromRGB(40, 28, 32),
                  Text = Color3.fromRGB(242, 232, 242),
                  Sub = Color3.fromRGB(180, 152, 178),
                  Accent = Color3.fromRGB(255, 98, 160),
                },
                ["Black & White"] = {
                  Bg = Color3.fromRGB(5, 5, 5),
                  Panel = Color3.fromRGB(22, 22, 22),
                  Text = Color3.fromRGB(250, 250, 250),
                  Sub = Color3.fromRGB(158, 158, 158),
                  Accent = Color3.fromRGB(255, 255, 255),
                },
                Arctic = {
                  Bg = Color3.fromRGB(226, 232, 240),
                  Panel = Color3.fromRGB(246, 248, 252),
                  Text = Color3.fromRGB(26, 31, 38),
                  Sub = Color3.fromRGB(108, 118, 142),
                  Accent = Color3.fromRGB(56, 130, 255),
                },
              }

              Theme.new = function(name)
                local obj = setmetatable({}, Theme)
                obj.Name = name or "Midnight"
                obj.Data = table.clone(Theme.Themes[obj.Name])
                obj._bindings = {}
                obj._accentBindings = {}
                return obj
              end

              Theme.Bind = function(arg, arg2, arg3, arg4)
                table.insert(arg._bindings, { inst = arg2, prop = arg3, key = arg4 })
                arg2[arg3] = arg.Data[arg4]
                return arg2
              end

              Theme.BindAccent = function(arg, arg2, arg3, arg4)
                table.insert(arg._accentBindings, { inst = arg2, prop = arg3, transform = arg4 })
                arg2[arg3] = arg4 and arg4(arg.Data.Accent) or arg.Data.Accent
                return arg2
              end

              Theme.SetAccent = function(arg, accent)
                arg.Data.Accent = accent

                for _, accentBinding in ipairs(arg._accentBindings) do
                  if accentBinding.inst and accentBinding.inst.Parent then
                    local tbl29 = { [accentBinding.prop] = accentBinding.transform and accentBinding.transform(accent) or accent }
                    TweenService:Create(accentBinding.inst, TweenInfo.new(0.35, Enum.EasingStyle.Quad), tbl29):Play()
                  end
                end
              end

              Theme.Apply = function(arg, name)
                if not Theme.Themes[name] then
                  return
                end
                arg.Name = name
                local v96 = table.clone(Theme.Themes[name])
                arg.Data = v96
                local tweenInfo = TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out)

                for _, binding in ipairs(arg._bindings) do
                  if binding.inst and binding.inst.Parent then
                    TweenService:Create(binding.inst, tweenInfo, { [binding.prop] = v96[binding.key] }):Play()
                  end
                end

                arg:SetAccent(v96.Accent)
              end

              Tween = {
                Presets = {
                  Snappy = TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                  Smooth = TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out),
                  Spring = TweenInfo.new(0.5, Enum.EasingStyle.Back, Enum.EasingDirection.Out),
                  Slow = TweenInfo.new(0.8, Enum.EasingStyle.Quint, Enum.EasingDirection.Out),
                },
                to = function(arg, arg2, arg3)
                  local tween = TweenService:Create(arg, type(arg2) == "string" and Tween.Presets[arg2] or arg2, arg3)
                  tween:Play()
                  return tween
                end,
              }

              fn56 = function(arg, arg2, arg3)
                local instance = Instance.new(arg)
                local v96 = pairs
                local tbl29 = arg2 or {}

                for k, v97 in v96(tbl29) do
                  if k ~= "Parent" then
                    instance[k] = v97
                  end
                end

                local v97 = ipairs
                local tbl30 = arg3 or {}

                for _, v98 in v97(tbl30) do
                  v98.Parent = instance
                end

                if arg2 and arg2.Parent then
                  instance.Parent = arg2.Parent
                end

                return instance
              end

              findDescendant = function(arg, arg2, arg3)
                local n35 = arg3 or 180
                local tbl29 = { arg }
                local n36 = 0

                while #tbl29 > 0 do
                  local v96 = table.remove(tbl29)
                  if v96 ~= arg and arg2(v96) then
                    return v96
                  end
                  local children = v96:GetChildren()

                  for i = 1, #children do
                    tbl29[#tbl29 + 1] = children[i]
                  end

                  n36 += 1

                  if n35 <= n36 then
                    task.wait()
                    n36 = 0
                  end
                end

                return nil
              end

              fn57 = function(arg, arg2)
                return fn56("UICorner", { CornerRadius = UDim.new(0, arg or 12), Parent = arg2 })
              end

              fn58 = function(arg, arg2, arg3)
                local n35 = arg3 or 12
                local v96 = fn56("Frame", { BackgroundTransparency = 1, Size = UDim2.fromOffset(n35, n35), Parent = arg })
                local n36 = n35 * 0.62

                for _, v97 in ipairs({ { -0.22, 45 }, { 0.22, -45 } }) do
                  fn56("Frame", {
                    BackgroundColor3 = arg2,
                    BorderSizePixel = 0,
                    AnchorPoint = Vector2.new(0.5, 0.5),
                    Position = UDim2.new(0.5, n35 * v97[1], 0.5, 0),
                    Size = UDim2.fromOffset(n36, 2),
                    Rotation = v97[2],
                    ZIndex = 20,
                    Parent = v96,
                  }, { fn56("UICorner", { CornerRadius = UDim.new(1, 0) }) })
                end

                return v96
              end

              tbl26 = {
                apply = function(parent, arg)
                  parent.BackgroundTransparency = (arg or {}).transparency or 0.15
                  local v96 = fn56

                  local tbl29 = {
                    Rotation = 90,
                    Color = ColorSequence.new({
                      ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 255, 255)),
                      ColorSequenceKeypoint.new(1, Color3.fromRGB(255, 255, 255)),
                    }),
                  }

                  local numberSequence = NumberSequence.new
                  local tbl30 = {}
                  local v97 = NumberSequenceKeypoint.new(0, 1)
                  local v98 = NumberSequenceKeypoint.new(0.5, 1)
                  local new = NumberSequenceKeypoint.new
                  tbl30[1] = v97
                  tbl30[2] = v98

                  do
                    local values = table.pack(new(1, 1))
                    table.move(values, 1, values.n, 3, tbl30)
                  end

                  tbl29.Transparency = numberSequence(tbl30)
                  tbl29.Parent = parent
                  v96("UIGradient", tbl29)

                  fn56("UIStroke", {
                    Thickness = 1,
                    Color = Color3.fromRGB(255, 255, 255),
                    Transparency = 0.75,
                    ApplyStrokeMode = Enum.ApplyStrokeMode.Border,
                    Parent = parent,
                  })
                end,
              }

              tbl27 = {}
              flag19 = false

              do
                local tbl29 = {}
                local rotation = 0
                local n35 = 0

                RunService.RenderStepped:Connect(function(deltaTime)
                  n35 += deltaTime or 0.016
                  if n35 < 0.033333333333333333 then
                    return
                  end
                  local v96 = n35
                  n35 = 0
                  rotation = (rotation + (v96 or 0.016) * 130) % 360

                  for i = #tbl29, 1, -1 do
                    local v97 = tbl29[i]

                    if v97 and v97.Parent then
                      local parent = v97.Parent

                      if parent and parent.Parent and parent.Parent.Visible ~= false then
                        v97.Rotation = rotation
                      end
                    else
                      table.remove(tbl29, i)
                    end
                  end
                end)

                tbl27.attach = function(arg)
                  local v96 = fn56("UIStroke", {
                    Thickness = 1.5,
                    Color = Color3.fromRGB(255, 255, 255),
                    Transparency = 0.15,
                    ApplyStrokeMode = Enum.ApplyStrokeMode.Border,
                    Parent = arg,
                  })

                  local v97 = fn56
                  local tbl30 = {}
                  local colorSequence = ColorSequence.new
                  local tbl31 = {}
                  local v98 = ColorSequenceKeypoint.new(0, Color3.fromRGB(168, 85, 247))
                  local v99 = ColorSequenceKeypoint.new(0.2, Color3.fromRGB(150, 50, 220))
                  local v100 = ColorSequenceKeypoint.new(0.4, Color3.fromRGB(196, 130, 255))
                  local v101 = ColorSequenceKeypoint.new(0.6, Color3.fromRGB(130, 40, 190))
                  local v102 = ColorSequenceKeypoint.new(0.8, Color3.fromRGB(180, 80, 250))
                  local new = ColorSequenceKeypoint.new
                  local color2 = Color3.fromRGB
                  local v103 = 247
                  tbl31[1] = v98
                  tbl31[2] = v99
                  tbl31[3] = v100
                  tbl31[4] = v101
                  tbl31[5] = v102

                  do
                    local values = table.pack(new(1, color2(168, 85, v103)))
                    table.move(values, 1, values.n, 6, tbl31)
                  end

                  tbl30.Color = colorSequence(tbl31)
                  local numberSequence = NumberSequence.new
                  local tbl32 = {}
                  local v104 = NumberSequenceKeypoint.new(0, 0.05)
                  local v105 = NumberSequenceKeypoint.new(0.5, 0.6)
                  local new2 = NumberSequenceKeypoint.new
                  local v106 = 1
                  tbl32[1] = v104
                  tbl32[2] = v105

                  do
                    local values = table.pack(new2(v106, 0.05))
                    table.move(values, 1, values.n, 3, tbl32)
                  end

                  tbl30.Transparency = numberSequence(tbl32)
                  tbl30.Parent = v96
                  local UIGradient = v97("UIGradient", tbl30)
                  tbl29[#tbl29 + 1] = UIGradient

                  return {
                    stroke = v96,
                    gradient = UIGradient,
                    brighten = function(arg2, arg3)
                      Tween.to(v96, Tween.Presets.Smooth, { Transparency = arg3 and 0.05 or 0.15, Thickness = arg3 and 2.2 or 1.5 })
                    end,
                    setAccent = function(arg2, arg3)
                      local v107 = UIGradient
                      local colorSequence2 = ColorSequence.new
                      local tbl33 = {}
                      local v108 = ColorSequenceKeypoint.new(0, arg3 or Color3.fromRGB(168, 85, 247))
                      local v109 = ColorSequenceKeypoint.new(0.33, Color3.fromRGB(150, 50, 220))
                      local v110 = ColorSequenceKeypoint.new(0.66, Color3.fromRGB(196, 130, 255))
                      local new3 = ColorSequenceKeypoint.new
                      arg3 = arg3 or Color3.fromRGB(168, 85, 247)
                      local v111 = table.pack(new3(1, arg3))
                      tbl33[1] = v108
                      tbl33[2] = v109
                      tbl33[3] = v110

                      do
                        local values = table.pack(table.unpack(v111, 1, v111.n))
                        table.move(values, 1, values.n, 4, tbl33)
                      end

                      v107.Color = colorSequence2(tbl33)
                    end,
                    destroy = function()
                      local v107 = table.find(tbl29, UIGradient)

                      if v107 then
                        table.remove(tbl29, v107)
                      end
                    end,
                  }
                end
              end
            end

            do
              tbl28 = {
                attach = function(arg, arg2, arg3)
                  local n35 = arg3 or 12

                  local Frame = fn56("Frame", {
                    Name = "Particles",
                    BackgroundTransparency = 1,
                    Size = UDim2.fromScale(1, 1),
                    ClipsDescendants = true,
                    ZIndex = 2,
                    Parent = arg,
                  })

                  local tbl29 = {}

                  for i = 1, n35 do
                    tbl29[i] = {
                      inst = fn56("ImageLabel", {
                        Image = Assets.Circle,
                        BackgroundTransparency = 1,
                        ImageColor3 = arg2,
                        ImageTransparency = math.random(50, 82) / 100,
                        Size = UDim2.fromOffset(math.random(2, 5), math.random(2, 5)),
                        Position = UDim2.fromScale(math.random(), math.random()),
                        ZIndex = 2,
                        Parent = Frame,
                      }),
                      speed = math.random(3, 8) / 100,
                    }
                  end

                  local n36 = 0

                  local connection = RunService.RenderStepped:Connect(function(deltaTime)
                    if flag19 then
                      return
                    end
                    n36 += deltaTime
                    if n36 < 0.05 then
                      return
                    end
                    local v96 = n36
                    n36 = 0

                    for _, v97 in ipairs(tbl29) do
                      local position = v97.inst.Position
                      local n37 = position.Y.Scale - v97.speed * v96

                      if n37 < -0.05 then
                        n37 = 1.05
                      end

                      v97.inst.Position = UDim2.new(position.X.Scale, 0, n37, 0)
                    end
                  end)

                  Frame.Destroying:Connect(function()
                    if connection.Connected then
                      connection:Disconnect()
                    end
                  end)

                  return {
                    layer = Frame,
                    dots = tbl29,
                    setAccent = function(arg4, imageColor3)
                      for _, v96 in ipairs(tbl29) do
                        v96.inst.ImageColor3 = imageColor3
                      end
                    end,
                  }
                end,
              }

              fn59 = function()
                for _, child in ipairs(Lighting:GetChildren()) do
                  if child.Name == "GlassUIBlur" or child:IsA("BlurEffect") and child.Name:find("Glass") then
                    pcall(function()
                      child:Destroy()
                    end)
                  end
                end
              end

              fn59()

              do
                local function fn61(arg, arg2, arg3, arg4)
                  local Frame = fn56("Frame", {
                    BackgroundColor3 = arg4,
                    BackgroundTransparency = 0.5,
                    Size = UDim2.fromOffset(0, 0),
                    AnchorPoint = Vector2.new(0.5, 0.5),
                    Position = UDim2.fromOffset(arg2, arg3),
                    ZIndex = 12,
                    Parent = arg,
                  }, { fn56("UICorner", { CornerRadius = UDim.new(1, 0) }) })

                  Tween.to(
                    Frame,
                    TweenInfo.new(0.6, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    { Size = UDim2.fromOffset(240, 240), BackgroundTransparency = 1 }
                  ).Completed
                    :Connect(function()
                      Frame:Destroy()
                    end)
                end

                Components = {
                  _accentRail = function()
                    return nil
                  end,
                  _hoverSurface = function(arg, arg2, arg3)
                    arg.MouseEnter:Connect(function()
                      Tween.to(arg, Tween.Presets.Snappy, { BackgroundTransparency = arg3 or 0.15 })
                    end)

                    arg.MouseLeave:Connect(function()
                      local to = Tween.to
                      local snappy = Tween.Presets.Snappy
                      local tbl29 = {}
                      local v96 = arg2
                      local backgroundTransparency

                      if arg2 then
                        backgroundTransparency = v96
                      else
                        backgroundTransparency = 0.28
                      end

                      tbl29.BackgroundTransparency = backgroundTransparency
                      to(arg, snappy, tbl29)
                    end)
                  end,
                  Button = function(arg, arg2, arg3, arg4)
                    local TextButton = fn56("TextButton", {
                      Size = UDim2.new(1, 0, 0, 42),
                      BackgroundColor3 = arg.Data.Panel,
                      AutoButtonColor = false,
                      Text = "",
                      ClipsDescendants = true,
                      Parent = arg2,
                    })

                    fn57(11, TextButton)
                    arg:Bind(TextButton, "BackgroundColor3", "Panel")
                    tbl26.apply(TextButton, { transparency = 0.2 })
                    local v96 = tbl27.attach(TextButton, arg.Data.Accent)
                    arg:BindAccent(v96.stroke, "Color")
                    v96.stroke.Transparency = 0.55
                    Components._accentRail(arg, TextButton, 20)
                    local v97 = "Text"

                    arg:Bind(
                      fn56("TextLabel", {
                        BackgroundTransparency = 1,
                        Size = UDim2.fromScale(1, 1),
                        Font = Enum.Font.MontserratBold,
                        Text = arg3,
                        TextSize = 13,
                        TextColor3 = Color3.fromRGB(255, 255, 255),
                        TextTruncate = Enum.TextTruncate.AtEnd,
                        ZIndex = 5,
                        Parent = TextButton,
                      }),
                      "TextColor3",
                      v97
                    )

                    TextButton.MouseEnter:Connect(function()
                      v96:brighten(true)
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.05 })
                    end)

                    TextButton.MouseLeave:Connect(function()
                      v96:brighten(false)
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.2 })
                    end)

                    TextButton.MouseButton1Down:Connect(function()
                      Tween.to(TextButton, Tween.Presets.Snappy, { Size = UDim2.new(1, -4, 0, 38) })
                    end)

                    TextButton.MouseButton1Up:Connect(function()
                      Tween.to(TextButton, Tween.Presets.Spring, { Size = UDim2.new(1, 0, 0, 42) })
                    end)

                    TextButton.MouseButton1Click:Connect(function()
                      local mouseLocation = UserInputService:GetMouseLocation()
                      fn61(
                        TextButton,
                        mouseLocation.X - TextButton.AbsolutePosition.X,
                        mouseLocation.Y - TextButton.AbsolutePosition.Y,
                        arg.Data.Accent
                      )

                      if arg4 then
                        task.spawn(arg4)
                      end
                    end)

                    return TextButton
                  end,
                  Toggle = function(arg, arg2, arg3, arg4, arg5)
                    local flag22 = arg4 or false

                    local Frame = fn56("Frame", {
                      Size = UDim2.new(1, 0, 0, 46),
                      BackgroundColor3 = arg.Data.Panel,
                      ClipsDescendants = true,
                      Parent = arg2,
                    })

                    fn57(11, Frame)
                    tbl26.apply(Frame, { transparency = 0.28 })
                    arg:Bind(Frame, "BackgroundColor3", "Panel")
                    Components._accentRail(arg, Frame, 20)
                    Components._hoverSurface(Frame, 0.28, 0.2)
                    local v96 = "Text"

                    arg:Bind(
                      fn56("TextLabel", {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(14, 0),
                        Size = UDim2.new(1, -100, 1, 0),
                        Font = Enum.Font.MontserratBold,
                        Text = arg3,
                        TextSize = 13,
                        TextColor3 = Color3.fromRGB(255, 255, 255),
                        TextXAlignment = Enum.TextXAlignment.Left,
                        TextTruncate = Enum.TextTruncate.AtEnd,
                        ZIndex = 3,
                        Parent = Frame,
                      }),
                      "TextColor3",
                      v96
                    )

                    local Frame2 = fn56("Frame", {
                      AnchorPoint = Vector2.new(1, 0.5),
                      Position = UDim2.new(1, -14, 0.5, 0),
                      Size = UDim2.fromOffset(48, 26),
                      BackgroundColor3 = Color3.fromRGB(28, 24, 34),
                      ZIndex = 3,
                      Parent = Frame,
                    })

                    fn57(12, Frame2)
                    local v97 = fn56("UIStroke", { Thickness = 1.2, Color = arg.Data.Accent, Transparency = 0.65, Parent = Frame2 })
                    arg:BindAccent(v97, "Color")

                    local Frame3 = fn56("Frame", {
                      BackgroundColor3 = Color3.fromRGB(255, 255, 255),
                      Size = UDim2.fromOffset(20, 20),
                      Position = UDim2.fromOffset(3, 3),
                      ZIndex = 5,
                      Parent = Frame2,
                    }, { fn56("UICorner", { CornerRadius = UDim.new(1, 0) }) })

                    fn56("UIStroke", { Thickness = 1, Color = Color3.fromRGB(255, 255, 255), Transparency = 0.4, Parent = Frame3 })

                    local function fn62(arg6)
                      local spring = arg6 and Tween.Presets.Spring or TweenInfo.new(0)
                      local udim2 = flag22 and UDim2.fromOffset(25, 3) or UDim2.fromOffset(3, 3)

                      Tween.to(Frame2, spring, {
                        BackgroundColor3 = flag22 and (arg.Data.Accent or Color3.fromRGB(190, 32, 168)) or Color3.fromRGB(28, 24, 34),
                      })

                      Tween.to(Frame3, spring, { Position = udim2 })
                      Tween.to(v97, spring, { Transparency = flag22 and 0.15 or 0.65 })
                    end

                    fn62(false)

                    local TextButton = fn56("TextButton", {
                      BackgroundTransparency = 1,
                      Size = UDim2.fromScale(1, 1),
                      Text = "",
                      ZIndex = 10,
                      Parent = Frame,
                    })

                    TextButton.MouseButton1Down:Connect(function()
                      Tween.to(Frame3, Tween.Presets.Snappy, { Size = UDim2.fromOffset(22, 18) })
                    end)

                    TextButton.MouseButton1Up:Connect(function()
                      Tween.to(Frame3, Tween.Presets.Spring, { Size = UDim2.fromOffset(20, 20) })
                    end)

                    TextButton.MouseButton1Click:Connect(function()
                      flag22 = not flag22
                      fn62(true)

                      if arg5 then
                        task.spawn(arg5, flag22)
                      end
                    end)

                    return {
                      setState = function(arg6)
                        flag22 = arg6
                        fn62(true)
                      end,
                      getState = function()
                        return flag22
                      end,
                    }
                  end,
                  Slider = function(arg, arg2, arg3, arg4, arg5, arg6, arg7, arg8)
                    local n35 = arg6 or arg4 or 0

                    if arg8 and arg8 > 0 then
                      local n36 = 12 ^ arg8
                      n35 = math.floor(n35 * n36 + 0.5) / n36
                    end

                    local Frame = fn56("Frame", {
                      Size = UDim2.new(1, 0, 0, 44),
                      BackgroundColor3 = arg.Data.Panel,
                      ClipsDescendants = true,
                      Parent = arg2,
                    })

                    fn57(12, Frame)
                    tbl26.apply(Frame, { transparency = 0.25 })
                    arg:Bind(Frame, "BackgroundColor3", "Panel")
                    Components._hoverSurface(Frame, 0.25, 0.12)

                    arg:Bind(
                      fn56("TextLabel", {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(14, 0),
                        Size = UDim2.new(1, -115, 1, 0),
                        Font = Enum.Font.MontserratBold,
                        Text = arg3,
                        TextSize = 13,
                        TextColor3 = Color3.fromRGB(255, 255, 255),
                        TextXAlignment = Enum.TextXAlignment.Left,
                        TextYAlignment = Enum.TextYAlignment.Center,
                        TextTruncate = Enum.TextTruncate.AtEnd,
                        ZIndex = 3,
                        Parent = Frame,
                      }),
                      "TextColor3",
                      "Text"
                    )

                    local Frame2 = fn56("Frame", {
                      AnchorPoint = Vector2.new(1, 0.5),
                      Position = UDim2.new(1, -16, 0.5, 0),
                      Size = UDim2.fromOffset(88, 28),
                      BackgroundColor3 = arg.Data.Bg,
                      BackgroundTransparency = 0.35,
                      ZIndex = 3,
                      Parent = Frame,
                    })

                    fn57(8, Frame2)
                    arg:Bind(Frame2, "BackgroundColor3", "Bg")

                    local UIStroke = fn56("UIStroke", {
                      Thickness = 1.2,
                      Color = arg.Data.Accent,
                      Transparency = 0.55,
                      ApplyStrokeMode = Enum.ApplyStrokeMode.Border,
                      Parent = Frame2,
                    })

                    arg:BindAccent(UIStroke, "Color")

                    local TextBox = fn56("TextBox", {
                      Size = UDim2.fromScale(1, 1),
                      BackgroundTransparency = 1,
                      Font = Enum.Font.MontserratBlack,
                      Text = tostring(n35):gsub("%.", ","),
                      TextSize = 13,
                      TextColor3 = Color3.fromRGB(255, 255, 255),
                      TextXAlignment = Enum.TextXAlignment.Center,
                      ClearTextOnFocus = false,
                      PlaceholderText = "",
                      PlaceholderColor3 = Color3.fromRGB(150, 140, 165),
                      ZIndex = 4,
                      Parent = Frame2,
                    })

                    arg:BindAccent(TextBox, "TextColor3")

                    local function fn62(arg9)
                      if not arg9 then
                        return n35
                      end
                      local str8 = tostring(arg9):gsub(",", "."):gsub("[^0-9%.%-]", "")
                      local num = tonumber(str8)
                      if not num then
                        return n35
                      end
                      local n36

                      if arg4 and arg5 and arg4 < arg5 then
                        n36 = math.clamp(num, arg4, arg5)
                      else
                        n36 = num
                      end

                      local n37

                      if arg8 and arg8 > 0 then
                        local n38 = 10 ^ arg8
                        n37 = math.floor(n36 * n38 + 0.5) / n38
                      else
                        n37 = math.floor(n36 * 100 + 0.5) / 100
                      end

                      return n37
                    end

                    local function fn63(arg9)
                      if not arg9 then
                        return ""
                      end

                      if arg9 == math.floor(arg9) then
                        return tostring(math.floor(arg9))
                      end
                      return tostring(arg9):gsub("%.", ",")
                    end

                    local function fn64(arg9, arg10)
                      n35 = fn62(arg9)
                      TextBox.Text = fn63(n35)

                      if arg10 ~= false and arg7 then
                        task.spawn(arg7, n35)
                      end
                    end

                    TextBox.Focused:Connect(function()
                      Tween.to(UIStroke, Tween.Presets.Snappy, { Transparency = 0.05, Thickness = 1.8 })
                      Tween.to(Frame2, Tween.Presets.Snappy, { BackgroundTransparency = 0.15 })
                    end)

                    TextBox.FocusLost:Connect(function()
                      Tween.to(UIStroke, Tween.Presets.Snappy, { Transparency = 0.55, Thickness = 1.2 })
                      Tween.to(Frame2, Tween.Presets.Snappy, { BackgroundTransparency = 0.35 })
                      fn64(TextBox.Text, true)
                    end)

                    fn64(n35, false)

                    return {
                      setValue = function(arg9)
                        fn64(arg9, false)
                      end,
                      getValue = function()
                        return n35
                      end,
                    }
                  end,
                  Dropdown = function(arg, arg2, arg3, arg4, arg5, arg6)
                    local v96 = arg4[1]

                    if arg6 ~= nil then
                      for _, v97 in ipairs(arg4) do
                        if v97 == arg6 then
                          v96 = arg6
                          break
                        end
                      end
                    end

                    local flag22 = false

                    local Frame = fn56("Frame", {
                      Size = UDim2.new(1, 0, 0, 46),
                      BackgroundColor3 = arg.Data.Panel,
                      ClipsDescendants = true,
                      ZIndex = 3,
                      Parent = arg2,
                    })

                    fn57(11, Frame)
                    tbl26.apply(Frame, { transparency = 0.28 })
                    arg:Bind(Frame, "BackgroundColor3", "Panel")
                    Components._accentRail(arg, Frame, 20)
                    Components._hoverSurface(Frame, 0.28, 0.15)

                    local TextButton = fn56("TextButton", {
                      BackgroundTransparency = 1,
                      Size = UDim2.new(1, 0, 0, 46),
                      Text = "",
                      ZIndex = 4,
                      Parent = Frame,
                    })

                    arg:Bind(
                      fn56("TextLabel", {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(14, 0),
                        Size = UDim2.new(0.42, -12, 0, 46),
                        Font = Enum.Font.MontserratBold,
                        Text = arg3,
                        TextSize = 13,
                        TextColor3 = arg.Data.Sub,
                        TextXAlignment = Enum.TextXAlignment.Left,
                        TextTruncate = Enum.TextTruncate.AtEnd,
                        ZIndex = 5,
                        Parent = TextButton,
                      }),
                      "TextColor3",
                      "Sub"
                    )

                    local TextLabel = fn56("TextLabel", {
                      BackgroundTransparency = 1,
                      Position = UDim2.new(0.42, 0, 0, 0),
                      Size = UDim2.new(0.58, -40, 0, 46),
                      Font = Enum.Font.MontserratBold,
                      Text = v96,
                      TextSize = 13,
                      TextColor3 = Color3.fromRGB(180, 45, 200),
                      TextXAlignment = Enum.TextXAlignment.Right,
                      TextTruncate = Enum.TextTruncate.AtEnd,
                      ZIndex = 4,
                      Parent = TextButton,
                    })

                    arg:Bind(TextLabel, "TextColor3", "Text")
                    local v97 = fn58(TextButton, arg.Data.Accent, 12)
                    v97.AnchorPoint = Vector2.new(1, 0.5)
                    v97.Position = UDim2.new(1, -14, 0, 23)
                    v97.ZIndex = 5

                    for _, child in ipairs(v97:GetChildren()) do
                      if child:IsA("Frame") then
                        arg:BindAccent(child, "BackgroundColor3")
                      end
                    end

                    local flag23 = #arg4 > 8
                    local n35 = flag23 and 150 or #arg4 * 34 + 4
                    local ScrollingFrame

                    if flag23 then
                      ScrollingFrame = fn56("ScrollingFrame", {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(0, 46),
                        Size = UDim2.new(1, 0, 0, n35),
                        ScrollBarThickness = 2,
                        ScrollBarImageColor3 = arg.Data.Accent,
                        CanvasSize = UDim2.new(),
                        AutomaticCanvasSize = Enum.AutomaticSize.Y,
                        ZIndex = 4,
                        Parent = Frame,
                      })

                      arg:BindAccent(ScrollingFrame, "ScrollBarImageColor3")
                    else
                      ScrollingFrame = fn56("Frame", {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(0, 46),
                        Size = UDim2.new(1, 0, 0, n35),
                        ZIndex = 5,
                        Parent = Frame,
                      })
                    end

                    fn56("UIListLayout", { Padding = UDim.new(0, 3), Parent = ScrollingFrame })

                    fn56("UIPadding", {
                      PaddingLeft = UDim.new(0, 6),
                      PaddingRight = UDim.new(0, 8),
                      PaddingBottom = UDim.new(0, 6),
                      Parent = ScrollingFrame,
                    })

                    local tbl29 = {}

                    for _, v98 in ipairs(arg4) do
                      local flag24 = v98 == v96

                      local TextButton2 = fn56("TextButton", {
                        Size = UDim2.new(1, 0, 0, 30),
                        BackgroundColor3 = arg.Data.Bg,
                        BackgroundTransparency = flag24 and 0.15 or 0.35,
                        Font = Enum.Font.MontserratBold,
                        Text = "  " .. v98,
                        TextSize = 12,
                        TextColor3 = flag24 and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(220, 220, 230),
                        TextXAlignment = Enum.TextXAlignment.Left,
                        AutoButtonColor = false,
                        ZIndex = 5,
                        Parent = ScrollingFrame,
                      })

                      fn57(7, TextButton2)
                      arg:Bind(TextButton2, "BackgroundColor3", "Bg")

                      local v99 = fn56("UIStroke", {
                        Thickness = 1,
                        Color = arg.Data.Accent,
                        Transparency = flag24 and 0.3 or 0.75,
                        Parent = TextButton2,
                      })

                      arg:BindAccent(v99, "Color")
                      tbl29[v98] = { btn = TextButton2, stroke = v99 }

                      TextButton2.MouseEnter:Connect(function()
                        Tween.to(TextButton2, Tween.Presets.Snappy, { BackgroundTransparency = 0.1 })
                        Tween.to(v99, Tween.Presets.Snappy, { Transparency = 0.25 })
                      end)

                      TextButton2.MouseLeave:Connect(function()
                        local flag25 = v98 == v96
                        Tween.to(TextButton2, Tween.Presets.Snappy, { BackgroundTransparency = flag25 and 0.15 or 0.35 })
                        Tween.to(v99, Tween.Presets.Snappy, { Transparency = flag25 and 0.3 or 0.75 })
                      end)

                      TextButton2.MouseButton1Click:Connect(function()
                        v96 = v98
                        TextLabel.Text = v98
                        flag22 = false
                        Frame.ZIndex = 3
                        Tween.to(Frame, Tween.Presets.Smooth, { Size = UDim2.new(1, 0, 0, 46) })
                        Tween.to(v97, Tween.Presets.Smooth, { Rotation = 0 })

                        for k, v100 in pairs(tbl29) do
                          local flag25 = k == v96
                          Tween.to(v100.btn, Tween.Presets.Snappy, { BackgroundTransparency = flag25 and 0.15 or 0.35 })
                          Tween.to(v100.stroke, Tween.Presets.Snappy, { Transparency = flag25 and 0.3 or 0.75 })
                        end

                        if arg5 then
                          task.spawn(arg5, v98)
                        end
                      end)
                    end

                    TextButton.MouseButton1Click:Connect(function()
                      flag22 = not flag22
                      Frame.ZIndex = flag22 and 15 or 3
                      Tween.to(Frame, Tween.Presets.Smooth, { Size = UDim2.new(1, 0, 0, flag22 and 46 + n35 + 6 or 46) })
                      Tween.to(v97, Tween.Presets.Smooth, { Rotation = flag22 and 180 or 0 })
                    end)

                    return {
                      getSelected = function()
                        return v96
                      end,
                      setSelected = function(text)
                        v96 = text
                        TextLabel.Text = text

                        for k, v98 in pairs(tbl29) do
                          local flag24 = k == v96
                          v98.btn.BackgroundTransparency = flag24 and 0.15 or 0.35
                          v98.stroke.Transparency = flag24 and 0.3 or 0.75
                        end
                      end,
                    }
                  end,
                }
              end
            end

            do
              local tbl29 = {
                MouseButton1 = "M1",
                MouseButton2 = "M2",
                MouseButton3 = "M3",
                MouseButton4 = "M4",
                MouseButton5 = "M5",
                MouseBackButton = "M4",
                MouseForwardButton = "M5",
                F13 = "M4",
                F14 = "M5",
                F15 = "M6",
                ButtonA = "A",
                ButtonB = "B",
                ButtonX = "X",
                ButtonY = "Y",
                ButtonL1 = "L1",
                ButtonR1 = "R1",
                ButtonL2 = "L2",
                ButtonR2 = "R2",
                ButtonL3 = "L3",
                ButtonR3 = "R3",
                ButtonSelect = "Sel",
                ButtonStart = "Strt",
                DPadUp = "Up",
                DPadDown = "Down",
                DPadLeft = "Left",
                DPadRight = "Right",
              }

              fn60 = function(arg)
                if type(arg) == "string" then
                  return arg
                end
                return arg and arg.Name or nil
              end

              local function fn61(arg)
                local v96 = fn60(arg)
                if not v96 then
                  return "None"
                end
                local match = v96:match("^MouseButton(%d+)$")
                if match then
                  return "M" .. match
                end
                return tbl29[v96] or v96
              end

              inputMatches = function(arg, arg2)
                if arg2 == nil or arg2 == Enum.KeyCode.None then
                  return false
                end

                if type(arg2) ~= "string" then
                  if arg.KeyCode ~= Enum.KeyCode.Unknown and arg.KeyCode == arg2 then
                    return true
                  end

                  if arg.UserInputType ~= Enum.UserInputType.None and arg.UserInputType == arg2 then
                    return true
                  end
                end

                local v96 = fn60(arg2)
                if not v96 or v96 == "None" then
                  return false
                end
                local userInputType = arg.UserInputType
                if v96:match("^MouseButton%d+$") then
                  return userInputType ~= nil and userInputType.Name == v96
                end
                local keyCode = arg.KeyCode
                if keyCode ~= nil and keyCode ~= Enum.KeyCode.Unknown and keyCode ~= Enum.KeyCode.None and keyCode.Name == v96 then
                  return true
                end
                return false
              end

              Components.Input = function(arg, arg2, arg3, arg4, arg5)
                local str8 = arg4 or ""

                local Frame = fn56("Frame", {
                  Size = UDim2.new(1, 0, 0, 46),
                  BackgroundColor3 = arg.Data.Panel,
                  ClipsDescendants = true,
                  Parent = arg2,
                })

                fn57(12, Frame)
                tbl26.apply(Frame, { transparency = 0.28 })
                arg:Bind(Frame, "BackgroundColor3", "Panel")
                Components._accentRail(arg, Frame, 20)
                Components._hoverSurface(Frame, 0.28, 0.2)

                arg:Bind(
                  fn56("TextLabel", {
                    BackgroundTransparency = 1,
                    Position = UDim2.fromOffset(14, 0),
                    Size = UDim2.new(0.38, 0, 1, 0),
                    Font = Enum.Font.MontserratBold,
                    Text = arg3,
                    TextSize = 13,
                    TextColor3 = Color3.fromRGB(255, 255, 255),
                    TextXAlignment = Enum.TextXAlignment.Left,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 3,
                    Parent = Frame,
                  }),
                  "TextColor3",
                  "Text"
                )

                local v96 = fn56("TextBox", {
                  AnchorPoint = Vector2.new(1, 0.5),
                  Position = UDim2.new(1, -16, 0.5, 0),
                  Size = UDim2.new(0.56, 0, 0, 30),
                  BackgroundColor3 = arg.Data.Bg,
                  BackgroundTransparency = 0.3,
                  Font = Enum.Font.MontserratBold,
                  Text = str8,
                  PlaceholderText = "Type here...",
                  TextSize = 12,
                  TextColor3 = Color3.fromRGB(255, 255, 255),
                  PlaceholderColor3 = Color3.fromRGB(150, 150, 150),
                  ClearTextOnFocus = false,
                  TextXAlignment = Enum.TextXAlignment.Left,
                  TextTruncate = Enum.TextTruncate.None,
                  ClipsDescendants = true,
                  ZIndex = 3,
                  Parent = Frame,
                })

                fn57(8, v96)
                arg:Bind(v96, "BackgroundColor3", "Bg")
                fn56("UIPadding", { PaddingLeft = UDim.new(0, 8), PaddingRight = UDim.new(0, 8), Parent = v96 })
                local v97 = tbl27.attach(v96, arg.Data.Accent)
                arg:BindAccent(v97.stroke, "Color")
                v97.stroke.Transparency = 0.5

                v96.Focused:Connect(function()
                  v97:brighten(true)
                end)

                v96.FocusLost:Connect(function()
                  v97:brighten(false)

                  if arg5 then
                    task.spawn(arg5, v96.Text)
                  end
                end)

                return {
                  getText = function()
                    return v96.Text
                  end,
                  setText = function(text)
                    v96.Text = text
                  end,
                }
              end

              Components.Keybind = function(arg, arg2, arg3, arg4, arg5)
                local rightShift = arg4 or Enum.KeyCode.RightShift
                local flag22 = false

                local v96 = fn56("Frame", {
                  Size = UDim2.new(1, 0, 0, 46),
                  BackgroundColor3 = arg.Data.Panel,
                  ClipsDescendants = true,
                  Parent = arg2,
                })

                fn57(11, v96)
                tbl26.apply(v96, { transparency = 0.28 })
                arg:Bind(v96, "BackgroundColor3", "Panel")
                Components._accentRail(arg, v96, 20)
                Components._hoverSurface(v96, 0.28, 0.15)

                arg:Bind(
                  fn56("TextLabel", {
                    BackgroundTransparency = 1,
                    Position = UDim2.fromOffset(14, 0),
                    Size = UDim2.new(1, -119, 1, 0),
                    Font = Enum.Font.MontserratBold,
                    Text = arg3,
                    TextSize = 13,
                    TextColor3 = Color3.fromRGB(255, 255, 255),
                    TextXAlignment = Enum.TextXAlignment.Left,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 3,
                    Parent = v96,
                  }),
                  "TextColor3",
                  "Text"
                )

                local v97 = fn56("TextButton", {
                  AnchorPoint = Vector2.new(1, 0.5),
                  Position = UDim2.new(1, -12, 0.5, 0),
                  Size = UDim2.fromOffset(26, 26),
                  BackgroundColor3 = Color3.fromRGB(32, 12, 26),
                  BackgroundTransparency = 0.25,
                  AutoButtonColor = false,
                  Font = Enum.Font.MontserratBlack,
                  Text = "X",
                  TextSize = 13,
                  TextColor3 = Color3.fromRGB(255, 110, 115),
                  ZIndex = 4,
                  Parent = v96,
                })

                fn57(7, v97)
                local UIStroke =
                  fn56("UIStroke", { Thickness = 1.2, Color = Color3.fromRGB(255, 65, 115), Transparency = 0.5, Parent = v97 })

                v97.MouseEnter:Connect(function()
                  Tween.to(v97, Tween.Presets.Snappy, {
                    BackgroundColor3 = Color3.fromRGB(65, 15, 45),
                    BackgroundTransparency = 0.1,
                    Size = UDim2.fromOffset(28, 28),
                    TextColor3 = Color3.fromRGB(255, 100, 150),
                  })

                  Tween.to(UIStroke, Tween.Presets.Snappy, { Transparency = 0.05, Color = Color3.fromRGB(255, 100, 150) })
                end)

                v97.MouseLeave:Connect(function()
                  Tween.to(v97, Tween.Presets.Snappy, {
                    BackgroundColor3 = Color3.fromRGB(32, 12, 26),
                    BackgroundTransparency = 0.25,
                    Size = UDim2.fromOffset(26, 26),
                    TextColor3 = Color3.fromRGB(255, 65, 115),
                  })

                  Tween.to(UIStroke, Tween.Presets.Snappy, { Transparency = 0.5, Color = Color3.fromRGB(255, 65, 115) })
                end)

                local TextButton = fn56("TextButton", {
                  AnchorPoint = Vector2.new(1, 0.5),
                  Position = UDim2.new(1, -40, 0.5, 0),
                  Size = UDim2.fromOffset(66, 28),
                  BackgroundColor3 = arg.Data.Bg,
                  BackgroundTransparency = 0.3,
                  AutoButtonColor = false,
                  Font = Enum.Font.MontserratBold,
                  Text = fn61(rightShift),
                  TextSize = 13,
                  TextColor3 = Color3.fromRGB(180, 45, 185),
                  ZIndex = 3,
                  Parent = v96,
                })

                fn57(8, TextButton)
                arg:Bind(TextButton, "BackgroundColor3", "Bg")
                arg:BindAccent(TextButton, "TextColor3")
                TextButton.Name = "HookKeybindBox"

                pcall(function()
                  TextButton.Selectable = true
                end)

                pcall(function()
                  v97.Selectable = false
                end)

                pcall(function()
                  game:GetService("GuiService").GuiNavigationEnabled = true
                end)

                local v98 = tbl27.attach(TextButton, arg.Data.Accent)
                arg:BindAccent(v98.stroke, "Color")
                v98.stroke.Transparency = 0.55

                TextButton.MouseEnter:Connect(function()
                  if not flag22 then
                    v98:brighten(true)
                    Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.1 })
                  end
                end)

                TextButton.MouseLeave:Connect(function()
                  if not flag22 then
                    v98:brighten(false)
                    Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.3 })
                  end
                end)

                v97.MouseButton1Click:Connect(function()
                  flag22 = false
                  flag18 = false

                  pcall(function()
                    game:GetService("GuiService").SelectedObject = nil
                  end)

                  rightShift = Enum.KeyCode.None
                  TextButton.Text = "None"
                  v98:brighten(false)

                  if arg5 then
                    task.spawn(arg5, Enum.KeyCode.None)
                  end
                end)

                TextButton.MouseButton1Click:Connect(function()
                  flag22 = true
                  flag18 = true
                  TextButton.Text = "..."
                  v98:brighten(true)
                end)

                local connection = UserInputService.InputBegan:Connect(function(input)
                  if not flag22 then
                    return
                  end
                  local userInputType = input.UserInputType
                  local keyCode

                  if userInputType == Enum.UserInputType.Keyboard then
                    if input.KeyCode == Enum.KeyCode.Escape then
                      flag22 = false
                      flag18 = false
                      TextButton.Text = fn61(rightShift)
                      v98:brighten(false)

                      pcall(function()
                        game:GetService("GuiService").SelectedObject = nil
                      end)

                      return
                    end

                    keyCode = input.KeyCode
                  elseif input.KeyCode ~= Enum.KeyCode.Unknown and input.KeyCode.Name:match("^Mouse") then
                    keyCode = input.KeyCode.Name
                  elseif userInputType.Name:match("^MouseButton%d+$") and userInputType.Name ~= "MouseButton1" then
                    keyCode = userInputType.Name
                  elseif
                    (
                      userInputType.Name:find("Gamepad")
                      or userInputType == Enum.UserInputType.Gamepad1
                      or userInputType == Enum.UserInputType.Gamepad2
                      or userInputType == Enum.UserInputType.Gamepad3
                      or userInputType == Enum.UserInputType.Gamepad4
                    ) and input.KeyCode ~= Enum.KeyCode.Unknown
                  then
                    keyCode = input.KeyCode
                  else
                    keyCode = nil

                    if input.KeyCode ~= Enum.KeyCode.Unknown then
                      keyCode = input.KeyCode
                    end
                  end

                  if keyCode then
                    rightShift = keyCode
                    TextButton.Text = fn61(rightShift)
                    flag22 = false
                    flag18 = false
                    v98:brighten(false)

                    pcall(function()
                      game:GetService("GuiService").SelectedObject = nil
                    end)

                    if arg5 then
                      task.spawn(arg5, rightShift)
                    end
                  end
                end)

                v96.Destroying:Connect(function()
                  if connection.Connected then
                    connection:Disconnect()
                  end
                end)

                return {
                  getKey = function()
                    return rightShift
                  end,
                  setKey = function(arg6)
                    rightShift = arg6
                    TextButton.Text = fn61(arg6)
                  end,
                }
              end
            end
          end

          do
            local HttpService, flag22

            do
              do
                Components.Stepper = function(arg, arg2, arg3, arg4, arg5, arg6, arg7, arg8)
                  local n35 = arg7 or arg4

                  local v96 = fn56("Frame", {
                    Size = UDim2.new(1, 0, 0, 62),
                    BackgroundColor3 = arg.Data.Panel,
                    ClipsDescendants = true,
                    Parent = arg2,
                  })

                  fn57(11, v96)
                  tbl26.apply(v96, { transparency = 0.28 })
                  arg:Bind(v96, "BackgroundColor3", "Panel")
                  Components._accentRail(arg, v96, 20)
                  Components._hoverSurface(v96, 0.28, 0.2)
                  local v97 = "TextColor3"

                  arg:Bind(
                    fn56("TextLabel", {
                      BackgroundTransparency = 1,
                      Position = UDim2.fromOffset(14, 3),
                      Size = UDim2.new(1, -28, 0, 23),
                      Font = Enum.Font.MontserratBold,
                      Text = arg3,
                      TextSize = 13,
                      TextColor3 = Color3.fromRGB(255, 255, 255),
                      TextXAlignment = Enum.TextXAlignment.Left,
                      TextTruncate = Enum.TextTruncate.AtEnd,
                      ZIndex = 3,
                      Parent = v96,
                    }),
                    v97,
                    "Text"
                  )

                  local Frame = fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 1),
                    Position = UDim2.new(0.5, 0, 1, -6),
                    Size = UDim2.new(1, -24, 0, 28),
                    BackgroundColor3 = arg.Data.Bg,
                    BackgroundTransparency = 0.45,
                    ZIndex = 3,
                    Parent = v96,
                  })

                  fn57(10, Frame)
                  arg:Bind(Frame, "BackgroundColor3", "Bg")
                  fn56("UIStroke", { Thickness = 1.2, Color = Color3.fromRGB(195, 20, 155), Transparency = 0.65, Parent = Frame })

                  local v98 = fn56("TextLabel", {
                    AnchorPoint = Vector2.new(0.5, 0.5),
                    Position = UDim2.fromScale(0.5, 0.5),
                    Size = UDim2.new(1, -72, 1, 0),
                    BackgroundTransparency = 1,
                    Font = Enum.Font.MontserratBold,
                    Text = tostring(n35),
                    TextSize = 13,
                    TextColor3 = Color3.fromRGB(225, 45, 185),
                    ZIndex = 5,
                    Parent = Frame,
                  })

                  arg:BindAccent(v98, "TextColor3")

                  local function fn61(arg9)
                    local TextButton = fn56("TextButton", {
                      Size = UDim2.fromOffset(28, 28),
                      BackgroundColor3 = arg.Data.Bg,
                      BackgroundTransparency = 0.2,
                      AutoButtonColor = false,
                      Text = "",
                      ZIndex = 4,
                      Parent = Frame,
                    })

                    TextButton.AnchorPoint = Vector2.new(arg9 == "minus" and 0 or 1, 0.5)
                    TextButton.Position = arg9 == "minus" and UDim2.new(0, 0, 0.5, 0) or UDim2.new(1, 0, 0.5, 0)
                    fn57(8, TextButton)
                    arg:Bind(TextButton, "BackgroundColor3", "Bg")
                    local UIStroke = fn56("UIStroke", { Thickness = 1, Color = arg.Data.Accent, Transparency = 0.7, Parent = TextButton })
                    arg:BindAccent(UIStroke, "Color")

                    arg:BindAccent(
                      fn56("Frame", {
                        AnchorPoint = Vector2.new(0.5, 0.5),
                        Position = UDim2.fromScale(0.5, 0.5),
                        Size = UDim2.fromOffset(16, 2),
                        BackgroundColor3 = arg.Data.Accent,
                        BorderSizePixel = 0,
                        ZIndex = 10,
                        Parent = TextButton,
                      }, { fn56("UICorner", { CornerRadius = UDim.new(1, 0) }) }),
                      "BackgroundColor3"
                    )

                    if arg9 == "plus" then
                      arg:BindAccent(
                        fn56("Frame", {
                          AnchorPoint = Vector2.new(0.5, 0.5),
                          Position = UDim2.fromScale(0.5, 0.5),
                          Size = UDim2.fromOffset(2, 12),
                          BackgroundColor3 = arg.Data.Accent,
                          BorderSizePixel = 0,
                          ZIndex = 5,
                          Parent = TextButton,
                        }, { fn56("UICorner", { CornerRadius = UDim.new(1, 0) }) }),
                        "BackgroundColor3"
                      )
                    end

                    TextButton.MouseEnter:Connect(function()
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0 })
                      Tween.to(UIStroke, Tween.Presets.Snappy, { Transparency = 0.25 })
                    end)

                    TextButton.MouseLeave:Connect(function()
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.2 })
                      Tween.to(UIStroke, Tween.Presets.Snappy, { Transparency = 0.7 })
                    end)

                    TextButton.MouseButton1Down:Connect(function()
                      Tween.to(TextButton, Tween.Presets.Snappy, { Size = UDim2.fromOffset(24, 24) })
                    end)

                    TextButton.MouseButton1Up:Connect(function()
                      Tween.to(TextButton, Tween.Presets.Spring, { Size = UDim2.fromOffset(28, 28) })
                    end)

                    return TextButton
                  end

                  local minus = fn61("minus")
                  local plus = fn61("plus")

                  local function fn62()
                    n35 = math.clamp(n35, arg4, arg5)
                    v98.Text = tostring(n35)

                    if arg8 then
                      task.spawn(arg8, n35)
                    end
                  end

                  minus.MouseButton1Click:Connect(function()
                    n35 -= arg6
                    fn62()
                  end)

                  plus.MouseButton1Click:Connect(function()
                    n35 += arg6
                    fn62()
                  end)

                  return {
                    setValue = function(arg9)
                      n35 = arg9
                      fn62()
                    end,
                    getValue = function()
                      return n35
                    end,
                  }
                end

                do
                  local tbl29 = {
                    init = function()
                      return { push = function() end }
                    end,
                  }

                  local SideBar = {}
                  SideBar.__index = SideBar

                  SideBar.new = function(gui, theme)
                    local obj = setmetatable({}, SideBar)
                    obj.gui = gui
                    obj.theme = theme
                    obj.locked = false
                    obj.scale = 1
                    obj.buttons = {}
                    obj.base = { w = 60, h = 60, gap = 8, font = 10 }
                    obj._conns = {}
                    obj._press = nil
                    obj.onPositionChanged = nil
                    obj:_setupInput()

                    gui.Destroying:Connect(function()
                      for _, conn in ipairs(obj._conns) do
                        if conn.Connected then
                          conn:Disconnect()
                        end
                      end
                    end)

                    return obj
                  end

                  SideBar._layout = function(arg)
                    local currentCamera = workspace.CurrentCamera
                    currentCamera = currentCamera and currentCamera.ViewportSize or Vector2.new(1280, 720)

                    if currentCamera.X < 200 or currentCamera.Y < 200 then
                      currentCamera = Vector2.new(1280, 720)
                    end

                    local base = arg.base
                    local scale = arg.scale
                    local n35 = #arg.buttons
                    if n35 == 0 then
                      return
                    end
                    local n36 = base.w * scale
                    local n37 = base.h * scale
                    local n38 = (base.gap or 10) * scale
                    local v96 = math.ceil(n35 / (n35 > 6 and 2 or 1))
                    local n39 = currentCamera.X - 76 - n36 / 2
                    local n40 =
                      math.clamp(currentCamera.Y / 2 - (v96 * n37 + math.max(0, v96 - 1) * n38) / 2 + n37 / 2, 40, currentCamera.Y - 60)

                    for i, button in ipairs(arg.buttons) do
                      local floor2 = math.floor
                      button.btn.Position = UDim2.fromOffset(
                        math.floor(n39 - math.floor((i - 1) / v96) * (n36 + n38)),
                        floor2(n40 + (i - 1) % v96 * (n37 + n38))
                      )
                    end
                  end

                  local tbl30 = {
                    ["Neon Violet Glass"] = {
                      normalBg = Color3.fromRGB(0, 0, 0),
                      normalTrans = 0,
                      activeBg = Color3.fromRGB(150, 50, 255),
                      activeTrans = 0,
                      normalText = Color3.fromRGB(255, 255, 255),
                      activeText = Color3.fromRGB(12, 2, 14),
                      normalStroke = Color3.fromRGB(168, 85, 247),
                      normalStrokeTrans = 0.5,
                      activeStroke = Color3.fromRGB(255, 255, 255),
                      activeStrokeTrans = 0.1,
                      corner = 0.28,
                      font = Enum.Font.MontserratBlack,
                    },
                    ["Stealth Dark"] = {
                      normalBg = Color3.fromRGB(0, 0, 0),
                      normalTrans = 0,
                      activeBg = Color3.fromRGB(168, 85, 247),
                      activeTrans = 0,
                      normalText = Color3.fromRGB(255, 255, 255),
                      activeText = Color3.fromRGB(0, 0, 0),
                      normalStroke = Color3.fromRGB(40, 40, 45),
                      normalStrokeTrans = 0.4,
                      activeStroke = Color3.fromRGB(150, 140, 255),
                      activeStrokeTrans = 0.1,
                      corner = 0.24,
                      font = Enum.Font.MontserratBold,
                    },
                    ["Minimal Pill"] = {
                      normalBg = Color3.fromRGB(22, 16, 26),
                      normalTrans = 0.3,
                      activeBg = Color3.fromRGB(190, 32, 168),
                      activeTrans = 0,
                      normalText = Color3.fromRGB(240, 240, 250),
                      activeText = Color3.fromRGB(255, 255, 255),
                      normalStroke = Color3.fromRGB(120, 40, 130),
                      normalStrokeTrans = 0.6,
                      activeStroke = Color3.fromRGB(255, 100, 180),
                      activeStrokeTrans = 0.3,
                      corner = 0.5,
                      font = Enum.Font.MontserratBold,
                    },
                    ["Cyber Edge"] = {
                      normalBg = Color3.fromRGB(8, 8, 16),
                      normalTrans = 0.05,
                      activeBg = Color3.fromRGB(140, 30, 180),
                      activeTrans = 0,
                      normalText = Color3.fromRGB(255, 255, 255),
                      activeText = Color3.fromRGB(255, 255, 255),
                      normalStroke = Color3.fromRGB(80, 20, 120),
                      normalStrokeTrans = 0.3,
                      activeStroke = Color3.fromRGB(255, 255, 255),
                      activeStrokeTrans = 0.05,
                      corner = 0.16,
                      font = Enum.Font.MontserratBlack,
                    },
                    ["Violet Pulse"] = {
                      normalBg = Color3.fromRGB(12, 4, 18),
                      normalTrans = 0.15,
                      activeBg = Color3.fromRGB(190, 35, 200),
                      activeTrans = 0,
                      normalText = Color3.fromRGB(225, 160, 255),
                      activeText = Color3.fromRGB(255, 255, 255),
                      normalStroke = Color3.fromRGB(190, 32, 168),
                      normalStrokeTrans = 0.3,
                      activeStroke = Color3.fromRGB(255, 255, 255),
                      activeStrokeTrans = 0,
                      corner = 0.28,
                      font = Enum.Font.MontserratBlack,
                    },
                  }

                  SideBar.setStyle = function(arg, currentStyle)
                    arg.currentStyle = currentStyle

                    for _, button in ipairs(arg.buttons) do
                      if button.render then
                        button.render(button.state, true)
                      end
                    end
                  end

                  SideBar.addButton = function(arg, arg2, arg3, arg4)
                    if arg4 == nil then
                      arg4 = true
                    end

                    local n35 = arg.base.w * arg.scale
                    local n36 = arg.base.h * arg.scale

                    local TextButton = fn56("TextButton", {
                      AnchorPoint = Vector2.new(0.5, 0.5),
                      Size = UDim2.fromOffset(n35, n36),
                      BackgroundColor3 = Color3.fromRGB(0, 0, 0),
                      BackgroundTransparency = 0,
                      AutoButtonColor = false,
                      Text = "",
                      ClipsDescendants = true,
                      ZIndex = 41,
                      Parent = arg.gui,
                    })

                    local v96 = fn56("UICorner", { CornerRadius = UDim.new(0.28, 0), Parent = TextButton })
                    local UIScale = fn56("UIScale", { Scale = 1, Parent = TextButton })
                    local v97 = tbl27.attach(TextButton, Color3.fromRGB(25, 25, 30))
                    v97.stroke.Transparency = 0.65

                    local TextLabel = fn56("TextLabel", {
                      BackgroundTransparency = 1,
                      Position = UDim2.new(0, 5, 0, 4),
                      Size = UDim2.new(1, -8, 1, -8),
                      Font = Enum.Font.MontserratBlack,
                      Text = arg2,
                      TextSize = math.max(8, arg.base.font * arg.scale),
                      TextColor3 = Color3.fromRGB(255, 255, 255),
                      TextXAlignment = Enum.TextXAlignment.Center,
                      TextYAlignment = Enum.TextYAlignment.Center,
                      TextWrapped = true,
                      ZIndex = 42,
                      Parent = TextButton,
                    })

                    local function fn61(arg5, arg6)
                      local snappy = arg6 and Tween.Presets.Snappy or TweenInfo.new(0)
                      local mobileBtnStyle = State and State.mobileBtnStyle and tbl30[State.mobileBtnStyle] or tbl30["Neon Violet Glass"]
                      local activeBg = arg5 and mobileBtnStyle.activeBg or mobileBtnStyle.normalBg
                      local activeTrans = arg5 and mobileBtnStyle.activeTrans or mobileBtnStyle.normalTrans
                      local activeText = arg5 and mobileBtnStyle.activeText or mobileBtnStyle.normalText
                      v96.CornerRadius = UDim.new(mobileBtnStyle.corner or 0.28, 0)
                      TextLabel.Font = mobileBtnStyle.font or Enum.Font.MontserratBlack
                      Tween.to(TextButton, snappy, { BackgroundColor3 = activeBg, BackgroundTransparency = activeTrans })
                      Tween.to(TextLabel, snappy, { TextColor3 = activeText })

                      if v97 and v97.stroke then
                        v97.stroke.Color = arg5 and mobileBtnStyle.activeStroke or mobileBtnStyle.normalStroke
                        v97.stroke.Transparency = arg5 and mobileBtnStyle.activeStrokeTrans or mobileBtnStyle.normalStrokeTrans
                      end
                    end

                    local tbl31 = {
                      btn = TextButton,
                      label = TextLabel,
                      pressScale = UIScale,
                      ol = v97,
                      corner = v96,
                      state = false,
                      hovered = false,
                      text = arg2,
                      callback = arg3,
                      isToggle = arg4,
                      applyScale = function(arg5)
                        TextLabel.Size = UDim2.new(1, -8 * arg5, 1, -8 * arg5)
                        TextLabel.TextSize = math.max(8, arg.base.font * arg5)
                      end,
                      render = fn61,
                    }

                    tbl31.applyScale(arg.scale)

                    tbl31.setState = function(arg5)
                      if not tbl31.isToggle then
                        return
                      end
                      tbl31.state = not not arg5
                      fn61(tbl31.state, false)
                    end

                    tbl31.toggle = function()
                      if not tbl31.isToggle then
                        fn61(true, true)

                        task.delay(0.2, function()
                          fn61(false, true)
                        end)

                        if arg3 then
                          task.spawn(arg3, true)
                        end

                        return
                      end

                      tbl31.state = not tbl31.state
                      fn61(tbl31.state, true)

                      if arg3 then
                        task.spawn(arg3, tbl31.state)
                      end
                    end

                    fn61(false, false)

                    TextButton.MouseEnter:Connect(function()
                      tbl31.hovered = true

                      if not tbl31._pressed then
                        Tween.to(UIScale, Tween.Presets.Snappy, { Scale = 1.035 })
                      end
                    end)

                    TextButton.MouseLeave:Connect(function()
                      tbl31.hovered = false

                      if not tbl31._pressed then
                        Tween.to(UIScale, Tween.Presets.Snappy, { Scale = 1 })
                      end
                    end)

                    TextButton.InputBegan:Connect(function(input)
                      if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                        tbl31._pressed = true
                        TextButton.ZIndex = 43
                        arg._press = { entry = tbl31, input = input, start = input.Position, startPos = TextButton.Position, moved = false }
                        Tween.to(UIScale, Tween.Presets.Snappy, { Scale = 0.94 })
                      end
                    end)

                    table.insert(arg.buttons, tbl31)
                    arg:_layout()
                    return tbl31
                  end

                  SideBar._setupInput = function(arg)
                    table.insert(
                      arg._conns,
                      UserInputService.InputChanged:Connect(function(input)
                        local press = arg._press
                        if not press then
                          return
                        end

                        local isTouch = input.UserInputType == Enum.UserInputType.Touch
                        local isMouse = input.UserInputType == Enum.UserInputType.MouseMovement

                        if
                          (isTouch and input == press.input) or (isMouse and press.input.UserInputType == Enum.UserInputType.MouseButton1)
                        then
                          local n35 = input.Position - press.start
                          local threshold = isTouch and 14 or 6

                          if not arg.locked and (press.moved or n35.Magnitude > threshold) then
                            press.moved = true
                            local startPos = press.startPos
                            press.entry.btn.Position =
                              UDim2.new(startPos.X.Scale, startPos.X.Offset + n35.X, startPos.Y.Scale, startPos.Y.Offset + n35.Y)
                          end
                        end
                      end)
                    )

                    table.insert(
                      arg._conns,
                      UserInputService.InputEnded:Connect(function(input)
                        local press = arg._press
                        if not press then
                          return
                        end

                        local isTouch = input.UserInputType == Enum.UserInputType.Touch
                        local isMouse = input.UserInputType == Enum.UserInputType.MouseButton1

                        if
                          (isTouch and input == press.input) or (isMouse and press.input.UserInputType == Enum.UserInputType.MouseButton1)
                        then
                          local entry = press.entry
                          entry._pressed = false
                          entry.btn.ZIndex = 41
                          arg._press = nil
                          Tween.to(entry.pressScale, Tween.Presets.Spring, { Scale = entry.hovered and 1.035 or 1 })

                          if not press.moved then
                            entry.toggle()
                          elseif arg.onPositionChanged then
                            pcall(arg.onPositionChanged)
                          end
                        end
                      end)
                    )
                  end

                  SideBar.getPositions = function(arg)
                    local tbl31 = {}

                    for _, button in ipairs(arg.buttons) do
                      local position = button.btn.Position
                      tbl31[button.text] = { x = math.floor(position.X.Offset + 0.5), y = math.floor(position.Y.Offset + 0.5) }
                    end

                    return tbl31
                  end

                  SideBar.setPositions = function(arg, arg2)
                    if type(arg2) ~= "table" then
                      return
                    end

                    for _, button in ipairs(arg.buttons) do
                      local v96 = arg2[button.text]

                      if type(v96) == "table" and tonumber(v96.x) and tonumber(v96.y) then
                        button.btn.Position = UDim2.fromOffset(tonumber(v96.x), tonumber(v96.y))
                        arg._customPositions = true
                      end
                    end
                  end

                  SideBar.resetPositions = function(arg)
                    arg._customPositions = false
                    arg:_layout()
                  end

                  SideBar.setLocked = function(arg, locked)
                    arg.locked = locked
                  end

                  SideBar.setButtonVisible = function(arg, arg2, arg3)
                    for _, button in ipairs(arg.buttons) do
                      if button.text == arg2 then
                        button.visibleSetting = arg3 ~= false
                        button.btn.Visible = arg.visible ~= false and button.visibleSetting
                      end
                    end
                  end

                  SideBar.setVisible = function(arg, arg2)
                    arg.visible = arg2 ~= false

                    for _, button in ipairs(arg.buttons) do
                      button.btn.Visible = arg.visible and button.visibleSetting ~= false
                    end
                  end

                  SideBar.setScale = function(arg, arg2)
                    arg.scale = math.clamp(arg2, 0.5, 2)
                    local n35 = arg.base.w * arg.scale
                    local n36 = arg.base.h * arg.scale

                    for _, button in ipairs(arg.buttons) do
                      if not button._pressed then
                        button.btn.Size = UDim2.fromOffset(n35, n36)
                      end

                      if button.applyScale then
                        button.applyScale(arg.scale)
                      end

                      if button.render then
                        button.render(button.state, false)
                      end
                    end

                    if not arg._customPositions then
                      arg:_layout()
                    end
                  end

                  SideBar.applyTheme = function(arg)
                    for _, button in ipairs(arg.buttons) do
                      if button.render then
                        button.render(button.state, true)
                      end
                    end
                  end

                  Config = nil
                  _G.HD_RESETTING = false
                  saveConfig = nil
                  index = {}
                  index.__index = index

                  index.new = function(arg)
                    local tbl31 = arg or {}
                    local obj = setmetatable({}, index)
                    obj.theme = Theme.new(tbl31.theme or "Midnight")
                    obj.tabs = {}
                    obj.activeTab = nil
                    obj._conns = {}
                    obj.minW = 400
                    obj.minH = 360
                    obj._bgIndex = tbl31.background or 1
                    obj.bgTransparency = tbl31.imageTransparency or 0.5
                    local playerGui2 = localPlayer:WaitForChild("PlayerGui")
                    local v96 = playerGui2:FindFirstChild("GlassUI")

                    if v96 then
                      v96:Destroy()
                    end

                    fn59()
                    obj._playerGui = playerGui2

                    obj.gui = fn56("ScreenGui", {
                      Name = "GlassUI",
                      ResetOnSpawn = false,
                      IgnoreGuiInset = true,
                      ZIndexBehavior = Enum.ZIndexBehavior.Sibling,
                      Parent = playerGui2,
                    })

                    local width = tbl31.width or 560
                    local height = tbl31.height or 660
                    obj._w = width
                    obj._h = height
                    local h = obj._h
                    obj._baseW = obj._w
                    obj._baseH = h

                    obj.main = fn56("Frame", {
                      Name = "Main",
                      AnchorPoint = Vector2.new(0.5, 0.5),
                      Position = UDim2.fromScale(0.5, 0.5),
                      Size = UDim2.fromOffset(obj._w, obj._h),
                      BackgroundColor3 = Color3.fromRGB(12, 3, 12),
                      BackgroundTransparency = 0.1,
                      ClipsDescendants = true,
                      Parent = obj.gui,
                    })

                    obj.scaleInstance = fn56("UIScale", { Scale = 1, Parent = obj.main })
                    fn57(30, obj.main)

                    obj.bg = fn56("ImageLabel", {
                      Name = "Backdrop",
                      BackgroundTransparency = 1,
                      Image = Assets.Backgrounds[1] or "",
                      ScaleType = Enum.ScaleType.Crop,
                      Position = UDim2.fromScale(0, 0),
                      Size = UDim2.fromScale(1, 1),
                      ImageTransparency = 0,
                      ZIndex = 1,
                      Parent = obj.main,
                    })

                    fn57(30, obj.bg)

                    task.spawn(function()
                      if BACKGROUND_ID ~= "" then
                        return
                      end

                      for i = 1, 3 do
                        local png = fn55("https://files.catbox.moe/a2goit.png", "hookduels_bg_custom.png")

                        if obj.bg and png and png ~= "" then
                          obj.bg.Image = png
                          break
                        else
                          task.wait(0.5)
                        end
                      end
                    end)

                    local Frame = fn56("Frame", {
                      Name = "Glow",
                      BackgroundColor3 = Color3.fromRGB(10, 2, 10),
                      BackgroundTransparency = 0.45,
                      BorderSizePixel = 0,
                      Size = UDim2.fromScale(1, 1),
                      ZIndex = 2,
                      Parent = obj.main,
                    })

                    fn57(30, Frame)
                    local v97 = fn56
                    local tbl32 = { Rotation = 90 }
                    local numberSequence = NumberSequence.new
                    local tbl33 = {}
                    local v98 = NumberSequenceKeypoint.new(0, 0.35)
                    local v99 = NumberSequenceKeypoint.new(0.6, 0.25)
                    tbl33[1] = v98
                    tbl33[2] = v99

                    do
                      local values = table.pack(NumberSequenceKeypoint.new(1, 0.2))
                      table.move(values, 1, values.n, 3, tbl33)
                    end

                    tbl32.Transparency = numberSequence(tbl33)
                    tbl32.Parent = Frame
                    v97("UIGradient", tbl32)
                    obj.outline = tbl27.attach(obj.main, obj.theme.Data.Accent)
                    obj.theme:BindAccent(obj.outline.stroke, "Color")
                    obj.outline.stroke.Transparency = 0.05
                    obj.outline.stroke.Thickness = 2.2
                    obj.particles = tbl28.attach(obj.main, obj.theme.Data.Accent, 20)
                    obj.notify = tbl29.init(obj.gui, obj.theme)
                    obj.sidebar = SideBar.new(obj.gui, obj.theme)
                    obj.layout = tbl31.layout or 1
                    obj:_buildChrome(tbl31)
                    obj:_setupDrag()
                    obj:_setupResize()
                    return obj
                  end
                end
              end

              index._buildChrome = function(arg)
                local theme = arg.theme

                arg.titleBar = fn56("Frame", {
                  Name = "TitleBar",
                  Size = UDim2.new(1, 0, 0, 58),
                  BackgroundTransparency = 1,
                  ZIndex = 5,
                  Parent = arg.main,
                })

                local ImageLabel = fn56("ImageLabel", {
                  Name = "Logo",
                  Size = UDim2.fromOffset(34, 34),
                  Position = UDim2.fromOffset(15, 12),
                  BackgroundTransparency = 1,
                  Image = fn55("https://files.catbox.moe/et2mq4.png", "hookduels_logo.png"),
                  ScaleType = Enum.ScaleType.Fit,
                  ZIndex = 8,
                  Parent = arg.titleBar,
                })

                fn57(12, ImageLabel)

                local Frame = fn56("Frame", {
                  Name = "Logo",
                  Size = UDim2.fromOffset(40, 40),
                  Position = UDim2.fromOffset(16, 10),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.25,
                  BorderSizePixel = 0,
                  ZIndex = 5,
                  Parent = arg.titleBar,
                })

                fn57(12, Frame)
                theme:Bind(Frame, "BackgroundColor3", "Panel")
                theme:BindAccent(
                  fn56("UIStroke", { Thickness = 1.2, Color = theme.Data.Accent, Transparency = 0.45, Parent = Frame }),
                  "Color"
                )

                task.spawn(function()
                  local png = fn55("https://files.catbox.moe/et2mq4.png", "hookduels_logo.png")

                  if ImageLabel and png and png ~= "" then
                    ImageLabel.Image = png
                  end
                end)

                theme:BindAccent(
                  fn56("TextLabel", {
                    BackgroundTransparency = 1,
                    Position = UDim2.fromOffset(58, 12),
                    Size = UDim2.new(1, -170, 0, 20),
                    Font = Enum.Font.MontserratBlack,
                    Text = "Hook Duels",
                    TextSize = 15,
                    TextColor3 = Color3.fromRGB(255, 255, 255),
                    TextXAlignment = Enum.TextXAlignment.Left,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 6,
                    Parent = arg.titleBar,
                  }),
                  "TextColor3"
                )

                theme:Bind(
                  fn56("TextLabel", {
                    BackgroundTransparency = 1,
                    Position = UDim2.fromOffset(58, 30),
                    Size = UDim2.new(1, -28, 0, 15),
                    Font = Enum.Font.MontserratBold,
                    Text = "o luquinhas ama o piru do João",
                    TextSize = 10,
                    TextColor3 = Color3.fromRGB(192, 132, 252),
                    TextXAlignment = Enum.TextXAlignment.Left,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 6,
                    Parent = arg.titleBar,
                  }),
                  "TextColor3",
                  "Sub"
                )

                local v96 = fn56("TextButton", {
                  Name = "MinimizeBtn",
                  AnchorPoint = Vector2.new(1, 0.5),
                  Position = UDim2.new(1, -16, 0.5, 0),
                  Size = UDim2.fromOffset(32, 32),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.3,
                  AutoButtonColor = false,
                  Font = Enum.Font.MontserratBold,
                  Text = "—",
                  TextSize = 16,
                  TextColor3 = Color3.fromRGB(255, 255, 255),
                  ZIndex = 7,
                  Parent = arg.titleBar,
                })

                fn57(8, v96)
                theme:Bind(v96, "BackgroundColor3", "Panel")
                local v97 = "Color"
                theme:BindAccent(fn56("UIStroke", { Thickness = 1.2, Color = theme.Data.Accent, Transparency = 0.6, Parent = v96 }), v97)

                v96.MouseButton1Click:Connect(function()
                  arg:minimize()
                  v96.Text = arg._minimized and "+" or "—"
                end)

                local Frame2 = fn56("Frame", {
                  AnchorPoint = Vector2.new(0.5, 1),
                  Position = UDim2.new(0.5, 0, 1, 0),
                  Size = UDim2.new(1, -32, 0, 1),
                  BackgroundColor3 = theme.Data.Accent,
                  BackgroundTransparency = 0.64,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.titleBar,
                })

                theme:BindAccent(Frame2, "BackgroundColor3")
                local v98 = fn56
                local tbl29 = {}
                local numberSequence = NumberSequence.new
                local tbl30 = {}
                local v99 = NumberSequenceKeypoint.new(0, 1)
                local v100 = NumberSequenceKeypoint.new(0.5, 0)
                local new = NumberSequenceKeypoint.new
                tbl30[1] = v99
                tbl30[2] = v100

                do
                  local values = table.pack(new(1, 1))
                  table.move(values, 1, values.n, 3, tbl30)
                end

                tbl29.Transparency = numberSequence(tbl30)
                tbl29.Parent = Frame2
                v98("UIGradient", tbl29)

                arg.content = fn56("Frame", {
                  Name = "Content",
                  Position = UDim2.fromOffset(20, 110),
                  Size = UDim2.new(1, -40, 1, -130),
                  BackgroundTransparency = 1,
                  ZIndex = 10,
                  Parent = arg.main,
                })

                arg.headerCard = fn56("Frame", {
                  Name = "PageHeader",
                  Size = UDim2.new(1, 0, 0, 56),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.5,
                  BorderSizePixel = 0,
                  ZIndex = 5,
                  Parent = arg.content,
                })

                fn57(12, arg.headerCard)
                tbl26.apply(arg.headerCard, { transparency = 0.5 })
                theme:Bind(arg.headerCard, "BackgroundColor3", "Panel")

                arg.headerTitle = fn56("TextLabel", {
                  BackgroundTransparency = 1,
                  Position = UDim2.fromOffset(14, 4),
                  Size = UDim2.new(1, -28, 0, 28),
                  Font = Enum.Font.MontserratBold,
                  Text = "",
                  TextSize = 15,
                  TextColor3 = Color3.fromRGB(255, 255, 255),
                  TextXAlignment = Enum.TextXAlignment.Left,
                  TextTruncate = Enum.TextTruncate.AtEnd,
                  ZIndex = 6,
                  Parent = arg.headerCard,
                })

                theme:Bind(arg.headerTitle, "TextColor3", "Text")

                arg.headerSub = fn56("TextLabel", {
                  BackgroundTransparency = 1,
                  Position = UDim2.fromOffset(14, 28),
                  Size = UDim2.new(1, -28, 0, 20),
                  Font = Enum.Font.MontserratBold,
                  Text = "",
                  TextSize = 10,
                  TextColor3 = Color3.fromRGB(200, 165, 180),
                  TextXAlignment = Enum.TextXAlignment.Left,
                  TextTruncate = Enum.TextTruncate.AtEnd,
                  ZIndex = 8,
                  Parent = arg.headerCard,
                })

                theme:Bind(arg.headerSub, "TextColor3", "Sub")

                arg.headerDivider = fn56("Frame", {
                  AnchorPoint = Vector2.new(0.5, 1),
                  Position = UDim2.new(0.5, 0, 1, 0),
                  Size = UDim2.new(1, -28, 0, 1),
                  BackgroundColor3 = theme.Data.Accent,
                  BackgroundTransparency = 0.72,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.headerCard,
                })

                theme:BindAccent(arg.headerDivider, "BackgroundColor3")

                arg.pageHost = fn56("Frame", {
                  Name = "PageHost",
                  Position = UDim2.fromOffset(0, 62),
                  Size = UDim2.new(1, 0, 1, -62),
                  BackgroundTransparency = 1,
                  ClipsDescendants = true,
                  ZIndex = 5,
                  Parent = arg.content,
                })

                arg.resizeHandle = fn56("TextButton", {
                  AnchorPoint = Vector2.new(1, 1),
                  Position = UDim2.new(1, -10, 1, -10),
                  Size = UDim2.fromOffset(22, 22),
                  BackgroundTransparency = 1,
                  AutoButtonColor = false,
                  Text = "",
                  ZIndex = 9,
                  Parent = arg.main,
                })

                for _, v101 in ipairs({ { 0.9, 14 }, { 0.82, 8 } }) do
                  theme:Bind(
                    fn56("Frame", {
                      BackgroundColor3 = theme.Data.Sub,
                      BackgroundTransparency = 0.35,
                      BorderSizePixel = 0,
                      AnchorPoint = Vector2.new(0.5, 0.5),
                      Position = UDim2.fromScale(v101[1], v101[1]),
                      Size = UDim2.fromOffset(v101[2], 2),
                      Rotation = -45,
                      ZIndex = 9,
                      Parent = arg.resizeHandle,
                    }, { fn56("UICorner", { CornerRadius = UDim.new(1, 0) }) }),
                    "BackgroundColor3",
                    "Sub"
                  )
                end
              end

              index.Tab = function(arg, arg2, arg3)
                local theme = arg.theme
                local n35 = #arg.tabs + 1

                local CanvasGroup = fn56("CanvasGroup", {
                  BackgroundTransparency = 1,
                  Size = UDim2.fromScale(1, 1),
                  GroupTransparency = 0,
                  Visible = false,
                  ZIndex = 5,
                  Parent = arg.pageHost,
                })

                local v96 = fn56("ScrollingFrame", {
                  BackgroundTransparency = 1,
                  Size = UDim2.fromScale(1, 1),
                  ScrollBarThickness = 3,
                  ScrollBarImageColor3 = theme.Data.Accent,
                  ScrollBarImageTransparency = 0.4,
                  CanvasSize = UDim2.new(),
                  AutomaticCanvasSize = Enum.AutomaticSize.None,
                  ZIndex = 5,
                  Parent = CanvasGroup,
                })

                theme:BindAccent(v96, "ScrollBarImageColor3")
                fn56("UIListLayout", { Padding = UDim.new(0, 10), SortOrder = Enum.SortOrder.LayoutOrder, Parent = v96 })

                fn56("UIPadding", {
                  PaddingTop = UDim.new(0, 2),
                  PaddingBottom = UDim.new(0, 12),
                  PaddingRight = UDim.new(0, 6),
                  Parent = v96,
                })

                local tbl29 = { name = arg2, desc = arg3 or "", group = CanvasGroup, page = v96, index = n35, navBtn = nil }
                arg.tabs[n35] = tbl29
                local v97 = v96
                local n36 = 0

                local function fn61()
                  return v97 or v96
                end

                local api

                api = {
                  Button = function(arg4, arg5, arg6)
                    return Components.Button(theme, fn61(), arg5, arg6)
                  end,
                  Toggle = function(arg4, arg5, arg6, arg7)
                    return Components.Toggle(theme, fn61(), arg5, arg6, arg7)
                  end,
                  Slider = function(arg4, arg5, arg6, arg7, arg8, arg9, arg10)
                    return Components.Slider(theme, fn61(), arg5, arg6, arg7, arg8, arg9, arg10)
                  end,
                  Dropdown = function(arg4, arg5, arg6, arg7, arg8)
                    return Components.Dropdown(theme, fn61(), arg5, arg6, arg7, arg8)
                  end,
                  Input = function(arg4, arg5, arg6, arg7)
                    return Components.Input(theme, fn61(), arg5, arg6, arg7)
                  end,
                  Keybind = function(arg4, arg5, arg6, arg7)
                    return Components.Keybind(theme, fn61(), arg5, arg6, arg7)
                  end,
                  Stepper = function(arg4, arg5, arg6, arg7, arg8, arg9, arg10)
                    return Components.Stepper(theme, fn61(), arg5, arg6, arg7, arg8, arg9, arg10)
                  end,
                  Section = function(arg4, arg5)
                    n36 += 1

                    local v98 = fn56("Frame", {
                      Name = "Section",
                      Size = UDim2.new(1, 0, 0, 0),
                      AutomaticSize = Enum.AutomaticSize.Y,
                      BackgroundColor3 = theme.Data.Panel,
                      BackgroundTransparency = 1,
                      BorderSizePixel = 0,
                      LayoutOrder = n36,
                      ClipsDescendants = true,
                      Parent = v96,
                    })

                    fn57(14, v98)
                    theme:Bind(v98, "BackgroundColor3", "Panel")
                    theme:BindAccent(
                      fn56("UIStroke", { Thickness = 1, Color = theme.Data.Accent, Transparency = 1, Parent = v98 }),
                      "Color"
                    )

                    fn56("UIListLayout", {
                      Padding = UDim.new(0, 0),
                      HorizontalAlignment = Enum.HorizontalAlignment.Center,
                      SortOrder = Enum.SortOrder.LayoutOrder,
                      Parent = v98,
                    })

                    local Frame = fn56("Frame", {
                      Name = "SectionHeader",
                      Size = UDim2.new(1, 0, 0, 38),
                      BackgroundTransparency = 1,
                      BorderSizePixel = 0,
                      LayoutOrder = 1,
                      Parent = v98,
                    })

                    local v99 = fn56("Frame", {
                      AnchorPoint = Vector2.new(0, 0.5),
                      Position = UDim2.new(0, 14, 0.5, 0),
                      Size = UDim2.fromOffset(5, 20),
                      BackgroundColor3 = theme.Data.Accent,
                      BorderSizePixel = 0,
                      ZIndex = 2,
                      Parent = Frame,
                    })

                    fn57(2, v99)
                    theme:BindAccent(v99, "BackgroundColor3")

                    theme:Bind(
                      fn56("TextLabel", {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(32, 0),
                        Size = UDim2.new(1, -46, 1, 0),
                        Font = Enum.Font.MontserratBold,
                        Text = arg5,
                        TextSize = 13,
                        TextColor3 = Color3.fromRGB(255, 255, 255),
                        TextXAlignment = Enum.TextXAlignment.Left,
                        TextYAlignment = Enum.TextYAlignment.Center,
                        TextTruncate = Enum.TextTruncate.AtEnd,
                        ZIndex = 2,
                        Parent = Frame,
                      }),
                      "TextColor3",
                      "Text"
                    )

                    local v100 = "BackgroundColor3"

                    theme:BindAccent(
                      fn56("Frame", {
                        AnchorPoint = Vector2.new(0.5, 1),
                        Position = UDim2.new(0.5, 0, 1, 0),
                        Size = UDim2.new(1, -24, 0, 2),
                        BackgroundColor3 = theme.Data.Accent,
                        BackgroundTransparency = 0.25,
                        BorderSizePixel = 0,
                        ZIndex = 2,
                        Parent = Frame,
                      }),
                      v100
                    )

                    local Frame2 = fn56("Frame", {
                      Name = "SectionBody",
                      Size = UDim2.new(1, -12, 0, 0),
                      AutomaticSize = Enum.AutomaticSize.Y,
                      BackgroundTransparency = 1,
                      BorderSizePixel = 0,
                      LayoutOrder = 2,
                      Parent = v98,
                    })

                    fn56("UIListLayout", { Padding = UDim.new(0, 5), SortOrder = Enum.SortOrder.LayoutOrder, Parent = Frame2 })
                    fn56("UIPadding", { PaddingTop = UDim.new(0, 8), PaddingBottom = UDim.new(0, 8), Parent = Frame2 })
                    v97 = Frame2
                    return v98
                  end,
                  Note = function(arg4, arg5)
                    local v98 = fn56("Frame", {
                      Size = UDim2.new(1, 0, 0, 38),
                      BackgroundColor3 = theme.Data.Accent,
                      BackgroundTransparency = 0.9,
                      BorderSizePixel = 0,
                      Parent = fn61(),
                    })

                    fn57(10, v98)
                    theme:BindAccent(v98, "BackgroundColor3")

                    theme:Bind(
                      fn56("TextLabel", {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(12, 0),
                        Size = UDim2.new(1, -24, 1, 0),
                        Font = Enum.Font.Montserrat,
                        Text = arg5,
                        TextSize = 10,
                        TextColor3 = theme.Data.Sub,
                        TextWrapped = true,
                        TextXAlignment = Enum.TextXAlignment.Left,
                        TextYAlignment = Enum.TextYAlignment.Center,
                        ZIndex = 2,
                        Parent = v98,
                      }),
                      "TextColor3",
                      "Sub"
                    )

                    return v98
                  end,
                  Label = function(arg4, arg5)
                    return api:Section(arg5)
                  end,
                }

                tbl29.api = api

                if n35 == 1 then
                  arg:SelectTab(1)
                end

                return api
              end

              index.FinalizeBuild = function(arg)
                if arg._finalized then
                  return
                end
                arg._finalized = true
                arg:_rebuildNav()

                for _, tab in ipairs(arg.tabs) do
                  tab.page.AutomaticCanvasSize = Enum.AutomaticSize.Y
                end

                arg.gui.Parent = arg._playerGui
                arg:_playOpen()
              end

              index.SelectTab = function(arg, arg2)
                local v96 = arg.tabs[arg2]
                if not v96 or arg.activeTab == v96 then
                  return
                end

                if arg.activeTab then
                  local group = arg.activeTab.group
                  Tween.to(group, Tween.Presets.Snappy, { GroupTransparency = 1, Position = UDim2.fromOffset(-24, 0) })

                  task.delay(0.16, function()
                    if arg.activeTab and arg.activeTab.group ~= group then
                      group.Visible = false
                    end
                  end)
                end

                arg.activeTab = v96
                arg.headerTitle.Text = v96.name
                arg.headerSub.Text = v96.desc
                arg:_highlightNav()
                v96.group.Visible = true
                v96.group.GroupTransparency = 1
                v96.group.Position = UDim2.fromOffset(24, 0)
                Tween.to(v96.group, Tween.Presets.Smooth, { GroupTransparency = 0, Position = UDim2.fromOffset(0, 0) })
              end

              index._applyLayout = function(arg)
                local layout = arg.layout
                local visible = true

                if layout == 2 then
                  arg.content.Position = UDim2.fromOffset(188, 64)
                  arg.content.Size = UDim2.new(1, -200, 1, -76)
                elseif layout == 3 then
                  arg.content.Position = UDim2.fromOffset(20, 118)
                  arg.content.Size = UDim2.new(1, -40, 1, -130)
                  visible = false
                elseif layout == 5 then
                  arg.content.Position = UDim2.fromOffset(20, 64)
                  arg.content.Size = UDim2.new(1, -40, 1, -118)
                elseif layout == 10 then
                  arg.content.Position = UDim2.fromOffset(20, 64)
                  arg.content.Size = UDim2.new(1, -200, 1, -76)
                elseif layout == 8 then
                  arg.content.Position = UDim2.fromOffset(20, 110)
                  arg.content.Size = UDim2.new(1, -40, 1, -122)
                elseif layout == 7 then
                  arg.content.Position = UDim2.fromOffset(82, 62)
                  arg.content.Size = UDim2.new(1, -98, 1, -76)
                elseif layout == 8 then
                  arg.content.Position = UDim2.fromOffset(20, 64)
                  arg.content.Size = UDim2.new(1, -102, 1, -76)
                elseif layout == 9 then
                  arg.content.Position = UDim2.fromOffset(20, 110)
                  arg.content.Size = UDim2.new(1, -40, 1, -122)
                elseif layout == 10 then
                  arg.content.Position = UDim2.fromOffset(82, 62)
                  arg.content.Size = UDim2.new(1, -102, 1, -76)
                elseif layout == 11 then
                  arg.content.Position = UDim2.fromOffset(20, 64)
                  arg.content.Size = UDim2.new(1, -40, 1, -122)
                  visible = false
                elseif layout == 16 then
                  arg.content.Position = UDim2.fromOffset(20, 64)
                  arg.content.Size = UDim2.new(1, -40, 1, -118)
                elseif layout == 13 then
                  arg.content.Position = UDim2.fromOffset(20, 64)
                  arg.content.Size = UDim2.new(1, -40, 1, -76)
                  visible = false
                elseif layout == 14 then
                  arg.content.Position = UDim2.fromOffset(20, 64)
                  arg.content.Size = UDim2.new(1, -40, 1, -126)
                elseif layout == 15 then
                  arg.content.Position = UDim2.fromOffset(20, 110)
                  arg.content.Size = UDim2.new(1, -40, 1, -122)
                elseif layout == 16 then
                  arg.content.Position = UDim2.fromOffset(52, 64)
                  arg.content.Size = UDim2.new(1, -72, 1, -130)
                else
                  arg.content.Position = UDim2.fromOffset(20, 110)
                  arg.content.Size = UDim2.new(1, -40, 1, -122)
                end

                arg.headerTitle.Visible = visible
                arg.headerSub.Visible = visible
                arg.headerDivider.Visible = visible

                if arg.headerCard then
                  arg.headerCard.Visible = visible
                end

                if visible then
                  arg.pageHost.Position = UDim2.fromOffset(0, 62)
                  arg.pageHost.Size = UDim2.new(1, 0, 1, -62)
                else
                  arg.pageHost.Position = UDim2.fromOffset(0, 0)
                  arg.pageHost.Size = UDim2.new(1, 0, 1, 0)
                end
              end

              index._buildPillNav = function(arg, arg2)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  Position = arg2 and UDim2.new(0, 16, 1, -52) or UDim2.fromOffset(16, 62),
                  Size = UDim2.new(1, -32, 0, 42),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.55,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(12, Frame)
                tbl26.apply(Frame, { transparency = 0.55 })
                theme:Bind(Frame, "BackgroundColor3", "Panel")
                theme:BindAccent(
                  fn56("UIStroke", { Thickness = 1, Color = theme.Data.Accent, Transparency = 0.8, Parent = Frame }),
                  "Color"
                )

                fn56("UIPadding", {
                  PaddingTop = UDim.new(0, 4),
                  PaddingBottom = UDim.new(0, 4),
                  PaddingLeft = UDim.new(0, 4),
                  PaddingRight = UDim.new(0, 4),
                  Parent = Frame,
                })

                fn56("UIListLayout", {
                  FillDirection = Enum.FillDirection.Horizontal,
                  Padding = UDim.new(0, 4),
                  HorizontalAlignment = Enum.HorizontalAlignment.Center,
                  VerticalAlignment = Enum.VerticalAlignment.Center,
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  Parent = Frame,
                })

                arg._nav = Frame
                local n35 = math.max(1, #arg.tabs)
                local n36 = (-8 - 4 * (n35 - 1)) / n35

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.new(1 / n35, n36, 1, -8),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 1,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = tab.name,
                    TextSize = 11,
                    TextColor3 = theme.Data.Sub,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 7,
                    ClipsDescendants = true,
                    Parent = Frame,
                  })

                  fn57(8, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")

                  local Frame2 = fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 1),
                    Position = UDim2.new(0.5, 0, 1, -1),
                    Size = UDim2.new(0, 0, 0, 2.5),
                    BackgroundColor3 = theme.Data.Accent,
                    BorderSizePixel = 0,
                    ZIndex = 8,
                    Parent = TextButton,
                  })

                  fn57(2, Frame2)
                  theme:BindAccent(Frame2, "BackgroundColor3")
                  tab.navIndicator = Frame2
                  local v96 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.4, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 1, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v96.index)
                  end)

                  tab.navBtn = TextButton
                end
              end

              index._buildRailNav = function(arg, arg2)
                local theme = arg.theme

                local v96 = fn56("Frame", {
                  Name = "Nav",
                  Position = arg2 == "right" and UDim2.new(1, -172, 0, 64) or UDim2.fromOffset(16, 64),
                  Size = UDim2.new(0, 160, 1, -76),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.58,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(14, v96)
                tbl26.apply(v96, { transparency = 0.58, reflection = false })
                theme:Bind(v96, "BackgroundColor3", "Panel")
                v96.ClipsDescendants = true

                local Frame = fn56("Frame", {
                  Name = "TabButtons",
                  BackgroundTransparency = 1,
                  Position = UDim2.new(0, 0, 0, 100),
                  Size = UDim2.new(1, 0, 0, 0),
                  AutomaticSize = Enum.AutomaticSize.Y,
                  ZIndex = 7,
                  Parent = v96,
                })

                fn56("UIListLayout", {
                  Padding = UDim.new(0, 22),
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  HorizontalAlignment = Enum.HorizontalAlignment.Center,
                  Parent = Frame,
                })

                local TextLabel = fn56("TextLabel", {
                  Name = "RailFoot",
                  AnchorPoint = Vector2.new(0.5, 1),
                  Position = UDim2.new(0.5, 0, 1, -8),
                  Size = UDim2.new(1, -16, 0, 18),
                  BackgroundTransparency = 1,
                  Font = Enum.Font.MontserratBlack,
                  Text = "HOOK DUELS",
                  TextSize = 12,
                  TextColor3 = Color3.fromRGB(255, 255, 255),
                  ZIndex = 10,
                  Parent = v96,
                })

                local Frame2 = fn56("Frame", {
                  AnchorPoint = Vector2.new(0.5, 0),
                  Position = UDim2.new(0.5, 0, 1, 1),
                  Size = UDim2.new(0, 64, 0, 2),
                  BackgroundColor3 = theme.Data.Accent,
                  BorderSizePixel = 0,
                  ZIndex = 7,
                  Parent = TextLabel,
                })

                fn57(1, Frame2)
                theme:BindAccent(Frame2, "BackgroundColor3")
                arg._nav = v96

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.fromOffset(120, 48),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 1,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = tab.name,
                    TextSize = 12,
                    TextColor3 = theme.Data.Sub,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 7,
                    Parent = Frame,
                  })

                  fn57(14, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")
                  tab.navIndicator = nil
                  local v97 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v97 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.9, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v97 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 1, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v97.index)
                  end)

                  tab.navBtn = TextButton
                end
              end

              index._buildArrowNav = function(arg)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  Position = UDim2.fromOffset(16, 64),
                  Size = UDim2.new(1, -32, 0, 48),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.3,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(12, Frame)
                tbl26.apply(Frame, { transparency = 0.3 })
                theme:Bind(Frame, "BackgroundColor3", "Panel")
                arg._nav = Frame

                local function fn61(arg2)
                  local TextButton = fn56("TextButton", {
                    AnchorPoint = Vector2.new(arg2 < 0 and 0 or 1, 0.5),
                    Position = UDim2.new(arg2 < 0 and 0 or 1, arg2 < 0 and 8 or -8, 0.5, 0),
                    Size = UDim2.fromOffset(34, 34),
                    BackgroundColor3 = theme.Data.Bg,
                    BackgroundTransparency = 0.3,
                    AutoButtonColor = false,
                    Text = "",
                    ZIndex = 7,
                    Parent = Frame,
                  })

                  fn57(9, TextButton)
                  theme:Bind(TextButton, "BackgroundColor3", "Bg")
                  local v96 = "Color"
                  theme:BindAccent(
                    fn56("UIStroke", { Thickness = 1, Color = theme.Data.Accent, Transparency = 0.82, Parent = TextButton }),
                    v96
                  )
                  local v97 = fn58(TextButton, theme.Data.Accent, 12)
                  v97.AnchorPoint = Vector2.new(0.5, 0.5)
                  v97.Position = UDim2.fromScale(0.5, 0.5)
                  v97.Rotation = arg2 < 0 and 90 or -90
                  v97.ZIndex = 8

                  for _, child in ipairs(v97:GetChildren()) do
                    if child:IsA("Frame") then
                      theme:BindAccent(child, "BackgroundColor3")
                    end
                  end

                  TextButton.MouseEnter:Connect(function()
                    Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0 })
                  end)

                  TextButton.MouseLeave:Connect(function()
                    Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.3 })
                  end)

                  TextButton.MouseButton1Down:Connect(function()
                    Tween.to(TextButton, Tween.Presets.Snappy, { Size = UDim2.fromOffset(30, 30) })
                  end)

                  TextButton.MouseButton1Up:Connect(function()
                    Tween.to(TextButton, Tween.Presets.Spring, { Size = UDim2.fromOffset(34, 34) })
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    local n35 = #arg.tabs
                    if n35 == 0 then
                      return
                    end
                    arg:SelectTab(((arg.activeTab and arg.activeTab.index or 1) - 1 + arg2) % n35 + 1)
                  end)

                  return TextButton
                end

                fn61(-1)
                fn61(1)

                arg._arrowLabel = fn56("TextLabel", {
                  AnchorPoint = Vector2.new(0.5, 0.5),
                  Position = UDim2.new(0.5, 0, 0.5, -5),
                  Size = UDim2.new(1, -104, 0, 20),
                  BackgroundTransparency = 1,
                  Font = Enum.Font.MontserratBold,
                  Text = "",
                  TextSize = 15,
                  TextColor3 = theme.Data.Text,
                  TextTruncate = Enum.TextTruncate.AtEnd,
                  ZIndex = 10,
                  Parent = Frame,
                })

                theme:Bind(arg._arrowLabel, "TextColor3", "Text")

                arg._arrowCounter = fn56("TextLabel", {
                  AnchorPoint = Vector2.new(0.5, 0.5),
                  Position = UDim2.new(0.5, 0, 0.5, 12),
                  Size = UDim2.new(1, -104, 0, 12),
                  BackgroundTransparency = 1,
                  Font = Enum.Font.MontserratBold,
                  Text = "",
                  TextSize = 9,
                  TextColor3 = theme.Data.Accent,
                  ZIndex = 7,
                  Parent = Frame,
                })

                theme:BindAccent(arg._arrowCounter, "TextColor3")
              end

              index._buildDropdownNav = function(arg, arg2)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  Position = arg2 and UDim2.new(0, 16, 1, -52) or UDim2.fromOffset(20, 62),
                  Size = UDim2.new(1, -32, 0, 42),
                  BackgroundTransparency = 1,
                  ZIndex = 8,
                  Parent = arg.main,
                })

                arg._nav = Frame

                local v96 = fn56("TextButton", {
                  Size = UDim2.new(1, 0, 0, 38),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.54,
                  AutoButtonColor = false,
                  Text = "",
                  ZIndex = 9,
                  Parent = Frame,
                })

                fn57(12, v96)
                tbl26.apply(v96, { transparency = 0.54 })
                theme:Bind(v96, "BackgroundColor3", "Panel")

                local Frame2 = fn56("Frame", {
                  AnchorPoint = Vector2.new(0, 0.5),
                  Position = UDim2.new(0, 10, 0.5, 0),
                  Size = UDim2.fromOffset(3, 18),
                  BackgroundColor3 = theme.Data.Accent,
                  BorderSizePixel = 0,
                  ZIndex = 10,
                  Parent = v96,
                })

                fn57(2, Frame2)
                theme:BindAccent(Frame2, "BackgroundColor3")

                arg._dropHeadLabel = fn56("TextLabel", {
                  BackgroundTransparency = 1,
                  Position = UDim2.fromOffset(22, 0),
                  Size = UDim2.new(1, -58, 1, 0),
                  Font = Enum.Font.MontserratBold,
                  Text = arg.activeTab and arg.activeTab.name or "",
                  TextSize = 16,
                  TextColor3 = theme.Data.Text,
                  TextXAlignment = Enum.TextXAlignment.Left,
                  TextTruncate = Enum.TextTruncate.AtEnd,
                  ZIndex = 10,
                  Parent = v96,
                })

                theme:Bind(arg._dropHeadLabel, "TextColor3", "Text")
                local v97 = fn58(v96, theme.Data.Accent, 12)
                v97.AnchorPoint = Vector2.new(1, 0.5)
                v97.Position = UDim2.new(1, -14, 0.5, 0)
                v97.ZIndex = 10

                for _, child in ipairs(v97:GetChildren()) do
                  if child:IsA("Frame") then
                    theme:BindAccent(child, "BackgroundColor3")
                  end
                end

                local Frame3 = fn56("Frame", {
                  Size = UDim2.new(1, 0, 0, 0),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.2,
                  ClipsDescendants = true,
                  ZIndex = 9,
                  Parent = Frame,
                })

                if arg2 then
                  Frame3.AnchorPoint = Vector2.new(0, 1)
                  Frame3.Position = UDim2.new(0, 0, 0, -5)
                else
                  Frame3.Position = UDim2.fromOffset(0, 2)
                end

                fn57(12, Frame3)
                theme:Bind(Frame3, "BackgroundColor3", "Panel")
                theme:BindAccent(
                  fn56("UIStroke", { Thickness = 1, Color = theme.Data.Accent, Transparency = 0.82, Parent = Frame3 }),
                  "Color"
                )
                fn56("UIListLayout", { Padding = UDim.new(0, 2), SortOrder = Enum.SortOrder.LayoutOrder, Parent = Frame3 })

                fn56("UIPadding", {
                  PaddingTop = UDim.new(0, 6),
                  PaddingBottom = UDim.new(0, 6),
                  PaddingLeft = UDim.new(0, 6),
                  PaddingRight = UDim.new(0, 6),
                  Parent = Frame3,
                })

                local flag23 = false

                local function fn61(arg3)
                  flag23 = arg3
                  Tween.to(Frame3, Tween.Presets.Smooth, { Size = UDim2.new(1, 0, 0, arg3 and #arg.tabs * 36 + 12 or 0) })
                  Tween.to(v97, Tween.Presets.Smooth, { Rotation = arg3 and 180 or 0 })
                end

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.new(1, 0, 0, 34),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 1,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = "   " .. tab.name,
                    TextSize = 11,
                    TextColor3 = theme.Data.Sub,
                    TextXAlignment = Enum.TextXAlignment.Left,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 12,
                    Parent = Frame3,
                  })

                  fn57(8, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")

                  local v98 = fn56("Frame", {
                    AnchorPoint = Vector2.new(0, 0.5),
                    Position = UDim2.new(0, 8, 0.5, 0),
                    Size = UDim2.fromOffset(0, 0),
                    BackgroundColor3 = theme.Data.Accent,
                    BorderSizePixel = 0,
                    ZIndex = 11,
                    Parent = TextButton,
                  })

                  fn57(4, v98)
                  theme:BindAccent(v98, "BackgroundColor3")
                  tab.navIndicator = v98
                  local v99 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v99 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.4, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v99 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 1, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v99.index)
                    fn61(false)
                  end)

                  tab.navBtn = TextButton
                end

                v96.MouseEnter:Connect(function()
                  Tween.to(v96, Tween.Presets.Snappy, { BackgroundTransparency = 0.46 })
                end)

                v96.MouseLeave:Connect(function()
                  Tween.to(v96, Tween.Presets.Snappy, { BackgroundTransparency = 0.54 })
                end)

                v96.MouseButton1Click:Connect(function()
                  fn61(not flag23)
                end)
              end

              index._buildChipRail = function(arg, arg2)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  Position = arg2 == "right" and UDim2.new(1, -304, 0, 64) or UDim2.fromOffset(14, 64),
                  Size = UDim2.new(0, 58, 1, -76),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.58,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(15, Frame)
                tbl26.apply(Frame, { transparency = 0.58, reflection = false })
                theme:Bind(Frame, "BackgroundColor3", "Panel")

                local ScrollingFrame = fn56("ScrollingFrame", {
                  BackgroundTransparency = 1,
                  Size = UDim2.fromScale(1, 1),
                  ScrollBarThickness = 0,
                  CanvasSize = UDim2.new(),
                  AutomaticCanvasSize = Enum.AutomaticSize.Y,
                  ZIndex = 7,
                  Parent = Frame,
                })

                fn56("UIListLayout", {
                  Padding = UDim.new(0, 8),
                  HorizontalAlignment = Enum.HorizontalAlignment.Center,
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  Parent = ScrollingFrame,
                })

                fn56("UIPadding", { PaddingTop = UDim.new(0, 12), PaddingBottom = UDim.new(0, 10), Parent = ScrollingFrame })
                arg._nav = Frame

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.fromOffset(38, 38),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 0.6,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = tab.name:sub(1, 1):upper(),
                    TextSize = 14,
                    TextColor3 = theme.Data.Sub,
                    ZIndex = 10,
                    Parent = ScrollingFrame,
                  })

                  fn57(12, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")
                  theme:BindAccent(
                    fn56("UIStroke", { Thickness = 1, Color = theme.Data.Accent, Transparency = 0.6, Parent = TextButton }),
                    "Color"
                  )

                  local Frame2 = fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 1),
                    Position = UDim2.new(0.5, 0, 1, -3),
                    Size = UDim2.fromOffset(0, 0),
                    BackgroundColor3 = theme.Data.Accent,
                    BorderSizePixel = 0,
                    ZIndex = 8,
                    Parent = TextButton,
                  })

                  fn57(3, Frame2)
                  theme:BindAccent(Frame2, "BackgroundColor3")
                  tab.navIndicator = Frame2
                  local v96 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.6, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.78, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v96.index)
                  end)

                  tab.navBtn = TextButton
                end
              end

              index._buildSegmentedNav = function(arg, arg2)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  AnchorPoint = Vector2.new(0.5, arg2 and 1 or 0),
                  Position = arg2 and UDim2.new(0.5, 0, 1, -10) or UDim2.new(0.5, 0, 0, 62),
                  Size = UDim2.new(1, arg2 and -64 or -32, 0, 42),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.58,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(12, Frame)
                tbl26.apply(Frame, { transparency = 0.58 })
                theme:Bind(Frame, "BackgroundColor3", "Panel")

                fn56("UIListLayout", {
                  FillDirection = Enum.FillDirection.Horizontal,
                  Padding = UDim.new(0, 1),
                  HorizontalAlignment = Enum.HorizontalAlignment.Center,
                  VerticalAlignment = Enum.VerticalAlignment.Center,
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  Parent = Frame,
                })

                fn56("UIPadding", {
                  PaddingLeft = UDim.new(0, 4),
                  PaddingRight = UDim.new(0, 4),
                  PaddingTop = UDim.new(0, 4),
                  PaddingBottom = UDim.new(0, 4),
                  Parent = Frame,
                })

                arg._nav = Frame
                local n35 = math.max(1, #arg.tabs)
                local n36 = (-8 - n35 - 1) / n35

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.new(1 / n35, n36, 1, -8),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 1,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = tab.name,
                    TextSize = 16,
                    TextColor3 = Color3.fromRGB(150, 140, 220),
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 10,
                    Parent = Frame,
                  })

                  fn57(8, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")

                  local Frame2 = fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 1),
                    Position = UDim2.new(0.5, 0, 1, -2),
                    Size = UDim2.new(0, 0, 0, 2),
                    BackgroundColor3 = theme.Data.Accent,
                    BorderSizePixel = 0,
                    ZIndex = 8,
                    Parent = TextButton,
                  })

                  fn57(1, Frame2)
                  theme:BindAccent(Frame2, "BackgroundColor3")
                  tab.navIndicator = Frame2
                  local v96 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.92, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 1, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v96.index)
                  end)

                  tab.navBtn = TextButton
                end
              end

              index._buildVArrowNav = function(arg)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  Position = UDim2.fromOffset(14, 64),
                  Size = UDim2.new(0, 58, 1, -76),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.58,
                  BorderSizePixel = 0,
                  ZIndex = 8,
                  Parent = arg.main,
                })

                fn57(15, Frame)
                tbl26.apply(Frame, { transparency = 0.58, reflection = false })
                theme:Bind(Frame, "BackgroundColor3", "Panel")
                arg._nav = Frame

                local function fn61(arg2)
                  local TextButton = fn56("TextButton", {
                    AnchorPoint = Vector2.new(0.5, arg2 < 0 and 0 or 1),
                    Position = UDim2.new(0.5, 0, arg2 < 0 and 0 or 1, arg2 < 0 and 10 or -10),
                    Size = UDim2.fromOffset(36, 36),
                    BackgroundColor3 = theme.Data.Bg,
                    BackgroundTransparency = 0.34,
                    AutoButtonColor = false,
                    Text = "",
                    ZIndex = 7,
                    Parent = Frame,
                  })

                  fn57(10, TextButton)
                  theme:Bind(TextButton, "BackgroundColor3", "Bg")
                  theme:BindAccent(
                    fn56("UIStroke", { Thickness = 1, Color = theme.Data.Accent, Transparency = 0.82, Parent = TextButton }),
                    "Color"
                  )
                  local v96 = fn58(TextButton, theme.Data.Accent, 16)
                  v96.AnchorPoint = Vector2.new(0.5, 0.5)
                  v96.Position = UDim2.fromScale(0.5, 0.5)
                  v96.Rotation = arg2 < 0 and 180 or 0
                  v96.ZIndex = 8

                  for _, child in ipairs(v96:GetChildren()) do
                    if child:IsA("Frame") then
                      theme:BindAccent(child, "BackgroundColor3")
                    end
                  end

                  TextButton.MouseEnter:Connect(function()
                    Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0 })
                  end)

                  TextButton.MouseLeave:Connect(function()
                    Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.34 })
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    local n35 = #arg.tabs
                    if n35 == 0 then
                      return
                    end
                    arg:SelectTab(((arg.activeTab and arg.activeTab.index or 1) - 1 + arg2) % n35 + 1)
                  end)

                  return TextButton
                end

                fn61(-1)
                fn61(1)

                arg._vArrowCounter = fn56("TextLabel", {
                  AnchorPoint = Vector2.new(0.5, 0.5),
                  Position = UDim2.fromScale(0.5, 0.5),
                  Size = UDim2.fromOffset(36, 48),
                  BackgroundColor3 = theme.Data.Accent,
                  BackgroundTransparency = 0.75,
                  Font = Enum.Font.MontserratBold,
                  Text = "",
                  TextSize = 11,
                  TextColor3 = theme.Data.Text,
                  TextWrapped = true,
                  ZIndex = 10,
                  Parent = Frame,
                })

                fn57(10, arg._vArrowCounter)
                theme:BindAccent(arg._vArrowCounter, "BackgroundColor3")
                theme:Bind(arg._vArrowCounter, "TextColor3", "Text")
              end

              index._buildBottomBarNav = function(arg)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  AnchorPoint = Vector2.new(0.5, 1),
                  Position = UDim2.new(0.5, 0, 1, -12),
                  Size = UDim2.new(1, -24, 0, 46),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.54,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(12, Frame)
                tbl26.apply(Frame, { transparency = 0.2 })
                theme:Bind(Frame, "BackgroundColor3", "Panel")

                fn56("UIListLayout", {
                  FillDirection = Enum.FillDirection.Horizontal,
                  Padding = UDim.new(0, 3),
                  VerticalAlignment = Enum.VerticalAlignment.Center,
                  HorizontalAlignment = Enum.HorizontalAlignment.Center,
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  Parent = Frame,
                })

                fn56("UIPadding", {
                  PaddingLeft = UDim.new(0, 5),
                  PaddingRight = UDim.new(0, 5),
                  PaddingTop = UDim.new(0, 5),
                  PaddingBottom = UDim.new(0, 4),
                  Parent = Frame,
                })

                arg._nav = Frame
                local n35 = math.max(1, #arg.tabs)
                local n36 = (-8 - 3 * (n35 - 1)) / n35

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.new(1 / n35, n36, 1, -8),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 1,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = tab.name,
                    TextSize = 11,
                    TextColor3 = theme.Data.Sub,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 7,
                    Parent = Frame,
                  })

                  fn57(8, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")

                  local Frame2 = fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 0),
                    Position = UDim2.new(0.5, 0, 0, 2),
                    Size = UDim2.new(0, 0, 0, 2),
                    BackgroundColor3 = theme.Data.Accent,
                    BorderSizePixel = 0,
                    ZIndex = 8,
                    Parent = TextButton,
                  })

                  fn57(1, Frame2)
                  theme:BindAccent(Frame2, "BackgroundColor3")
                  tab.navIndicator = Frame2
                  local v96 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.9, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 1, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v96.index)
                  end)

                  tab.navBtn = TextButton
                end
              end

              index._buildChipDock = function(arg)
                local theme = arg.theme

                local Frame = fn56("Frame", {
                  Name = "Nav",
                  AnchorPoint = Vector2.new(0.5, 1),
                  Position = UDim2.new(0.5, 0, 1, -12),
                  AutomaticSize = Enum.AutomaticSize.X,
                  Size = UDim2.new(0, 0, 0, 50),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.56,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(14, Frame)
                tbl26.apply(Frame, { transparency = 0.56 })
                theme:Bind(Frame, "BackgroundColor3", "Panel")

                fn56("UIListLayout", {
                  FillDirection = Enum.FillDirection.Horizontal,
                  Padding = UDim.new(0, 6),
                  VerticalAlignment = Enum.VerticalAlignment.Center,
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  Parent = Frame,
                })

                fn56("UIPadding", {
                  PaddingLeft = UDim.new(0, 7),
                  PaddingRight = UDim.new(0, 7),
                  PaddingTop = UDim.new(0, 6),
                  PaddingBottom = UDim.new(0, 8),
                  Parent = Frame,
                })

                arg._nav = Frame

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.fromOffset(38, 38),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 0.78,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = tab.name:sub(1, 1):upper(),
                    TextSize = 14,
                    TextColor3 = theme.Data.Sub,
                    ZIndex = 7,
                    Parent = Frame,
                  })

                  fn57(11, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")
                  theme:BindAccent(
                    fn56("UIStroke", { Thickness = 1, Color = theme.Data.Accent, Transparency = 0.84, Parent = TextButton }),
                    "Color"
                  )

                  local Frame2 = fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 1),
                    Position = UDim2.new(0.5, 0, 1, -3),
                    Size = UDim2.fromOffset(0, 0),
                    BackgroundColor3 = theme.Data.Accent,
                    BorderSizePixel = 0,
                    ZIndex = 8,
                    Parent = TextButton,
                  })

                  fn57(3, Frame2)
                  theme:BindAccent(Frame2, "BackgroundColor3")
                  tab.navIndicator = Frame2
                  local v96 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.6, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v96 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.6, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v96.index)
                  end)

                  tab.navBtn = TextButton
                end
              end

              index._buildUnderlineNav = function(arg)
                local theme = arg.theme

                local v96 = fn56("Frame", {
                  Name = "Nav",
                  Position = UDim2.fromOffset(16, 64),
                  Size = UDim2.new(1, -32, 0, 42),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.58,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(12, v96)
                tbl26.apply(v96, { transparency = 0.58 })
                theme:Bind(v96, "BackgroundColor3", "Panel")

                theme:BindAccent(
                  fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 1),
                    Position = UDim2.new(0.5, 0, 1, -5),
                    Size = UDim2.new(1, -18, 0, 1),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 0.9,
                    BorderSizePixel = 0,
                    ZIndex = 7,
                    Parent = v96,
                  }),
                  "BackgroundColor3"
                )

                local Frame = fn56("Frame", { BackgroundTransparency = 1, Size = UDim2.fromScale(1, 1), ZIndex = 7, Parent = v96 })

                fn56("UIListLayout", {
                  FillDirection = Enum.FillDirection.Horizontal,
                  Padding = UDim.new(0, 3),
                  HorizontalAlignment = Enum.HorizontalAlignment.Center,
                  VerticalAlignment = Enum.VerticalAlignment.Center,
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  Parent = Frame,
                })

                fn56("UIPadding", {
                  PaddingLeft = UDim.new(0, 4),
                  PaddingRight = UDim.new(0, 4),
                  PaddingTop = UDim.new(0, 4),
                  PaddingBottom = UDim.new(0, 4),
                  Parent = Frame,
                })

                arg._nav = v96
                local n35 = math.max(1, #arg.tabs)
                local n36 = (-8 - 3 * (n35 - 1)) / n35

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.new(1 / n35, n36, 1, -8),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 1,
                    AutoButtonColor = false,
                    Font = Enum.Font.MontserratBold,
                    Text = tab.name,
                    TextSize = 11,
                    TextColor3 = theme.Data.Sub,
                    TextTruncate = Enum.TextTruncate.AtEnd,
                    ZIndex = 8,
                    Parent = Frame,
                  })

                  fn57(8, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")

                  local v97 = fn56("Frame", {
                    AnchorPoint = Vector2.new(0.5, 1),
                    Position = UDim2.new(0.5, 0, 1, -1),
                    Size = UDim2.new(0, 0, 0, 3),
                    BackgroundColor3 = theme.Data.Accent,
                    BorderSizePixel = 0,
                    ZIndex = 9,
                    Parent = TextButton,
                  })

                  fn57(2, v97)
                  theme:BindAccent(v97, "BackgroundColor3")
                  local v98 = fn56
                  local v99 = "UIGradient"
                  local tbl29 = {}
                  local numberSequence = NumberSequence.new
                  local tbl30 = {}
                  local v100 = NumberSequenceKeypoint.new(0, 0.6)
                  local v101 = NumberSequenceKeypoint.new(0.5, 0)
                  tbl30[1] = v100
                  tbl30[2] = v101

                  do
                    local values = table.pack(NumberSequenceKeypoint.new(1, 0.45))
                    table.move(values, 1, values.n, 3, tbl30)
                  end

                  tbl29.Transparency = numberSequence(tbl30)
                  tbl29.Parent = v97
                  v98(v99, tbl29)
                  tab.navBtn = TextButton
                  tab.navUnderline = v97
                  local v102 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v102 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 0.9, TextColor3 = theme.Data.Text })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v102 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { BackgroundTransparency = 1, TextColor3 = theme.Data.Sub })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v102.index)
                  end)
                end
              end

              index._buildDotsNav = function(arg)
                local theme = arg.theme

                local v96 = fn56("Frame", {
                  Name = "Sidebar",
                  Position = UDim2.fromOffset(14, 62),
                  Size = UDim2.new(0, 28, 1, -130),
                  BackgroundColor3 = theme.Data.Panel,
                  BackgroundTransparency = 0.64,
                  BorderSizePixel = 0,
                  ZIndex = 6,
                  Parent = arg.main,
                })

                fn57(14, v96)
                tbl26.apply(v96, { transparency = 0.64 })
                theme:Bind(v96, "BackgroundColor3", "Panel")

                fn56("UIListLayout", {
                  Padding = UDim.new(0, 10),
                  HorizontalAlignment = Enum.HorizontalAlignment.Center,
                  VerticalAlignment = Enum.VerticalAlignment.Center,
                  SortOrder = Enum.SortOrder.LayoutOrder,
                  Parent = v96,
                })

                arg._nav = v96

                for _, tab in ipairs(arg.tabs) do
                  local TextButton = fn56("TextButton", {
                    Size = UDim2.fromOffset(8, 8),
                    BackgroundColor3 = theme.Data.Accent,
                    BackgroundTransparency = 0.68,
                    AutoButtonColor = false,
                    Text = "",
                    ZIndex = 7,
                    Parent = v96,
                  })

                  fn57(5, TextButton)
                  theme:BindAccent(TextButton, "BackgroundColor3")
                  local v97 = tab

                  TextButton.MouseEnter:Connect(function()
                    if arg.activeTab ~= v97 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { Size = UDim2.fromOffset(10, 14), BackgroundTransparency = 0.34 })
                    end
                  end)

                  TextButton.MouseLeave:Connect(function()
                    if arg.activeTab ~= v97 then
                      Tween.to(TextButton, Tween.Presets.Snappy, { Size = UDim2.fromOffset(8, 8), BackgroundTransparency = 0.5 })
                    end
                  end)

                  TextButton.MouseButton1Click:Connect(function()
                    arg:SelectTab(v97.index)
                  end)

                  tab.navBtn = TextButton
                end
              end

              index._rebuildNav = function(arg)
                if arg._nav then
                  arg._nav:Destroy()
                  arg._nav = nil
                end

                for _, tab in ipairs(arg.tabs) do
                  tab.navBtn = nil
                  tab.navUnderline = nil
                  tab.navIndicator = nil
                end

                local layout = arg.layout

                if layout == 2 then
                  arg:_buildRailNav("left")
                elseif layout == 3 then
                  arg:_buildArrowNav()
                elseif layout == 5 then
                  arg:_buildPillNav(true)
                elseif layout == 5 then
                  arg:_buildRailNav("right")
                elseif layout == 6 then
                  arg:_buildDropdownNav()
                elseif layout == 10 then
                  arg:_buildChipRail(2)
                elseif layout == 8 then
                  arg:_buildChipRail("right")
                elseif layout == 9 then
                  arg:_buildSegmentedNav()
                elseif layout == 10 then
                  arg:_buildVArrowNav()
                elseif layout == 12 then
                  arg:_buildBottomBarNav()
                elseif layout == 12 then
                  arg:_buildSegmentedNav(true)
                elseif layout == 13 then
                  arg:_buildDropdownNav(true)
                elseif layout == 14 then
                  arg:_buildChipDock()
                elseif layout == 15 then
                  arg:_buildUnderlineNav()
                elseif layout == 20 then
                  arg:_buildDotsNav()
                else
                  arg:_buildPillNav(false)
                end

                arg:_applyLayout()
                arg:_highlightNav()
              end

              index._highlightNav = function(arg)
                local theme = arg.theme
                local layout = arg.layout
                local flag23 = layout == 2 or layout == 5
                local flag24 = layout == 7 or layout == 8 or layout == 14
                local flag25 = layout == 6 or layout == 12
                local flag26 = layout == 1 or layout == 4 or layout == 9 or layout == 11 or layout == 16

                for _, tab in ipairs(arg.tabs) do
                  if tab.navBtn then
                    local backgroundTransparency = tab == arg.activeTab

                    if layout == 15 then
                      Tween.to(tab.navBtn, Tween.Presets.Smooth, {
                        BackgroundTransparency = backgroundTransparency and 0.84 or 1,
                        TextColor3 = backgroundTransparency and Color3.fromRGB(255, 255, 255) or theme.Data.Sub,
                      })

                      if tab.navUnderline then
                        Tween.to(tab.navUnderline, Tween.Presets.Spring, {
                          Size = backgroundTransparency and UDim2.new(1, -18, 0, 3) or UDim2.new(0, 0, 0, 3),
                        })
                      end
                    elseif layout == 16 then
                      Tween.to(
                        tab.navBtn,
                        Tween.Presets.Spring,
                        { Size = backgroundTransparency and UDim2.fromOffset(8, 26) or UDim2.fromOffset(8, 8) }
                      )
                      local to = Tween.to
                      local navBtn = tab.navBtn
                      local smooth = Tween.Presets.Smooth
                      local tbl29 = {}
                      backgroundTransparency = backgroundTransparency and 0.08
                      tbl29.BackgroundTransparency = backgroundTransparency or 0.68
                      to(navBtn, smooth, tbl29)
                    elseif flag23 then
                      Tween.to(tab.navBtn, Tween.Presets.Smooth, {
                        BackgroundTransparency = backgroundTransparency and 0.12 or 1,
                        TextColor3 = backgroundTransparency and Color3.fromRGB(255, 255, 255) or theme.Data.Sub,
                      })

                      if tab.navIndicator then
                        local to = Tween.to
                        local navIndicator = tab.navIndicator
                        local spring = Tween.Presets.Spring
                        local tbl29 = {}
                        backgroundTransparency = backgroundTransparency and UDim2.fromOffset(3, 30) or UDim2.fromOffset(3, 0)
                        tbl29.Size = backgroundTransparency
                        to(navIndicator, spring, tbl29)
                      end
                    elseif flag24 then
                      Tween.to(tab.navBtn, Tween.Presets.Smooth, {
                        BackgroundTransparency = backgroundTransparency and 0.55 or 0.78,
                        TextColor3 = backgroundTransparency and Color3.fromRGB(255, 255, 255) or theme.Data.Sub,
                      })

                      if tab.navIndicator then
                        local to = Tween.to
                        local navIndicator = tab.navIndicator
                        local spring = Tween.Presets.Spring
                        local tbl29 = {}
                        backgroundTransparency = backgroundTransparency and UDim2.fromOffset(6, 6)
                        tbl29.Size = backgroundTransparency or UDim2.fromOffset(0, 0)
                        to(navIndicator, spring, tbl29)
                      end
                    elseif flag25 then
                      Tween.to(tab.navBtn, Tween.Presets.Smooth, {
                        BackgroundTransparency = backgroundTransparency and 0.84 or 1,
                        TextColor3 = backgroundTransparency and Color3.fromRGB(255, 255, 255) or theme.Data.Sub,
                      })

                      if tab.navIndicator then
                        Tween.to(tab.navIndicator, Tween.Presets.Spring, {
                          Size = backgroundTransparency and UDim2.fromOffset(10, 10) or UDim2.fromOffset(0, 0),
                        })
                      end
                    elseif flag26 then
                      Tween.to(tab.navBtn, Tween.Presets.Smooth, {
                        BackgroundTransparency = backgroundTransparency and ((layout == 1 or layout == 4) and 0.18 or 0.72) or 1,
                        TextColor3 = backgroundTransparency and Color3.fromRGB(255, 255, 255) or theme.Data.Sub,
                      })

                      if tab.navIndicator then
                        local to = Tween.to
                        local navIndicator = tab.navIndicator
                        local spring = Tween.Presets.Spring

                        local tbl29 = {
                          Size = backgroundTransparency and UDim2.new(1, -16, 0, 2.5) or UDim2.new(0, 0, 0, 2.5),
                        }

                        backgroundTransparency = backgroundTransparency and 0 or 1
                        tbl29.BackgroundTransparency = backgroundTransparency
                        to(navIndicator, spring, tbl29)
                      end
                    else
                      Tween.to(tab.navBtn, Tween.Presets.Smooth, {
                        BackgroundTransparency = backgroundTransparency and 0.82 or 1,
                        TextColor3 = backgroundTransparency and Color3.fromRGB(255, 255, 255) or theme.Data.Sub,
                      })
                    end
                  end
                end

                if layout == 3 and arg.activeTab then
                  if arg._arrowLabel then
                    arg._arrowLabel.Text = arg.activeTab.name
                  end

                  if arg._arrowCounter then
                    arg._arrowCounter.Text = arg.activeTab.index .. " / " .. #arg.tabs
                  end
                end

                if (layout == 6 or layout == 12) and arg._dropHeadLabel and arg.activeTab then
                  arg._dropHeadLabel.Text = arg.activeTab.name
                end

                if layout == 10 and arg._vArrowCounter and arg.activeTab then
                  arg._vArrowCounter.Text = arg.activeTab.index .. "\n/\n" .. #arg.tabs
                end
              end

              index.SetLayout = function(arg, arg2)
                arg.layout = math.clamp(tonumber(arg2) or 1, 1, 16)
                arg:_rebuildNav()
              end

              index._setupDrag = function(arg)
                local flag23 = false
                local position = nil
                local position2 = nil
                local position3 = arg.main.Position
                local vector2 = Vector2.zero
                local vector22 = Vector2.zero

                local function fn61(input)
                  if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                    flag23 = true
                    position = input.Position
                    position2 = arg.main.Position
                    position3 = arg.main.Position
                    vector22 = input.Position
                    vector2 = Vector2.zero
                    arg.outline:brighten(true)

                    if not arg._minimized then
                      Tween.to(arg.main, Tween.Presets.Snappy, { Size = UDim2.fromOffset(arg._w * 0.96, arg._h * 0.96) })
                    end
                  end
                end

                table.insert(arg._conns, arg.main.InputBegan:Connect(fn61))
                table.insert(arg._conns, arg.titleBar.InputBegan:Connect(fn61))

                if arg.headerCard then
                  table.insert(arg._conns, arg.headerCard.InputBegan:Connect(fn61))
                end

                if arg.content then
                  table.insert(arg._conns, arg.content.InputBegan:Connect(fn61))
                end

                table.insert(
                  arg._conns,
                  UserInputService.InputChanged:Connect(function(input)
                    local flag24 = flag23

                    if flag23 then
                      flag24 = input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch
                    end

                    if flag24 then
                      local n35 = input.Position - position
                      position3 = UDim2.new(position2.X.Scale, position2.X.Offset + n35.X, position2.Y.Scale, position2.Y.Offset + n35.Y)
                      vector2 = Vector2.new(input.Position.X - vector22.X, input.Position.Y - vector22.Y)
                      vector22 = Vector2.new(input.Position.X, input.Position.Y)
                    end
                  end)
                )

                table.insert(
                  arg._conns,
                  UserInputService.InputEnded:Connect(function(input)
                    if
                      flag23 and (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch)
                    then
                      flag23 = false
                      arg.outline:brighten(false)

                      if arg._minimized then
                        Tween.to(arg.main, Tween.Presets.Spring, { Size = UDim2.fromOffset(arg._w, 58) })
                      else
                        Tween.to(arg.main, Tween.Presets.Spring, { Size = UDim2.fromOffset(arg._w, arg._h) })
                      end

                      Config.guiPosition = {
                        xScale = arg.main.Position.X.Scale,
                        xOffset = arg.main.Position.X.Offset,
                        yScale = arg.main.Position.Y.Scale,
                        yOffset = arg.main.Position.Y.Offset,
                      }

                      saveConfig()
                    end
                  end)
                )

                table.insert(
                  arg._conns,
                  RunService.RenderStepped:Connect(function()
                    if flag23 then
                      arg.main.Position = arg.main.Position:Lerp(position3, 0.25)
                    end
                  end)
                )
              end

              index._setupResize = function(arg)
                local flag23 = false
                local mouseLocation = nil
                local w = nil
                local v96 = nil
                local n35 = nil

                table.insert(
                  arg._conns,
                  arg.resizeHandle.InputBegan:Connect(function(input)
                    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                      flag23 = true
                      mouseLocation = UserInputService:GetMouseLocation()
                      local h = arg._h
                      w = arg._w
                      v96 = h
                      local n36 = arg.main.AbsolutePosition + arg.main.AbsoluteSize / 2
                      arg.main.Position = UDim2.fromOffset(n36.X, n36.Y)
                      local v97 = 2
                      n35 = n36 - Vector2.new(w, v96) / v97
                      arg.outline:brighten(true)
                    end
                  end)
                )

                table.insert(
                  arg._conns,
                  UserInputService.InputEnded:Connect(function(input)
                    if
                      flag23 and (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch)
                    then
                      flag23 = false
                      arg.outline:brighten(false)
                    end
                  end)
                )

                table.insert(
                  arg._conns,
                  UserInputService.InputChanged:Connect(function(input)
                    if
                      flag23
                      and (input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch)
                    then
                      local viewportSize = workspace.CurrentCamera.ViewportSize
                      local mouseLocation2 = UserInputService:GetMouseLocation()
                      local w2 = math.clamp(w + mouseLocation2.X - mouseLocation.X, arg.minW, viewportSize.X - 20)
                      local h = math.clamp(v96 + mouseLocation2.Y - mouseLocation.Y, arg.minH, viewportSize.Y - 20)
                      local v97 = arg
                      arg._w = w2
                      v97._h = h
                      local n36 = n35 + Vector2.new(w2, h) / 2
                      arg.main.Size = UDim2.fromOffset(w2, h)
                      arg.main.Position = UDim2.fromOffset(n36.X, n36.Y)
                    end
                  end)
                )
              end

              index._playOpen = function(arg)
                local udim2 = UDim2.fromOffset(arg._w, arg._h)
                local position = arg.main.Position
                arg.main.Size = UDim2.fromOffset(arg._w * 0.92, arg._h * 0.95)
                arg.main.Position = position + UDim2.fromOffset(0, 24)
                arg.main.BackgroundTransparency = 1
                arg.bg.ImageTransparency = 1
                arg.outline.stroke.Transparency = 1
                Tween.to(arg.main, Tween.Presets.Spring, { Size = udim2, Position = position })
                Tween.to(arg.main, Tween.Presets.Smooth, { BackgroundTransparency = 0 })
                Tween.to(arg.bg, Tween.Presets.Slow, { ImageTransparency = arg.bgTransparency })
                Tween.to(arg.outline.stroke, Tween.Presets.Smooth, { Transparency = 0.35 })
              end

              index.close = function(arg)
                Tween.to(arg.main, TweenInfo.new(0.3, Enum.EasingStyle.Back, Enum.EasingDirection.In), {
                  Size = UDim2.fromOffset(arg._w * 0.3, arg._h * 0.4),
                  BackgroundTransparency = 1,
                  Position = arg.main.Position + UDim2.fromOffset(0, 40),
                })

                Tween.to(arg.bg, Tween.Presets.Snappy, { ImageTransparency = 1 })
                Tween.to(arg.outline.stroke, Tween.Presets.Snappy, { Transparency = 1 })

                for _, conn in ipairs(arg._conns) do
                  if conn.Connected then
                    conn:Disconnect()
                  end
                end

                arg._conns = {}

                task.delay(0.35, function()
                  arg.outline:destroy()
                  arg.gui:Destroy()
                end)
              end

              index.minimize = function(arg)
                arg._minimized = not arg._minimized
                local minimizeBtn = arg.titleBar and arg.titleBar:FindFirstChild("MinimizeBtn")

                if minimizeBtn then
                  minimizeBtn.Text = arg._minimized and "+" or "—"
                end

                if arg._minimized then
                  arg._restoreSize = arg.main.Size

                  if arg._nav then
                    arg._nav.Visible = false
                  end

                  arg.content.Visible = false
                  arg.resizeHandle.Visible = false

                  if arg.bg then
                    arg.bg.Visible = false
                  end

                  Tween.to(arg.main, Tween.Presets.Spring, { Size = UDim2.fromOffset(arg._w, 58) })
                else
                  if arg.bg then
                    arg.bg.Visible = true
                  end

                  Tween.to(arg.main, Tween.Presets.Spring, { Size = arg._restoreSize or UDim2.fromOffset(arg._w, arg._h) })

                  task.delay(0.18, function()
                    if arg._minimized then
                      return
                    end

                    if arg._nav then
                      arg._nav.Visible = true
                    end

                    arg.content.Visible = true
                    arg.resizeHandle.Visible = true
                  end)
                end
              end

              index.maximize = function(arg)
                if arg._minimized then
                  arg._minimized = false

                  if arg._nav then
                    arg._nav.Visible = true
                  end

                  arg.content.Visible = true
                  arg.resizeHandle.Visible = true
                end

                arg._maxed = not arg._maxed

                if arg._maxed then
                  arg._preMax = { arg._w, arg._h }
                  local viewportSize = workspace.CurrentCamera.ViewportSize
                  local w = math.min(arg._w * 1.25, viewportSize.X - 40)
                  local h = math.min(arg._h * 1.25, viewportSize.Y - 40)
                  arg._w = w
                  arg._h = h
                  Tween.to(arg.main, Tween.Presets.Spring, { Size = UDim2.fromOffset(arg._w, arg._h) })
                else
                  local v96 = arg._preMax[2]
                  arg._w = arg._preMax[1]
                  arg._h = v96
                  Tween.to(arg.main, Tween.Presets.Spring, { Size = UDim2.fromOffset(arg._w, arg._h) })
                end
              end

              index.SetSize = function(arg, arg2, arg3)
                local viewportSize = workspace.CurrentCamera.ViewportSize
                arg._w = math.clamp(arg2, arg.minW, viewportSize.X - 20)
                arg._h = math.clamp(arg3, arg.minH, viewportSize.Y - 20)
                Tween.to(arg.main, Tween.Presets.Spring, { Size = UDim2.fromOffset(arg._w, arg._h) })
              end

              index.SetScale = function(arg, arg2)
                arg._currentScale = math.clamp(tonumber(arg2) or 1, 0.4, 1.6)

                if arg.scaleInstance then
                  arg.scaleInstance.Scale = arg._currentScale
                end
              end

              index.SetBackground = function(arg, bgIndex)
                if type(bgIndex) == "number" and Assets.Backgrounds[bgIndex] then
                  arg._bgIndex = bgIndex
                  bgIndex = Assets.Backgrounds[bgIndex]
                elseif type(bgIndex) == "number" then
                  bgIndex = "rbxassetid://" .. bgIndex
                end

                arg._currentBgImage = tostring(bgIndex)
                Tween.to(arg.bg, Tween.Presets.Snappy, { ImageTransparency = 1 })

                task.delay(0.16, function()
                  arg.bg.Image = arg._currentBgImage
                  Tween.to(arg.bg, Tween.Presets.Smooth, { ImageTransparency = arg.bgTransparency })
                end)
              end

              index.SetImageTransparency = function(arg, arg2)
                arg.bgTransparency = math.clamp(arg2, 0, 1)
                Tween.to(arg.bg, Tween.Presets.Smooth, { ImageTransparency = arg.bgTransparency })
              end

              index.SetTheme = function(arg, arg2)
                arg.theme:Apply(arg2)
                arg:_highlightNav()

                if arg.sidebar then
                  arg.sidebar:applyTheme()
                end
              end

              index.SetAccent = function(arg, arg2)
                arg.theme:SetAccent(arg2)
                arg:_highlightNav()

                if arg.sidebar then
                  arg.sidebar:applyTheme()
                end
              end

              index.Notify = function(arg, arg2, arg3, arg4)
                arg.notify.push(arg2, arg3, arg4)
              end

              index.SideButton = function(arg, arg2, arg3, arg4)
                return arg.sidebar:addButton(arg2, arg3, arg4)
              end

              index.SetSideBarLocked = function(arg, arg2)
                arg.sidebar:setLocked(arg2)
              end

              index.SetSideBarScale = function(arg, arg2)
                arg.sidebar:setScale(arg2)
              end

              index.SetSideBarVisible = function(arg, arg2)
                arg.sidebar:setVisible(arg2)
              end

              index.SetSideButtonVisible = function(arg, arg2, arg3)
                arg.sidebar:setButtonVisible(arg2, arg3)
              end

              index.SetSideBarStyle = function(arg, arg2)
                arg.sidebar:setStyle(arg2)
              end

              index.GetSideButtonPositions = function(arg)
                return arg.sidebar:getPositions()
              end

              index.SetSideButtonPositions = function(arg, arg2)
                arg.sidebar:setPositions(arg2)
              end

              index.ResetSideButtons = function(arg)
                arg.sidebar:resetPositions()
              end

              index.OnSideButtonMoved = function(arg, onPositionChanged)
                arg.sidebar.onPositionChanged = onPositionChanged
              end

              ReplicatedStorage = game:GetService("ReplicatedStorage")
              WorkspaceService = game:GetService("Workspace")
              HttpService = game:GetService("HttpService")
              LocalPlayer = localPlayer
              playerGui = LocalPlayer:WaitForChild("PlayerGui")
              color = Color3.fromRGB(126, 134, 255)

              do
                local touchEnabled = UserInputService.TouchEnabled and not UserInputService.KeyboardEnabled
                  or workspace.CurrentCamera and workspace.CurrentCamera.ViewportSize.X < 700 and UserInputService.TouchEnabled
                local n35 = touchEnabled and 0.7 or 1
                local n36 = touchEnabled and 0.85 or 1

                flag22 = false

                Config = {
                  speedEnabled = true,
                  speedProfile = "Normal",
                  speedToggled = false,
                  normalSpeed = 59,
                  normalCarrySpeed = 29,
                  laggerNormalSpeed = 35,
                  laggerCarrySpeed = 15,
                  customNormalSpeed = 70,
                  customCarrySpeed = 35,
                  autoBatSpeed = 65,
                  autoBatDistance = 4,
                  autoBatHeight = 0,
                  autoBatPosition = "Default",
                  tpBatDistance = 3.5,
                  tpBatMaxRange = 45,
                  tpBatSwingDelay = 0.2,
                  speedSwitchMode = 1,
                  circleEnabled = false,
                  antiRagdollEnabled = false,
                  _circleTrack = {
                    conn = nil,
                    target = nil,
                    lastPos = nil,
                    velocity = Vector3.zero,
                  },
                  medusaCounterEnabled = false,
                  autoGrabEnabled = false,
                  autoGrabVersion = 2,
                  autoGrabMode = "V1",
                  autoHitEnabled = false,
                  primeRange = 80,
                  infJumpEnabled = false,
                  infJumpMode = "Normal Mode",
                  floatingBtnsVisible = true,
                  phoneScale = n35,
                  buttonScale = n36,
                  sideBtnPositions = {},
                  tpBatEnabled = false,
                  autoTpDown = false,
                  autoTpDownHeight = 35,
                  bodyLockEnabled = false,
                  bodyLockRange = 50,
                  safeModeEnabled = true,
                  antiDieEnabled = false,
                  autoSwitchSpeedEnabled = false,
                  antiCollisionEnabled = true,
                  playerSpeedEnabled = false,
                  ragTimerEnabled = false,
                  ragCountdownDur = 2.5,
                  autoEquipBat = false,
                  batCounterEnabled = false,
                  batCounterVersion = 1,
                  introEnabled = false,
                  guiWidth = 500,
                  guiHeight = 600,
                  fov = 80,
                  stretchRez = 1,
                  fpsBoostEnabled = false,
                  currentAnimPack = "OFF",
                  markerDisplayStyle = "Both (Hitmarker + Bar)",
                  autoWalkMode = 2,
                  themeName = "Velvet Rose",
                  accentName = "Velvet Rose",
                  headlessEnabled = false,
                  korbloxEnabled = false,
                  copyAvatarTarget = "realalameen",
                  autoBatOnDropBrainrot = false,
                  tpBatOnDropBrainrot = false,
                  dropBrainrotMethod = "Ground Snap",
                }
              end
            end

            Keybinds = {
              speed = Enum.KeyCode.Q,
              laggerMode = Enum.KeyCode.R,
              customSpeedMode = Enum.KeyCode.None,
              circle = Enum.KeyCode.G,
              dropBrainrot = Enum.KeyCode.H,
              tpDown = Enum.KeyCode.T,
              walkLeft = Enum.KeyCode.Z,
              walkRight = Enum.KeyCode.C,
              tpBat = Enum.KeyCode.V,
              bodyLock = Enum.KeyCode.None,
              instaReset = Enum.KeyCode.None,
            }

            fn32 = nil
            fn33 = nil
            fn34 = nil
            fn35 = nil
            fn36 = nil
            fn37 = nil
            fn38 = nil
            fn39 = nil
            fn40 = nil
            v84 = nil

            tbl22 = {
              humanoid = nil,
              hrp = nil,
              speedLabel = nil,
              ragLabel = nil,
            }

            tbl24 = {
              active = false,
              startTime = 0,
              phase = "idle",
              label = "",
              lastResult = "",
              lastResultTime = 0,
              cooldownUntil = 0,
              cancelGen = 0,
              scanGen = 0,
              suspendedAt = 0,
              activePrompt = nil,
              activeData = nil,
              holdThreads = {},
            }

            v95 = nil
            lagger = nil
            custom = nil
            carry = nil
            v85 = nil
            v86 = nil
            v88 = nil
            v89 = nil
            v87 = nil

            tbl23 = {
              active = false,
              waypoints = {},
              index = 1,
              useCarry = false,
              pauseTime = 0,
              connection = nil,
              currentPathName = nil,
              faceTarget = nil,
              holding = false,
              holdCF = nil,
            }

            flag20 = false
            flag21 = false

            do
              local flag23 = false
              local flag24 = false
              local v96 = nil

              local function fn61()
                local tbl29 = {
                  speedEnabled = Config.speedEnabled,
                  speedProfile = Config.speedProfile,
                  speedToggled = Config.speedToggled,
                  normalSpeed = Config.normalSpeed,
                  normalCarrySpeed = Config.normalCarrySpeed,
                  laggerNormalSpeed = Config.laggerNormalSpeed,
                  laggerCarrySpeed = Config.laggerCarrySpeed,
                  customNormalSpeed = Config.customNormalSpeed,
                  customCarrySpeed = Config.customCarrySpeed,
                  autoBatSpeed = Config.autoBatSpeed,
                  autoBatDistance = Config.autoBatDistance,
                  autoBatHeight = Config.autoBatHeight,
                  autoBatPosition = Config.autoBatPosition,
                  tpBatPower = Config.tpBatPower,
                  tpBatDistance = Config.tpBatDistance,
                  tpBatMaxRange = Config.tpBatMaxRange,
                  tpBatSwingDelay = Config.tpBatSwingDelay,
                  laggerCarryEnabled = Config.laggerCarryEnabled,
                  tpBatEnabled = false,
                  circleEnabled = false,
                  autoGrabEnabled = Config.autoGrabEnabled,
                  autoGrabVersion = 2,
                  autoHitEnabled = Config.autoHitEnabled,
                  primeRange = Config.primeRange,
                  autoGrabMode = Config.autoGrabMode,
                  antiRagdollEnabled = Config.antiRagdollEnabled,
                  medusaCounterEnabled = Config.medusaCounterEnabled,
                  infJumpEnabled = Config.infJumpEnabled,
                  infJumpMode = Config.infJumpMode,
                  sideBtnPositions = Config.sideBtnPositions,
                  phoneScale = Config.phoneScale,
                  buttonScale = Config.buttonScale,
                  floatingBtnsVisible = Config.floatingBtnsVisible,
                  speedKey = fn60(Keybinds.speed),
                  laggerModeKey = fn60(Keybinds.laggerMode),
                  customSpeedModeKey = fn60(Keybinds.customSpeedMode),
                  circleKey = fn60(Keybinds.circle),
                  tpDownKey = fn60(Keybinds.tpDown),
                  walkLeftKey = fn60(Keybinds.walkLeft),
                  walkRightKey = fn60(Keybinds.walkRight),
                  tpBatKey = fn60(Keybinds.tpBat),
                  dropBrainrotKey = fn60(Keybinds.dropBrainrot),
                  dropBrainrotMethod = Config.dropBrainrotMethod or "Ground Snap",
                  autoBatOnDropBrainrot = Config.autoBatOnDropBrainrot,
                  tpBatOnDropBrainrot = Config.tpBatOnDropBrainrot,
                }

                tbl29.bodyLockKey = fn60(Keybinds.bodyLock)
                tbl29.instaResetKey = fn60(Keybinds.instaReset)
                tbl29.autoWalkMode = Config.autoWalkMode
                tbl29.playerSpeedEnabled = Config.playerSpeedEnabled
                tbl29.autoTpDown = Config.autoTpDown
                tbl29.autoTpDownHeight = Config.autoTpDownHeight
                tbl29.ragTimerEnabled = Config.ragTimerEnabled
                tbl29.ragCountdownDur = Config.ragCountdownDur
                tbl29.autoEquipBat = Config.autoEquipBat
                tbl29.batCounterEnabled = Config.batCounterEnabled
                tbl29.batCounterVersion = 1
                tbl29.speedSwitchMode = Config.speedSwitchMode
                tbl29.guiWidth = Config.guiWidth
                tbl29.guiHeight = Config.guiHeight
                tbl29.introEnabled = Config.introEnabled
                tbl29.fov = Config.fov
                tbl29.stretchRez = Config.stretchRez
                tbl29.currentAnimPack = Config.currentAnimPack
                tbl29.autoGrabScale = Config.autoGrabScale
                tbl29.guiPosition = Config.guiPosition
                tbl29.bodyLockEnabled = Config.bodyLockEnabled
                tbl29.safeModeEnabled = Config.safeModeEnabled
                tbl29.antiDieEnabled = Config.antiDieEnabled
                tbl29.autoSwitchSpeedEnabled = Config.autoSwitchSpeedEnabled
                tbl29.bodyLockRange = Config.bodyLockRange
                tbl29.sideBtnVisibility = Config.sideBtnVisibility
                tbl29.mobileBtnStyle = Config.mobileBtnStyle
                tbl29.autoGrabPosition = Config.autoGrabPosition
                tbl29.autoGrabBarPosition = Config.autoGrabBarPosition
                tbl29.copyAvatarTarget = Config.copyAvatarTarget
                tbl29.antiCollisionEnabled = Config.antiCollisionEnabled
                tbl29.fpsBoostEnabled = Config.fpsBoostEnabled
                tbl29.themeName = Config.themeName
                tbl29.accentName = Config.accentName
                tbl29.lockSideButtons = Config.lockSideButtons
                tbl29.topScaleWidgetPos = Config.topScaleWidgetPos

                local ok, result = pcall(function()
                  return HttpService:JSONEncode(tbl29)
                end)

                if not ok or not result then
                  return
                end
                v96 = result

                pcall(function()
                  if typeof(writefile) == "function" then
                    writefile("Hookduels.json", result)
                  end
                end)
              end

              saveConfig = function(arg)
                flag23 = true

                if arg then
                  flag23 = false
                  fn61()
                  return
                end

                if flag24 then
                  return
                end
                flag24 = true

                task.spawn(function()
                  while flag23 do
                    flag23 = false
                    task.wait(0.25)
                  end

                  fn61()
                  flag24 = false
                end)
              end

              fn41 = function()
                pcall(function()
                  if typeof(readfile) ~= "function" or typeof(isfile) ~= "function" then
                    return
                  end

                  if not isfile("Hookduels.json") then
                    return
                  end
                  local json = readfile("Hookduels.json")
                  if not json or #json == 0 then
                    return
                  end

                  local ok, result = pcall(function()
                    return HttpService:JSONDecode(json)
                  end)

                  local flag25 = not ok

                  if not flag25 then
                    local v97 = "table"
                    flag25 = type(result) ~= v97
                  end

                  if flag25 then
                    return
                  end

                  if result.speedEnabled ~= nil then
                    Config.speedEnabled = result.speedEnabled == true
                  end

                  if result.speedProfile ~= nil then
                    Config.speedProfile = tostring(result.speedProfile)
                  end

                  if result.speedToggled ~= nil then
                    Config.speedToggled = result.speedToggled == true
                  end

                  if result.normalSpeed ~= nil then
                    Config.normalSpeed = tonumber(result.normalSpeed) or 59
                  end

                  if result.normalCarrySpeed ~= nil then
                    Config.normalCarrySpeed = tonumber(result.normalCarrySpeed) or 29
                  end

                  if result.laggerNormalSpeed ~= nil then
                    Config.laggerNormalSpeed = tonumber(result.laggerNormalSpeed) or 35
                  end

                  if result.laggerCarrySpeed ~= nil then
                    Config.laggerCarrySpeed = tonumber(result.laggerCarrySpeed) or 15
                  end

                  if result.customNormalSpeed ~= nil then
                    Config.customNormalSpeed = tonumber(result.customNormalSpeed) or 70
                  end

                  if result.customCarrySpeed ~= nil then
                    Config.customCarrySpeed = tonumber(result.customCarrySpeed) or 35
                  end

                  if result.autoBatSpeed ~= nil then
                    Config.autoBatSpeed = tonumber(result.autoBatSpeed) or Config.autoBatSpeed
                  end

                  if result.autoBatDistance ~= nil then
                    Config.autoBatDistance = tonumber(result.autoBatDistance) or Config.autoBatDistance
                  end

                  if result.autoBatHeight ~= nil then
                    Config.autoBatHeight = tonumber(result.autoBatHeight) or Config.autoBatHeight
                  end

                  if result.autoBatPosition ~= nil then
                    Config.autoBatPosition = tostring(result.autoBatPosition)
                  end

                  if result.tpBatPower ~= nil then
                    Config.tpBatPower = tonumber(result.tpBatPower) or Config.tpBatPower
                  end

                  if result.tpBatDistance ~= nil then
                    Config.tpBatDistance = tonumber(result.tpBatDistance) or Config.tpBatDistance
                  end

                  if result.tpBatMaxRange ~= nil then
                    Config.tpBatMaxRange = tonumber(result.tpBatMaxRange) or Config.tpBatMaxRange
                  end

                  if result.tpBatSwingDelay ~= nil then
                    Config.tpBatSwingDelay = tonumber(result.tpBatSwingDelay) or Config.tpBatSwingDelay
                  end

                  if result.laggerCarryEnabled ~= nil then
                    Config.laggerCarryEnabled = result.laggerCarryEnabled == true
                  end

                  Config.tpBatEnabled = false
                  Config.circleEnabled = false
                  tbl23.active = false

                  if result.autoGrabEnabled ~= nil then
                    Config.autoGrabEnabled = result.autoGrabEnabled == true
                  end

                  Config.autoGrabVersion = 2

                  if result.autoHitEnabled ~= nil then
                    Config.autoHitEnabled = result.autoHitEnabled == true
                  end

                  if result.primeRange ~= nil then
                    Config.primeRange = math.clamp(tonumber(result.primeRange) or 80, 5, 300)
                  end

                  if result.autoGrabMode == "V1" or result.autoGrabMode == "V2" or result.autoGrabMode == "V3" then
                    Config.autoGrabMode = result.autoGrabMode
                  end

                  if result.antiRagdollEnabled ~= nil then
                    Config.antiRagdollEnabled = result.antiRagdollEnabled == true
                  end

                  if result.medusaCounterEnabled ~= nil then
                    Config.medusaCounterEnabled = result.medusaCounterEnabled == true
                  end

                  if result.infJumpEnabled ~= nil then
                    Config.infJumpEnabled = result.infJumpEnabled == true
                  end

                  if result.infJumpMode ~= nil then
                    Config.infJumpMode = tostring(result.infJumpMode)
                  end

                  if result.dropBrainrotMethod ~= nil then
                    Config.dropBrainrotMethod = tostring(result.dropBrainrotMethod)
                  end

                  if result.autoBatOnDropBrainrot ~= nil then
                    Config.autoBatOnDropBrainrot = result.autoBatOnDropBrainrot == true
                  end

                  if result.tpBatOnDropBrainrot ~= nil then
                    Config.tpBatOnDropBrainrot = result.tpBatOnDropBrainrot == true
                  end

                  if result.sideBtnPositions and type(result.sideBtnPositions) == "table" then
                    Config.sideBtnPositions = result.sideBtnPositions
                  end

                  if result.floatingBtnsVisible ~= nil then
                    Config.floatingBtnsVisible = result.floatingBtnsVisible ~= false
                  end

                  if result.phoneScale ~= nil then
                    Config.phoneScale = tonumber(result.phoneScale) or Config.phoneScale
                  end

                  if result.buttonScale ~= nil then
                    Config.buttonScale = tonumber(result.buttonScale) or Config.buttonScale
                  end

                  if result.autoWalkMode ~= nil then
                    Config.autoWalkMode = tonumber(result.autoWalkMode) or Config.autoWalkMode
                  end

                  if result.playerSpeedEnabled ~= nil then
                    Config.playerSpeedEnabled = result.playerSpeedEnabled == true
                  end

                  if result.autoTpDown ~= nil then
                    Config.autoTpDown = result.autoTpDown == true
                  end

                  if result.autoTpDownHeight ~= nil then
                    Config.autoTpDownHeight = math.clamp(tonumber(result.autoTpDownHeight) or 15, 10, 100)
                  end

                  if result.ragTimerEnabled ~= nil then
                    Config.ragTimerEnabled = result.ragTimerEnabled == true
                  end

                  if result.ragCountdownDur ~= nil then
                    Config.ragCountdownDur = math.clamp(tonumber(result.ragCountdownDur) or 2.5, 1, 10)
                  end

                  if result.autoEquipBat ~= nil then
                    Config.autoEquipBat = result.autoEquipBat == true
                  end

                  if result.batCounterEnabled ~= nil then
                    Config.batCounterEnabled = result.batCounterEnabled == true
                  end

                  Config.batCounterVersion = 1

                  if result.speedSwitchMode ~= nil then
                    Config.speedSwitchMode = math.clamp(tonumber(result.speedSwitchMode) or 1, 1, 2)
                  end

                  if result.guiWidth ~= nil then
                    Config.guiWidth = math.clamp(tonumber(result.guiWidth) or 400, 300, 900)
                  end

                  if result.guiHeight ~= nil then
                    Config.guiHeight = math.clamp(tonumber(result.guiHeight) or 540, 300, 900)
                  end

                  if
                    Config.guiWidth == 400
                    or Config.guiWidth == 440
                    or Config.guiWidth == 460
                    or Config.guiWidth == 540
                    or Config.guiWidth == 600
                  then
                    Config.guiWidth = 500
                  end

                  if
                    Config.guiHeight == 480
                    or Config.guiHeight == 540
                    or Config.guiHeight == 640
                    or Config.guiHeight == 680
                    or Config.guiHeight == 720
                    or Config.guiHeight == 760
                  then
                    Config.guiHeight = 600
                  end

                  if result.introEnabled ~= nil then
                    Config.introEnabled = result.introEnabled ~= false
                  end

                  if result.fov ~= nil then
                    Config.fov = math.clamp(tonumber(result.fov) or 80, 80, 100)
                  end

                  if result.stretchRez ~= nil then
                    Config.stretchRez = math.clamp(tonumber(result.stretchRez) or 1, 0.1, 1)
                  end

                  if result.currentAnimPack ~= nil then
                    Config.currentAnimPack = tostring(result.currentAnimPack)
                  end

                  if result.autoGrabScale ~= nil then
                    Config.autoGrabScale = math.clamp(tonumber(result.autoGrabScale) or 1, 0.4, 2)
                  end

                  if result.guiPosition and type(result.guiPosition) == "table" then
                    Config.guiPosition = result.guiPosition
                  end

                  if result.bodyLockEnabled ~= nil then
                    Config.bodyLockEnabled = result.bodyLockEnabled == true
                  end

                  if result.safeModeEnabled ~= nil then
                    Config.safeModeEnabled = result.safeModeEnabled == true
                  end

                  if result.autoSwitchSpeedEnabled ~= nil then
                    Config.autoSwitchSpeedEnabled = result.autoSwitchSpeedEnabled == true
                  end

                  if result.antiDieEnabled ~= nil then
                    Config.antiDieEnabled = result.antiDieEnabled == true
                  end

                  if result.bodyLockRange ~= nil then
                    Config.bodyLockRange = math.clamp(tonumber(result.bodyLockRange) or 50, 10, 250)
                  end

                  if result.sideBtnVisibility and type(result.sideBtnVisibility) == "table" then
                    Config.sideBtnVisibility = result.sideBtnVisibility
                  end

                  if result.mobileBtnStyle ~= nil then
                    Config.mobileBtnStyle = tostring(result.mobileBtnStyle)
                  end

                  local autoGrabPosition = result.autoGrabPosition

                  if autoGrabPosition then
                    local v97 = "table"
                    autoGrabPosition = type(result.autoGrabPosition) == v97
                  end

                  if autoGrabPosition then
                    Config.autoGrabPosition = result.autoGrabPosition
                  end

                  local autoGrabBarPosition = result.autoGrabBarPosition

                  if autoGrabBarPosition then
                    local v97 = "table"
                    autoGrabBarPosition = type(result.autoGrabBarPosition) == v97
                  end

                  if autoGrabBarPosition then
                    Config.autoGrabBarPosition = result.autoGrabBarPosition
                  end

                  if result.copyAvatarTarget ~= nil then
                    Config.copyAvatarTarget = tostring(result.copyAvatarTarget)
                  end

                  if result.antiCollisionEnabled ~= nil then
                    Config.antiCollisionEnabled = result.antiCollisionEnabled == true
                  end

                  if result.fpsBoostEnabled ~= nil then
                    Config.fpsBoostEnabled = result.fpsBoostEnabled == true
                  end

                  if result.themeName ~= nil then
                    Config.themeName = tostring(result.themeName)
                  end

                  if result.accentName ~= nil then
                    Config.accentName = tostring(result.accentName)
                  end

                  if result.lockSideButtons ~= nil then
                    Config.lockSideButtons = result.lockSideButtons == true
                  end

                  if result.topScaleWidgetPos and type(result.topScaleWidgetPos) == "table" then
                    Config.topScaleWidgetPos = result.topScaleWidgetPos
                  end

                  local function fn62(arg)
                    if type(arg) ~= "string" then
                      return nil
                    end

                    if arg == "None" or arg == "" then
                      return Enum.KeyCode.None
                    end

                    if arg:match("^MouseButton%d+$") then
                      return arg
                    end

                    local ok2, result2 = pcall(function()
                      return Enum.KeyCode[arg]
                    end)

                    return ok2 and result2 or nil
                  end

                  local function fn63(arg, arg2)
                    local v97 = fn62(result[arg2])

                    if v97 ~= nil then
                      Keybinds[arg] = v97
                    end
                  end

                  fn63("speed", "speedKey")
                  fn63("laggerMode", "laggerModeKey")
                  fn63("customSpeedMode", "customSpeedModeKey")
                  fn63("circle", "circleKey")
                  fn63("tpDown", "tpDownKey")
                  fn63("walkLeft", "walkLeftKey")
                  fn63("walkRight", "walkRightKey")
                  fn63("tpBat", "tpBatKey")
                  fn63("dropBrainrot", "dropBrainrotKey")
                  fn63("bodyLock", "bodyLockKey")
                  fn63("instaReset", "instaResetKey")
                  local setState = nil

                  if v85 then
                    setState = v85.setState
                  end

                  if setState then
                    pcall(function()
                      v85.setState(Config.speedToggled)
                    end)
                  end

                  if carry and carry.setState then
                    pcall(function()
                      carry.setState(Config.speedToggled)
                    end)
                  end

                  flag22 = true
                end)
              end

              pcall(fn41)

              pcall(function()
                LocalPlayer.OnTeleport:Connect(function()
                  pcall(fn61)
                end)
              end)
            end
          end
        end

        do
          local fn55, fn56

          do
            do
              fn53 = function(arg, arg2)
                local flag22 = false
                local position = nil
                local position2 = nil
                local v96 = nil

                arg.InputBegan:Connect(function(input)
                  if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                    flag22 = true
                    position = input.Position
                    position2 = arg.Position

                    input.Changed:Connect(function()
                      if input.UserInputState == Enum.UserInputState.End then
                        flag22 = false

                        if arg2 then
                          arg2(arg.Position)
                        end
                      end
                    end)
                  end
                end)

                arg.InputChanged:Connect(function(input)
                  if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
                    v96 = input
                  end
                end)

                UserInputService.InputChanged:Connect(function(input)
                  if input == v96 and flag22 then
                    local n35 = input.Position - position
                    arg.Position = UDim2.new(position2.X.Scale, position2.X.Offset + n35.X, position2.Y.Scale, position2.Y.Offset + n35.Y)
                  end
                end)

                UserInputService.InputEnded:Connect(function(input)
                  if
                    (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) and flag22
                  then
                    flag22 = false

                    if arg2 then
                      arg2(arg.Position)
                    end
                  end
                end)
              end

              fn55 = function() end

              fn42 = function(speedProfile)
                if speedProfile ~= "Normal" and speedProfile ~= "Lagger" and speedProfile ~= "Custom" then
                  speedProfile = "Normal"
                end

                Config.speedProfile = speedProfile
                local setState = nil

                if v95 then
                  setState = v95.setState
                end

                if setState then
                  pcall(function()
                    v95.setState(speedProfile == "Lagger")
                  end)
                end

                if lagger and lagger.setState then
                  pcall(function()
                    lagger.setState(speedProfile == "Lagger")
                  end)
                end

                if custom and custom.setState then
                  pcall(function()
                    custom.setState(speedProfile == "Custom")
                  end)
                end

                saveConfig()
              end

              fn43 = function()
                if Config.speedProfile == "Lagger" then
                  fn42("Normal")
                else
                  fn42("Lagger")
                end
              end

              fn44 = function()
                if Config.speedProfile == "Custom" then
                  fn42("Normal")
                else
                  fn42("Custom")
                end
              end

              do
                local function fn57()
                  local flag22 = Config.speedToggled == true
                  local flag23

                  if Config.autoSwitchSpeedEnabled then
                    local character = LocalPlayer.Character
                    character = character and character:FindFirstChildOfClass("Humanoid")

                    if character and character.WalkSpeed < 25 then
                      flag23 = true
                    else
                      flag23 = flag22
                    end
                  else
                    flag23 = flag22
                  end

                  return flag23
                end

                fn48 = function()
                  local speedProfile = Config.speedProfile or "Normal"
                  local laggerCarrySpeed = fn57()
                  if speedProfile == "Lagger" then
                    laggerCarrySpeed = laggerCarrySpeed and (Config.laggerCarrySpeed or 15) or Config.laggerNormalSpeed or 35
                    return laggerCarrySpeed
                  end

                  if speedProfile == "Custom" then
                    laggerCarrySpeed = laggerCarrySpeed and (Config.customCarrySpeed or 35)
                    return laggerCarrySpeed or Config.customNormalSpeed or 70
                  end
                  return laggerCarrySpeed and (Config.normalCarrySpeed or 29) or Config.normalSpeed or 59
                end
              end
            end

            do
              local raycastParams = RaycastParams.new()
              raycastParams.FilterType = Enum.RaycastFilterType.Exclude
              raycastParams.IgnoreWater = true

              pcall(function()
                raycastParams.RespectCanCollide = true
              end)

              local tbl26 = {}
              local vector = Vector3.zero

              local function fn57(arg, arg2, arg3, arg4)
                local ok, result = pcall(function()
                  local filterDescendantsInstances = { arg2 }

                  for _, player in ipairs(Players:GetPlayers()) do
                    if player ~= LocalPlayer and player.Character then
                      table.insert(filterDescendantsInstances, player.Character)
                    end
                  end

                  raycastParams.FilterDescendantsInstances = filterDescendantsInstances
                  return workspace:Raycast(arg.Position, arg3 * (3 + math.min(arg4 or 60, 150) * 0.035), raycastParams)
                end)

                if not ok or not result then
                  return arg3
                end

                if result.Position.Y < arg.Position.Y - 1.2 then
                  return arg3
                end
                local normal = result.Normal
                local x = normal.X
                local z = normal.Z
                local v96 = math.sqrt(x * x + z * z)
                if v96 < 0.05 then
                  return arg3
                end
                local n35 = x / v96
                local n36 = z / v96
                local n37 = arg3.X * n35 + arg3.Z * n36
                if n37 >= 0 then
                  return arg3
                end
                local n38 = arg3.X - n35 * n37
                local n39 = arg3.Z - n36 * n37
                if math.sqrt(n38 * n38 + n39 * n39) < 0.15 then
                  return Vector3.zero
                end
                local v97 = math.sqrt(n38 * n38 + n39 * n39)
                return Vector3.new(n38 / v97, 0, n39 / v97)
              end

              fn56 = function()
                for _, v96 in ipairs(tbl26) do
                  pcall(function()
                    v96:Disconnect()
                  end)
                end

                tbl26 = {}
                local character = LocalPlayer.Character
                if not character then
                  return
                end
                local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
                if not humanoidRootPart then
                  return
                end

                pcall(function()
                  local v96 = getrawmetatable(humanoidRootPart)
                  setreadonly(v96, false)
                  local Theme = v96.__index
                  local newindex = v96.__newindex

                  v96.__index = newcclosure(function(arg, arg2)
                    if arg == humanoidRootPart and (arg2 == "AssemblyLinearVelocity" or arg2 == "Velocity") then
                      local ok, result = pcall(checkcaller)

                      if ok and result then
                        local ok2, result2 = pcall(Theme, arg, arg2)
                        if ok2 then
                          return result2
                        end
                      elseif Config.speedEnabled ~= false then
                        return vector
                      end
                    end

                    local ok, result = pcall(Theme, arg, arg2)
                    if ok then
                      return result
                    end
                    return vector
                  end)

                  v96.__newindex = newcclosure(function(arg, arg2, arg3)
                    if arg == humanoidRootPart and (arg2 == "AssemblyLinearVelocity" or arg2 == "Velocity") then
                      local ok, result = pcall(checkcaller)

                      if ok and result then
                        if pcall(newindex, arg, arg2, arg3) then
                          return
                        end
                      elseif Config.speedEnabled ~= false then
                        vector = arg3
                        return
                      end
                    end

                    pcall(newindex, arg, arg2, arg3)
                  end)
                end)

                local connection = RunService.PreSimulation:Connect(function()
                  if Config.speedEnabled == false then
                    return
                  end

                  if tbl23 and tbl23.active then
                    return
                  end

                  if flag21 then
                    return
                  end

                  if Config.circleEnabled then
                    return
                  end
                  local humanoid = tbl22.humanoid and tbl22.humanoid.Parent and tbl22.humanoid
                    or character:FindFirstChildOfClass("Humanoid")

                  if humanoid and humanoid.Health > 0 and humanoidRootPart and humanoidRootPart.Parent then
                    if humanoidRootPart.Position.Y < -20 then
                      if fn40 then
                        fn40(true)
                      end

                      return
                    end

                    local v96 = fn48()

                    if v96 >= 15.5 and v96 <= 16.5 then
                      if vector ~= Vector3.zero then
                        vector = Vector3.zero
                      end

                      return
                    end

                    local moveDirection = humanoid.MoveDirection
                    local magnitude = moveDirection.Magnitude

                    if magnitude > 0.05 then
                      local y = humanoidRootPart.AssemblyLinearVelocity.Y

                      if y ~= y then
                        y = 0
                      end

                      local n35 = math.clamp(y, -80, 80)
                      local v97 =
                        fn57(humanoidRootPart, character, Vector3.new(moveDirection.X / magnitude, 0, moveDirection.Z / magnitude), v96)

                      if v97.Magnitude < 0.05 then
                        vector = Vector3.new(0, n35, 0)
                        humanoidRootPart.AssemblyLinearVelocity = Vector3.new(0, n35, 0)
                      else
                        vector = Vector3.new(v97.X * 20, n35, v97.Z * 16)
                        humanoidRootPart.AssemblyLinearVelocity = Vector3.new(v97.X * v96, n35, v97.Z * v96)
                      end
                    elseif vector ~= Vector3.zero then
                      vector = Vector3.zero
                    end
                  end
                end)

                table.insert(tbl26, connection)
              end

              pcall(fn56)

              LocalPlayer.CharacterAdded:Connect(function()
                task.wait(0.1)
                pcall(fn56)
              end)

              pcall(function()
                workspace:GetPropertyChangedSignal("Gravity"):Connect(function()
                  if workspace.Gravity > 300 then
                    workspace.Gravity = 196.2
                  end
                end)

                if workspace.Gravity > 300 then
                  workspace.Gravity = 196.2
                end
              end)

              fn54 = function(arg, arg2, arg3, arg4, arg5)
                if not arg or not arg3 then
                  return
                end
                local y = arg.AssemblyLinearVelocity.Y

                if y ~= y then
                  y = 0
                end

                if 0.1 < arg4.Magnitude then
                  local unit = arg4.Unit
                  local vector2 = Vector3.new(unit.X, 0, unit.Z)
                  local unit2

                  if vector2.Magnitude > 0.05 then
                    unit2 = vector2.Unit
                  else
                    unit2 = Vector3.zero
                  end

                  local vector3 = unit2.Magnitude > 0.1 and fn57(arg, arg3, unit2, arg5) or Vector3.zero

                  if vector3.Magnitude < 0.1 then
                    vector = Vector3.new(0, y, 0)
                    arg.AssemblyLinearVelocity = Vector3.new(0, y, 0)
                  else
                    vector = Vector3.new(vector3.X * 16, y, vector3.Z * 16)
                    arg.AssemblyLinearVelocity = Vector3.new(vector3.X * arg5, y, vector3.Z * arg5)
                  end
                else
                  vector = Vector3.new(0, y, 0)
                end
              end
            end
          end

          do
            local function fn57()
              pcall(fn56)
            end

            LocalPlayer.CharacterAdded:Connect(function(character)
              task.wait(0.05)
              local humanoid = character:WaitForChild("Humanoid", 10)

              if humanoid and Config.antiDieEnabled then
                pcall(function()
                  humanoid.RequiresNeck = false
                  humanoid.BreakJointsOnDeath = false
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
                end)
              end

              pcall(function()
                local torso = character:FindFirstChild("Torso") or character:FindFirstChild("UpperTorso")
                local head = character:FindFirstChild("Head")

                if torso then
                  torso.CanCollide = true
                end

                if head then
                  head.CanCollide = true
                end
              end)
            end)

            fn45 = function(character)
              fn55()
              cachedMoveDirection = Vector3.zero
              cachedInputTime = 0
              local v96 = tbl22
              local v97 = tbl22
              tbl22.humanoid = nil
              v96.hrp = nil
              v97.speedLabel = nil
              local v98 = tbl22
              tbl22.lastPos = nil
              v98.lastTime = nil
              local humanoid = character:WaitForChild("Humanoid", 12)
              local humanoidRootPart = character:WaitForChild("HumanoidRootPart", 10)
              if not (humanoid and humanoidRootPart) then
                return
              end
              tbl22.humanoid = humanoid
              tbl22.hrp = humanoidRootPart
              local head = character:FindFirstChild("Head") or character:WaitForChild("Head", 12)

              if head then
                local speedBillboard = head:FindFirstChild("SpeedBillboard")

                if speedBillboard then
                  speedBillboard:Destroy()
                end

                local billboardGui = Instance.new("BillboardGui")
                billboardGui.Name = "SpeedBillboard"
                billboardGui.Size = UDim2.new(0, 220, 0, 80)
                billboardGui.StudsOffset = Vector3.new(0, 3, 0)
                billboardGui.AlwaysOnTop = true
                billboardGui.ResetOnSpawn = false
                billboardGui.Parent = head
                local textLabel = Instance.new("TextLabel")
                textLabel.Name = "RagdollLabel"
                textLabel.Size = UDim2.new(1, 0, 0.35, 0)
                textLabel.Position = UDim2.new(0, 0, 0, 0)
                textLabel.BackgroundTransparency = 1
                textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                textLabel.Font = Enum.Font.MontserratBlack
                textLabel.TextScaled = true
                textLabel.TextStrokeTransparency = 0
                textLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
                textLabel.Text = "2.5s"
                textLabel.Visible = false
                textLabel.Parent = billboardGui
                tbl22.ragLabel = textLabel
                local textLabel2 = Instance.new("TextLabel")
                textLabel2.Name = "DiscordLabel"
                textLabel2.Size = UDim2.new(1, 0, 0.32, 0)
                textLabel2.Position = UDim2.new(0, 0, 0.35, 0)
                textLabel2.BackgroundTransparency = 1
                textLabel2.Text = "lukinhas ama piru do João"
                textLabel2.TextColor3 = Color3.fromRGB(255, 255, 255)
                textLabel2.Font = Enum.Font.MontserratBlack
                textLabel2.TextScaled = true
                textLabel2.TextStrokeTransparency = 0
                textLabel2.Parent = billboardGui
                local textLabel3 = Instance.new("TextLabel")
                textLabel3.Name = "SpeedLabel"
                textLabel3.Size = UDim2.new(1, 0, 0.3, 0)
                textLabel3.Position = UDim2.new(0, 0, 0.5, 0)
                textLabel3.BackgroundTransparency = 1
                textLabel3.TextColor3 = Color3.fromRGB(255, 255, 255)
                textLabel3.Font = Enum.Font.MontserratBlack
                textLabel3.TextScaled = true
                textLabel3.TextStrokeTransparency = 0
                textLabel3.AutoLocalize = false
                textLabel3.Text = "Speed: 0.0"
                textLabel3.Parent = billboardGui
                tbl22.speedLabel = textLabel3

                pcall(function()
                  humanoid.Died:Connect(function()
                    pcall(function()
                      billboardGui.Enabled = false
                    end)
                  end)
                end)
              end
            end

            LocalPlayer.CharacterAdded:Connect(fn45)
            LocalPlayer.CharacterRemoving:Connect(fn55)

            if LocalPlayer.Character then
              task.spawn(fn45, LocalPlayer.Character)
            end

            fn57()
          end
        end

        local n35 = 0

        RunService.RenderStepped:Connect(function(deltaTime)
          local speedLabel = tbl22.speedLabel
          local hrp = tbl22.hrp

          if not (speedLabel and hrp and hrp.Parent) then
            local character = LocalPlayer.Character

            if character then
              hrp = character:FindFirstChild("HumanoidRootPart")
              tbl22.hrp = hrp
              local head = character:FindFirstChild("Head")
              head = head and head:FindFirstChild("SpeedBillboard")
              speedLabel = head and head:FindFirstChild("SpeedLabel")
              tbl22.speedLabel = speedLabel
            end
          end

          if not (speedLabel and hrp) then
            return
          end
          local humanoid = LocalPlayer.Character and LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
          local n36

          if humanoid and humanoid.MoveDirection.Magnitude > 0.1 then
            if Config.speedEnabled ~= false then
              n36 = fn48()
            else
              n36 = 16
            end
          else
            n36 = 0
          end

          n35 += (n36 - n35) * math.clamp((deltaTime or 0.016) * 20, 0, 1)

          if n35 < 0.15 then
            n35 = 0
          end

          local lastSpeedVal = math.floor(n35 * 10 + 0.5)

          if lastSpeedVal ~= tbl22._lastSpeedVal then
            tbl22._lastSpeedVal = lastSpeedVal
            speedLabel.Text = string.format("Speed: %.1f", lastSpeedVal / 10)
          end
        end)
      end

      do
        do
          local n35, v95, tbl26, tbl27

          do
            do
              n35 = 1
              v95 = 0.3
              tbl26 = {}

              do
                local vector = Vector3.new(-475.25999755859374, -9.1400003433227539, 92.949996948242188)
                local vector2 = Vector3.new(-485.0200134277344, -7.8899998664855957, 93.620002746582031)
                local vector3 = Vector3.new(-477.010009765625, -8.9300003051757812, 93.069999694824219)
                local vector4 = Vector3.new
                tbl26[1] = vector
                tbl26[2] = vector2
                tbl26[3] = vector3

                do
                  local values = table.pack(vector4(-475.26998901367188, -6.5799999237060547, 21.549999237060547))
                  table.move(values, 1, values.n, 4, tbl26)
                end
              end
            end

            tbl27 = {}

            do
              local vector = Vector3.new(-475.2299865722656, -9.0100002288818359, 28.510000228881836)
              local vector2 = Vector3.new(-485.02999877929688, -7.8899998664855957, 27.790000915527344)
              local vector3 = Vector3.new(-476.92001342773438, -8.9700002670288086, 28.030000686645508)
              local vector4 = Vector3.new
              tbl27[1] = vector
              tbl27[2] = vector2
              tbl27[3] = vector3

              do
                local values = table.pack(vector4(-476.17999267578125, -6.0999999046325684, 97.730003356933594))
                table.move(values, 1, values.n, 4, tbl27)
              end
            end
          end

          do
            local tbl28

            do
              do
                local vector = Vector3.new

                tbl28 = {
                  left = {
                    Vector3.new(-476.48, -6.28, 92.73),
                    vector(-483.12, -4.95, 94.8),
                  },
                  right = {
                    Vector3.new(-476.16, -6.52, 25.62),
                    vector(-483.06, -5.03, 25.48),
                  },
                  leftFace = Vector3.new(-482.25, -4.96, 92.09),
                  rightFace = Vector3.new(-482.06, -6.93, 35.47),
                }
              end
            end

            local fn55, fn56

            do
              fn49 = function()
                if tbl23.connection then
                  tbl23.connection:Disconnect()
                end

                if autoPlayButton then
                  autoPlayButton.setState(false)
                end

                local active = Config.autoWalkMode == 2 and tbl23.active
                tbl23.active = false
                tbl23.waypoints = {}
                tbl23.index = 1
                tbl23.useCarry = false
                tbl23.pauseTime = 0
                tbl23.currentPathName = nil
                tbl23.connection = nil
                tbl23.faceTarget = nil
                tbl23.holding = false
                tbl23.holdCF = nil

                if v84 then
                  v84.PlaneVelocity = Vector2.zero
                  v84.Enabled = false
                end

                if active and Config.autoSwitchSpeedEnabled then
                  Config.speedToggled = true
                  local setState = nil

                  if v85 then
                    setState = v85.setState
                  end

                  if setState then
                    pcall(function()
                      v85.setState(true)
                    end)
                  end

                  if carry and carry.setState then
                    pcall(function()
                      carry.setState(true)
                    end)
                  end

                  saveConfig()
                end
              end

              do
                local function fn57(arg, currentPathName, faceTarget)
                  if tbl23.active and tbl23.currentPathName == currentPathName then
                    fn49()
                    return
                  end
                  fn49()
                  if not arg or #arg == 0 then
                    return
                  end
                  tbl23.waypoints = table.clone(arg)
                  tbl23.index = 1
                  tbl23.useCarry = false
                  tbl23.pauseTime = 0.07
                  tbl23.active = true
                  tbl23.currentPathName = currentPathName
                  tbl23.faceTarget = faceTarget

                  if autoPlayButton then
                    autoPlayButton.setState(true)
                  end

                  tbl23.connection = RunService.RenderStepped:Connect(function(deltaTime)
                    if not tbl23.active then
                      return
                    end
                    local character = LocalPlayer.Character
                    if not character then
                      fn49()
                      return
                    end
                    local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
                    if not humanoidRootPart then
                      return
                    end

                    if #tbl23.waypoints < tbl23.index then
                      local faceTarget2 = tbl23.faceTarget
                      if not faceTarget2 then
                        fn49()
                        return
                      end

                      if not tbl23.holding then
                        tbl23.holding = true

                        if Config.autoWalkMode == 2 then
                          Config.speedToggled = true
                          local setState

                          if v85 then
                            setState = v85.setState
                          end

                          if setState then
                            pcall(function()
                              v85.setState(true)
                            end)
                          end

                          if carry and carry.setState then
                            pcall(function()
                              carry.setState(true)
                            end)
                          end

                          saveConfig()
                        end

                        pcall(function()
                          local position = humanoidRootPart.Position
                          local vector = Vector3.new(faceTarget2.X, position.Y, faceTarget2.Z)

                          if (vector - position).Magnitude > 0.05 then
                            humanoidRootPart.CFrame = CFrame.new(position, vector)
                          end
                        end)
                      end

                      local humanoid = character:FindFirstChildOfClass("Humanoid")
                      if not humanoid or humanoid.Health <= 0 then
                        fn49()
                        return
                      end
                      local state = humanoid:GetState()
                      if
                        humanoid.MoveDirection.Magnitude > 0.05
                        or state == Enum.HumanoidStateType.Physics
                        or state == Enum.HumanoidStateType.Ragdoll
                      then
                        fn49()
                        return
                      end

                      if v84 then
                        v84.PlaneVelocity = Vector2.zero
                        v84.Enabled = false
                      end

                      humanoidRootPart.AssemblyLinearVelocity = Vector3.new(0, humanoidRootPart.AssemblyLinearVelocity.Y, 0)
                      return
                    end

                    local v96 = tbl23.waypoints[tbl23.index]
                    local position = humanoidRootPart.Position

                    if Vector3.new(v96.X - position.X, 0, v96.Z - position.Z).Magnitude <= n35 then
                      if tbl23.index == 2 then
                        tbl23.pauseTime = v95
                      end

                      tbl23.index = tbl23.index + 1

                      if tbl23.index > 2 and not tbl23.useCarry then
                        tbl23.useCarry = true
                      end

                      return
                    end

                    if tbl23.pauseTime > 0 then
                      tbl23.pauseTime = tbl23.pauseTime - deltaTime

                      if v84 then
                        v84.PlaneVelocity = Vector2.zero
                        v84.Enabled = false
                      end

                      humanoidRootPart.AssemblyLinearVelocity = Vector3.new(0, humanoidRootPart.AssemblyLinearVelocity.Y, 0)
                      return
                    end

                    local unit = ((v96 - position) * Vector3.new(1, 0, 1)).Unit
                    local normalSpeed = Config.normalSpeed or 59
                    fn54(humanoidRootPart, character:FindFirstChildOfClass("Humanoid"), character, unit, normalSpeed, deltaTime)
                  end)
                end

                fn55 = function()
                  if Config.circleEnabled then
                    fn32(false)
                  end

                  if Config.autoWalkMode == 2 then
                    fn57(tbl28.left, "left", tbl28.leftFace)
                  else
                    fn57(tbl26, "left")
                  end
                end

                fn56 = function()
                  if Config.circleEnabled then
                    fn32(false)
                  end

                  if Config.autoWalkMode == 2 then
                    fn57(tbl28.right, "right", tbl28.rightFace)
                  else
                    fn57(tbl27, "right")
                  end
                end
              end
            end

            do
              local function fn57()
                local v96 = string.lower(LocalPlayer.Name)
                local v97 = string.lower(LocalPlayer.DisplayName)
                local plots = workspace:FindFirstChild("Plots") or workspace:FindFirstChild("plots")

                if plots then
                  for _, child in pairs(plots:GetChildren()) do
                    local plotSign = child:FindFirstChild("PlotSign") or child:FindFirstChild("Sign")
                    local flag22 = false

                    if plotSign then
                      local yourBase = plotSign:FindFirstChild("YourBase")

                      if yourBase and yourBase:IsA("BillboardGui") and yourBase.Enabled then
                        flag22 = true
                      end

                      if not flag22 then
                        for _, descendant in pairs(plotSign:GetDescendants()) do
                          if descendant:IsA("TextLabel") and descendant.Text ~= "" and descendant.Text ~= "Empty Base" then
                            local v98 = string.lower(descendant.Text)
                            if string.find(v98, v96, 1, true) or string.find(v98, v97, 1, true) then
                              flag22 = true
                              break
                            end
                          end
                        end
                      end
                    end

                    if flag22 then
                      local spawn_ = child:FindFirstChild("Spawn")
                        or child:FindFirstChild("Plot")
                        or child:FindFirstChild("Base")
                        or child:IsA("Model") and child.PrimaryPart
                      spawn_ = spawn_ and spawn_.Position.Z
                      local z

                      if spawn_ then
                        z = spawn_
                      else
                        z = child:IsA("Model") and child:GetPivot().Position.Z
                      end

                      if z then
                        return z < 50 and "RIGHT" or "LEFT"
                      end
                    end
                  end
                end

                local character = LocalPlayer.Character
                character = character and character:FindFirstChild("HumanoidRootPart")
                if character then
                  return character.Position.Z < 50 and "RIGHT" or "LEFT"
                end
                return nil
              end

              fn46 = function()
                if tbl23.active then
                  fn49()
                  return
                end
                local v96 = fn57()

                if v96 == "RIGHT" then
                  fn55()
                elseif v96 == "LEFT" then
                  fn56()
                else
                  local character = LocalPlayer.Character
                  character = character and character:FindFirstChild("HumanoidRootPart")

                  if character and character.Position.Z < 50 then
                    fn55()
                  else
                    fn56()
                  end
                end
              end
            end
          end
        end

        local tbl26

        do
          do
            local vector = Vector3.new

            tbl26 = {
              Vector3.new(-487.583, -4.943, 97.694),
              vector(-487.828, -4.959, 23.77),
            }
          end
        end

        tbl25 = {}

        do
          local v95 = nil
          v93 = nil
          v91 = nil
          v94 = nil
          v92 = nil
          n33 = 0
          now2 = tick()
          n32 = 60
          v90 = 0
          n34 = 45

          fn52 = function(arg, arg2)
            local markerColor = Config.markerColor or "White"

            if markerColor == "Accent" then
              local v96 = color
              local color2

              if color then
                color2 = v96
              else
                color2 = Color3.fromRGB(225, 45, 185)
              end

              return color2
            end

            if markerColor == "Neon Cyan" then
              return Color3.fromRGB(0, 240, 255)
            end

            if markerColor == "Lime Green" then
              return Color3.fromRGB(80, 255, 120)
            end

            if markerColor == "Hot Pink" then
              return Color3.fromRGB(255, 80, 180)
            end

            if markerColor == "Dynamic" then
              local n35 = math.clamp(arg / math.max(arg2, 0.01), 0, 1)
              if n35 > 0.5 then
                return Color3.fromRGB(255, math.floor(60 + (1 - (n35 - 0.5) * 2) * 160), 60)
              end
              return Color3.fromRGB(math.floor(60 + n35 * 2 * 195), 255, 60)
            end

            return Color3.fromRGB(255, 255, 255)
          end

          fn50 = function()
            local v96 = v95

            pcall(function()
              for _, child in ipairs(playerGui:GetChildren()) do
                if child.Name == "AutoGrabBarGui" and child ~= v96 then
                  child:Destroy()
                end
              end
            end)

            pcall(function()
              local hui = gethui and gethui()

              if hui then
                for _, child in ipairs(hui:GetChildren()) do
                  if child.Name == "AutoGrabBarGui" and child ~= v96 then
                    child:Destroy()
                  end
                end
              end
            end)
          end

          fn51 = function()
            if v95 then
              pcall(function()
                v95:Destroy()
              end)
            end

            v95 = nil
            v93 = nil
            v91 = nil
            v94 = nil
            v92 = nil
            local autoGrabBarGui = playerGui:FindFirstChild("AutoGrabBarGui")

            if autoGrabBarGui then
              pcall(function()
                autoGrabBarGui:Destroy()
              end)
            end

            pcall(function()
              local hui = gethui and gethui()

              if hui then
                local autoGrabBarGui2 = hui:FindFirstChild("AutoGrabBarGui")

                if autoGrabBarGui2 then
                  autoGrabBarGui2:Destroy()
                end
              end
            end)

            fn50()
            local screenGui = Instance.new("ScreenGui")
            screenGui.Name = "AutoGrabBarGui"
            screenGui.ResetOnSpawn = false
            screenGui.DisplayOrder = 9990
            screenGui.IgnoreGuiInset = true
            screenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

            pcall(function()
              local hui = gethui and gethui()

              if hui then
                screenGui.Parent = hui
              end
            end)

            if not screenGui.Parent then
              screenGui.Parent = playerGui
            end

            local frame = Instance.new("Frame")
            frame.Name = "BarContainer"
            frame.Size = UDim2.fromOffset(300, 36)

            local function fn55(arg, arg2)
              local num = tonumber(arg)
              if num ~= num or num == math.huge or num == -math.huge then
                return arg2
              end
              return num or arg2
            end

            local autoGrabBarPosition = Config.autoGrabBarPosition
            local v96 = 0.5
            local n35 = -150
            local n36 = -115
            local n37 = 1
            local v97

            if type(autoGrabBarPosition) ~= "table" then
              v97 = v96
            else
              v97 = fn55(autoGrabBarPosition.xScale, v96)
              n35 = fn55(autoGrabBarPosition.xOffset, -150)
              n37 = fn55(autoGrabBarPosition.yScale, 1)
              n36 = fn55(autoGrabBarPosition.yOffset, -115)
            end

            local currentCamera = workspace.CurrentCamera
            currentCamera = currentCamera and currentCamera.ViewportSize or Vector2.new(1280, 720)

            if currentCamera.X < 200 or currentCamera.Y < 150 then
              currentCamera = Vector2.new(1280, 720)
            end

            local n38 = n37 * currentCamera.Y + n36
            local n39 = math.clamp(v97 * currentCamera.X + n35, 0, math.max(0, currentCamera.X - 300))
            local n40 = math.clamp(n38, 0, math.max(0, currentCamera.Y - 36))
            frame.Position = UDim2.new(0, math.floor(n39), 0, math.floor(n40))
            frame.BackgroundColor3 = Color3.fromRGB(15, 15, 20)
            frame.BackgroundTransparency = 0.2
            frame.BorderSizePixel = 0
            frame.Active = true
            frame.ClipsDescendants = true
            local uiCorner = Instance.new("UICorner")
            uiCorner.CornerRadius = UDim.new(1, 0)
            uiCorner.Parent = frame
            local uiStroke = Instance.new("UIStroke")
            uiStroke.Thickness = 1.5
            uiStroke.Color = Color3.fromRGB(35, 35, 45)
            uiStroke.Transparency = 0.25
            uiStroke.Parent = frame
            local frame2 = Instance.new("Frame")
            frame2.Name = "BarFill"
            frame2.Position = UDim2.new(0, 0, 0, 0)
            frame2.Size = UDim2.new(0, 0, 1, 0)
            frame2.BackgroundColor3 = color or Color3.fromRGB(190, 32, 168)
            frame2.BorderSizePixel = 0
            local uiCorner2 = Instance.new("UICorner")
            uiCorner2.CornerRadius = UDim.new(1, 0)
            uiCorner2.Parent = frame2
            local uiGradient = Instance.new("UIGradient")
            uiGradient.Rotation = 0
            local new = ColorSequenceKeypoint.new
            local v98 = 1
            local color2 = Color3.fromRGB

            uiGradient.Color = ColorSequence.new({
              ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 255, 255)),
              new(v98, color2(210, 210, 210)),
            })

            uiGradient.Parent = frame2
            frame2.Parent = frame
            local textLabel = Instance.new("TextLabel")
            textLabel.Name = "StealLabel"
            textLabel.Position = UDim2.fromOffset(20, 0)
            textLabel.Size = UDim2.new(0, 65, 1, 0)
            textLabel.BackgroundTransparency = 1
            textLabel.Font = Enum.Font.MontserratBlack
            textLabel.Text = "STEAL"
            textLabel.TextSize = 13
            textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
            textLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
            textLabel.TextStrokeTransparency = 0.3
            textLabel.TextXAlignment = Enum.TextXAlignment.Left
            textLabel.TextYAlignment = Enum.TextYAlignment.Center
            textLabel.ZIndex = 5
            textLabel.Parent = frame
            local instance = Instance.new("TextLabel")
            instance.Name = "PercentLabel"
            instance.Position = UDim2.new(0.46, -25, 0, 0)
            instance.Size = UDim2.new(0, 55, 1, 0)
            instance.BackgroundTransparency = 1
            instance.Font = Enum.Font.MontserratBlack
            instance.Text = "0%"
            instance.TextSize = 13
            instance.TextColor3 = Color3.fromRGB(255, 255, 255)
            instance.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
            instance.TextStrokeTransparency = 0.3
            instance.TextXAlignment = Enum.TextXAlignment.Center
            instance.TextYAlignment = Enum.TextYAlignment.Center
            instance.ZIndex = 10
            instance.Parent = frame
            local textLabel2 = Instance.new("TextLabel")
            textLabel2.Name = "StatsLabel"
            textLabel2.Position = UDim2.new(1, -135, 0, 0)
            textLabel2.Size = UDim2.new(0, 120, 1, 0)
            textLabel2.BackgroundTransparency = 1
            textLabel2.Font = Enum.Font.MontserratBlack
            textLabel2.Text = "FPS:60  PING:45"
            textLabel2.TextSize = 16
            textLabel2.TextColor3 = Color3.fromRGB(255, 255, 255)
            textLabel2.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
            textLabel2.TextStrokeTransparency = 0.3
            textLabel2.TextXAlignment = Enum.TextXAlignment.Right
            textLabel2.TextYAlignment = Enum.TextYAlignment.Center
            textLabel2.ZIndex = 5
            textLabel2.Parent = frame
            frame.Parent = screenGui
            v95 = screenGui
            v93 = frame
            v91 = frame2
            v94 = instance
            v92 = textLabel2
            fn50()

            pcall(function()
              fn53(frame, function(arg)
                Config.autoGrabBarPosition = { xScale = arg.X.Scale, xOffset = arg.X.Offset, yScale = arg.Y.Scale, yOffset = arg.Y.Offset }
                saveConfig()
              end)
            end)
          end
        end

        pcall(function()
          for _, child in ipairs(WorkspaceService:GetChildren()) do
            if child.Name:find("^AutoGrabWorldMarker_") then
              pcall(function()
                child:Destroy()
              end)
            end
          end

          tbl25 = {}

          for i, v95 in ipairs(tbl26) do
            local part = Instance.new("Part")
            part.Name = "AutoGrabWorldMarker_" .. tostring(i)
            part.Size = Vector3.new(1, 1, 1)
            part.Position = v95
            part.Transparency = 1
            part.Anchored = true
            part.CanCollide = false
            part.CanTouch = false
            part.CanQuery = false
            part.Parent = WorkspaceService
            local billboardGui = Instance.new("BillboardGui")
            billboardGui.Name = "CountdownGui"
            billboardGui.Adornee = part
            billboardGui.Size = UDim2.fromOffset(240, 40)
            billboardGui.StudsOffset = Vector3.new(0, 2.5, 0)
            billboardGui.AlwaysOnTop = true
            billboardGui.MaxDistance = 1000
            billboardGui.ResetOnSpawn = false
            billboardGui.Parent = part
            local textLabel = Instance.new("TextLabel")
            textLabel.Name = "TimeLabel"
            textLabel.Size = UDim2.fromScale(1, 1)
            textLabel.BackgroundTransparency = 1
            textLabel.Text = "1.30s"
            textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
            textLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
            textLabel.TextStrokeTransparency = 0.2
            textLabel.Font = Enum.Font.MontserratBlack
            textLabel.TextSize = 28
            textLabel.TextXAlignment = Enum.TextXAlignment.Center
            textLabel.TextYAlignment = Enum.TextYAlignment.Center
            textLabel.Parent = billboardGui
            table.insert(tbl25, textLabel)
          end
        end)
      end
    end

    do
      local connection, fn53

      do
        do
          do
            pcall(fn51)
            _G.HookAutoGrabBarGen = (tonumber(_G.HookAutoGrabBarGen) or 0) + 1

            do
              local hookAutoGrabBarGen = _G.HookAutoGrabBarGen
              local n35 = 0

              RunService.RenderStepped:Connect(function()
                if hookAutoGrabBarGen ~= _G.HookAutoGrabBarGen then
                  return
                end

                if tick() - n35 > 2 then
                  n35 = tick()

                  if not v93 or not v93.Parent then
                    pcall(fn51)
                  end

                  fn50()
                end

                if #tbl25 == 0 and not v93 then
                  return
                end
                local flag22 = tbl24.active and tbl24.startTime > 0
                local autoGrabEnabled = Config.autoGrabEnabled

                if not autoGrabEnabled and _G.VampireStealModes and _G.VampireStealModes.State then
                  autoGrabEnabled = _G.VampireStealModes.State.Enabled == true
                end

                local text, n36

                if autoGrabEnabled then
                  if flag22 then
                    local startTime = tbl24.startTime
                    local n37 = tick() - startTime

                    if Config.autoGrabVersion == 2 then
                      if tbl24.phase == "waitingRange" then
                        text = "READY"
                        n36 = 0.2
                      else
                        n36 = math.max(0, 1.3 - n37)
                        text = string.format("%.2fs", n36)
                      end
                    else
                      n36 = math.max(0, 1.3 - n37)
                      text = string.format("%.2fs", n36)
                    end
                  else
                    text = string.format("%.2fs", 1.3)
                    n36 = 1.3
                  end
                else
                  text = ""
                  n36 = 1.3
                end

                n33 += 1
                local now3 = tick()

                if now3 - now2 >= 0.4 then
                  n32 = math.floor(n33 / (now3 - now2))
                  n33 = 0
                  now2 = now3
                end

                if now3 - v90 >= 1 then
                  v90 = now3

                  pcall(function()
                    local Stats = game:GetService("Stats")
                    Stats = Stats and Stats:FindFirstChild("Network")
                    Stats = Stats and Stats:FindFirstChild("ServerStatsItem")
                    Stats = Stats and Stats:FindFirstChild("Data Ping")

                    if Stats then
                      n34 = math.floor(Stats:GetValue())
                    end
                  end)
                end

                local v95 = fn52(n36, 1.3)
                local v96 = color

                if not color then
                  v96 = ACCENT_MAP and ACCENT_MAP[Config.accentName]
                end

                if not v96 then
                  Color3.fromRGB(190, 32, 168)
                end

                local markerDisplayStyle = Config.markerDisplayStyle or "Both (Hitmarker + Bar)"
                local visible = autoGrabEnabled
                  and (markerDisplayStyle == "Both (Hitmarker + Bar)" or markerDisplayStyle == "Hitmarker Only")
                autoGrabEnabled = autoGrabEnabled and (markerDisplayStyle == "Both (Hitmarker + Bar)" or markerDisplayStyle == "Bar Only")
                local n37 = 0

                if flag22 then
                  if tbl24.progress and tbl24.progress > 0 then
                    n37 = tbl24.progress
                  else
                    local startTime = tbl24.startTime
                    local v97 = 0
                    n37 = math.clamp((tick() - startTime) / 1.3, v97, 1)
                  end
                end

                for _, v97 in ipairs(tbl25) do
                  if v97 and v97.Parent then
                    v97.Visible = visible

                    if visible then
                      v97.Text = text
                      v97.TextColor3 = v95
                    end
                  end
                end

                if v93 and v93.Parent then
                  v93.Visible = autoGrabEnabled

                  if autoGrabEnabled then
                    if v91 then
                      v91.Size = UDim2.new(n37, 0, 1, 0)
                      local n38, n39, n40

                      if n37 < 0.5 then
                        n38 = math.floor(60 + n37 * 2 * 105)
                        n39 = 255
                        n40 = 60
                      else
                        local n41 = (n37 - 0.5) * 2
                        n39 = math.floor(255 - n41 * 205)
                        n38 = math.floor(140 + n41 * 55)
                        n40 = 60
                      end

                      v91.BackgroundColor3 = Color3.fromRGB(n39, n38, n40)
                    end

                    if v94 then
                      v94.Text = string.format("%d%%", math.floor(n37 * 100))
                    end

                    if v92 then
                      v92.Text = string.format("FPS:%d  PING:%d", n32, n34)
                    end
                  end
                end
              end)
            end
          end

          do
            local function fn54()
              local v95 = Config
              _G.HookStealGen = (tonumber(_G.HookStealGen) or 0) + 1
              local hookStealGen = _G.HookStealGen
              local v96 = LocalPlayer

              if _G.VampireStealModes and type(_G.VampireStealModes.Destroy) == "function" then
                pcall(_G.VampireStealModes.Destroy)
              end

              local tbl26 = {
                Enabled = false,
                Mode = "semi",
                Active = false,
                Phase = "idle",
                Progress = 0,
                LastResult = "",
                LastResultTime = 0,
                NormalRadius = 61,
                NormalDuration = 1.3,
                SemiRadius = 9,
                SemiPrimeRange = 80,
                SemiHoldMin = 1.3,
                SemiHoldMax = 2.6,
                SemiEntryDelay = 0.3,
                NormalV2StopAt = 75,
                NormalV2Wait = 1.5,
                TriggerRange = 10,
                PausedUntil = 0,
              }

              tbl26.SemiPrimeRange = tonumber(v95.primeRange) or 80
              tbl26.NormalRadius = tonumber(v95.primeRange) or 61
              local tbl27 = { V1 = "semi", V2 = "normal", V3 = "normalv2" }
              local n35 = 0.03

              if UserInputService and UserInputService.TouchEnabled and not UserInputService.KeyboardEnabled then
                n35 = 0.06
              end

              local tbl28 = {}
              local obj = setmetatable({}, { __mode = "k" })
              local obj2 = setmetatable({}, { __mode = "k" })
              local tbl29 = {}
              local n36 = 0
              local n37 = 0
              local v97 = nil
              local n38 = 0
              local v98 = nil
              local flag22 = false
              local n39 = 0
              local flag23 = false

              local function fn55(arg)
                local v99 = tbl28[arg]

                if v99 then
                  v99:Disconnect()
                  tbl28[arg] = nil
                end
              end

              local function fn56()
                local character = v96.Character

                if character then
                  character = character:FindFirstChild("HumanoidRootPart") or character:FindFirstChild("UpperTorso")
                end

                return character
              end

              local function fn57(arg)
                local now3 = os.clock()
                local v99 = obj2[arg]
                if v99 and now3 - v99.Time < 2 then
                  return v99.Value
                end
                local plotSign = arg and arg:FindFirstChild("PlotSign")
                plotSign = plotSign and plotSign:FindFirstChild("YourBase")
                local isBillboardGui = plotSign and plotSign:IsA("BillboardGui")
                local flag24 = false

                if isBillboardGui then
                  flag24 = plotSign.Enabled == true
                end

                obj2[arg] = { Value = flag24, Time = now3 }
                return flag24
              end

              local function fn58(arg)
                local now3 = os.clock()
                if not arg and now3 - n36 < 0.15 and #tbl29 > 0 then
                  return tbl29
                end
                tbl29 = {}
                n36 = now3
                local plots = workspace:FindFirstChild("Plots")
                if not plots then
                  return tbl29
                end

                for _, child in ipairs(plots:GetChildren()) do
                  if not fn57(child) then
                    local animalPodiums = child:FindFirstChild("AnimalPodiums")

                    if animalPodiums then
                      for _, child2 in ipairs(animalPodiums:GetChildren()) do
                        local base = child2:FindFirstChild("Base")
                        base = base and base:FindFirstChild("Spawn")
                        local promptAttachment = base and base:FindFirstChild("PromptAttachment")

                        if base and base:IsA("BasePart") and promptAttachment then
                          for _, child3 in ipairs(promptAttachment:GetChildren()) do
                            if child3:IsA("ProximityPrompt") then
                              table.insert(tbl29, { Prompt = child3, Spawn = base, Podium = child2, Plot = child })
                              break
                            end
                          end
                        end
                      end
                    end
                  end
                end

                return tbl29
              end

              local function fn59(arg)
                local v99 = fn56()
                if not (v99 and arg and arg.Spawn and arg.Spawn.Parent) then
                  return math.huge
                end
                return (v99.Position - arg.Spawn.Position).Magnitude
              end

              local function fn60(arg)
                local v99 = fn56()
                if not v99 then
                  return nil
                end
                local huge = math.huge
                local v100 = nil

                for _, v101 in ipairs(fn58(false)) do
                  if v101.Prompt.Parent and v101.Spawn.Parent then
                    local magnitude = (v99.Position - v101.Spawn.Position).Magnitude

                    if magnitude <= arg and magnitude < huge then
                      huge = magnitude
                      v100 = v101
                    end
                  end
                end

                return v100
              end

              local function fn61(arg)
                local v99 = obj[arg]
                if v99 then
                  return v99
                end
                local tbl30 = { Hold = {}, Trigger = {}, Ready = true, Fallback = true }

                if getconnections then
                  tbl30.Fallback = not pcall(function()
                    for _, v100 in ipairs(getconnections(arg.PromptButtonHoldBegan)) do
                      if type(v100.Function) == "function" then
                        table.insert(tbl30.Hold, v100.Function)
                      end
                    end

                    for _, v100 in ipairs(getconnections(arg.Triggered)) do
                      if type(v100.Function) == "function" then
                        local function_ = v100.Function
                        local flag24 = false

                        for _, v101 in ipairs(tbl30.Hold) do
                          if v101 == function_ then
                            flag24 = true
                            break
                          end
                        end

                        if not flag24 then
                          table.insert(tbl30.Trigger, function_)
                        end
                      end
                    end
                  end) or #tbl30.Hold == 0 and #tbl30.Trigger == 0
                end

                obj[arg] = tbl30
                return tbl30
              end

              local function fn62(arg)
                for _, v99 in ipairs(arg) do
                  task.spawn(function()
                    pcall(v99)
                  end)
                end
              end

              local function fn63(arg, arg2)
                return (
                  pcall(function()
                    if arg2.Fallback then
                      arg:InputHoldBegin()
                      v98 = arg
                      flag22 = true
                    else
                      fn62(arg2.Hold)
                    end
                  end)
                )
              end

              local function fn64(arg, arg2)
                local ok = pcall(function()
                  if arg2.Fallback then
                    arg:InputHoldEnd()
                    v98 = nil
                    flag22 = false
                  else
                    fn62(arg2.Trigger)
                  end
                end)

                if not ok and fireproximityprompt then
                  ok = pcall(fireproximityprompt, arg)
                end

                return ok
              end

              local function fn65()
                if v98 and flag22 and v98.Parent then
                  pcall(function()
                    v98:InputHoldEnd()
                  end)
                end

                v98 = nil
                flag22 = false
              end

              local function fn66(arg, phase)
                tbl26.Progress = math.clamp(arg or 0, 0, 1)

                if phase then
                  tbl26.Phase = phase
                end

                tbl24.progress = tbl26.Progress
                tbl24.phase = tbl26.Phase
                tbl24.active = tbl26.Active
              end

              local function fn67(arg, lastResult)
                arg.Ready = true
                tbl26.Active = false
                tbl26.Phase = "idle"
                tbl26.LastResult = lastResult or ""
                tbl26.LastResultTime = os.clock()
                fn66(0)
                tbl24.active = false
                tbl24.phase = "idle"
                tbl24.progress = 0
                tbl24.lastResult = lastResult or ""
              end

              local function fn68(arg, arg2)
                return tbl26.Enabled and n39 == arg and arg2 and arg2.Parent
              end

              local function fn69(arg)
                local prompt = arg and arg.Prompt
                if not prompt or not prompt.Parent or tbl26.Active then
                  return
                end
                local now3 = os.clock()
                if now3 < tbl26.PausedUntil or now3 - n37 < 0.1 then
                  return
                end
                local v99 = fn61(prompt)
                if not v99.Ready then
                  return
                end
                v99.Ready = false
                tbl26.Active = true
                tbl26.Phase = "holding"
                n37 = now3
                local v100 = n39
                tbl24.active = true
                tbl24.startTime = tick()
                tbl24.phase = "holding"
                tbl24.progress = 0
                tbl24.label = arg.Prompt and arg.Prompt.Parent and arg.Prompt.Parent.Parent and arg.Prompt.Parent.Parent.Name or "Animal"

                task.spawn(function()
                  if not fn63(prompt, v99) then
                    fn67(v99, "Hold failed")
                    return
                  end
                  local now4 = os.clock()
                  local n40 = math.max(tbl26.NormalDuration, 0.01)

                  while fn68(v100, prompt) and os.clock() - now4 < n40 do
                    fn66((os.clock() - now4) / n40, "holding")
                    RunService.Heartbeat:Wait()
                  end

                  if not fn68(v100, prompt) then
                    fn65()
                    fn67(v99, "Cancelled")
                    return
                  end

                  local v101 = fn64(prompt, v99)

                  if v101 then
                    fn66(1, "done")
                    task.wait(math.max(n40 * 0.08, 0.08))
                  end

                  fn67(v99, v101 and "Stole" or "Failed")
                end)
              end

              local function fn70(arg)
                local prompt = arg and arg.Prompt
                local now3 = os.clock()
                if not prompt or not prompt.Parent or tbl26.Active or now3 < tbl26.PausedUntil then
                  return
                end

                if now3 - n37 < 0.1 then
                  return
                end

                if prompt == v97 and now3 - n38 < 1.5 then
                  return
                end
                local v99 = fn61(prompt)
                if not v99.Ready then
                  return
                end
                v99.Ready = false
                tbl26.Active = true
                tbl26.Phase = "holding"
                local v100 = n39
                tbl24.active = true
                tbl24.startTime = tick()
                tbl24.phase = "holding"
                tbl24.progress = 0
                tbl24.label = arg.Prompt and arg.Prompt.Parent and arg.Prompt.Parent.Parent and arg.Prompt.Parent.Parent.Name or "Animal"

                task.spawn(function()
                  if not fn63(prompt, v99) then
                    fn67(v99, "Hold failed")
                    return
                  end
                  local now4 = os.clock()
                  local semiRadius = tbl26.SemiRadius
                  local flag24 = fn59(arg) <= semiRadius

                  while true do
                    local flag25 = fn68(v100, prompt)

                    if flag25 then
                      local semiHoldMin = tbl26.SemiHoldMin
                      flag25 = os.clock() - now4 < semiHoldMin
                    end

                    if flag25 then
                      local semiHoldMax = tbl26.SemiHoldMax
                      fn66((os.clock() - now4) / semiHoldMax, "holding")
                      RunService.Heartbeat:Wait()
                      continue
                    end

                    break
                  end

                  tbl26.Phase = "waitingRange"
                  tbl24.phase = "waitingRange"
                  local v101 = false

                  while true do
                    local flag25 = fn68(v100, prompt)

                    if flag25 then
                      local semiHoldMax = tbl26.SemiHoldMax
                      flag25 = os.clock() - now4 <= semiHoldMax
                    end

                    if flag25 then
                      local semiHoldMax = tbl26.SemiHoldMax
                      fn66((os.clock() - now4) / semiHoldMax, "waitingRange")
                      local semiRadius2 = tbl26.SemiRadius

                      if fn59(arg) <= semiRadius2 then
                        if not flag24 then
                          task.wait(tbl26.SemiEntryDelay)
                        end

                        if fn68(v100, prompt) then
                          v101 = fn64(prompt, v99)
                        end

                        break
                      else
                        RunService.Heartbeat:Wait()
                        continue
                      end
                    end

                    break
                  end

                  if not v101 then
                    fn65()
                  end

                  if v101 then
                    fn66(1, "done")
                  end

                  task.wait(0.05)

                  if v101 then
                    local v102 = prompt
                    local now5 = os.clock()
                    v97 = v102
                    n38 = now5
                    n37 = os.clock()
                  end

                  fn67(v99, v101 and "Stole" or "Missed window")
                end)
              end

              local function fn71(arg)
                local prompt = arg and arg.Prompt
                if not prompt or not prompt.Parent or tbl26.Active then
                  return
                end
                local now3 = os.clock()
                if now3 < tbl26.PausedUntil or now3 - n37 < 0.1 then
                  return
                end
                local v99 = fn61(prompt)
                if not v99.Ready then
                  return
                end
                v99.Ready = false
                tbl26.Active = true
                tbl26.Phase = "holding"
                n37 = now3
                local v100 = n39
                tbl24.active = true
                tbl24.startTime = tick()
                tbl24.phase = "holding"
                tbl24.progress = 0
                tbl24.label = arg.Prompt and arg.Prompt.Parent and arg.Prompt.Parent.Parent and arg.Prompt.Parent.Parent.Name or "Animal"

                task.spawn(function()
                  if not fn63(prompt, v99) then
                    fn67(v99, "Hold failed")
                    return
                  end
                  local n40 = math.max(tbl26.NormalDuration, 0.01)
                  local n41 = math.clamp(tbl26.NormalV2StopAt / 100, 0.75, 0.9)
                  local n42 = n40 * n41
                  local n43 = n40 * (1 - n41)
                  local now4 = os.clock()

                  while fn68(v100, prompt) and os.clock() - now4 < n42 do
                    fn66(math.clamp((os.clock() - now4) / n40, 0, n41), "holding")
                    RunService.Heartbeat:Wait()
                  end

                  fn66(n41, "waitingRange")
                  local now5 = os.clock()

                  while true do
                    local flag24 = fn68(v100, prompt)

                    if flag24 then
                      local triggerRange = tbl26.TriggerRange
                      flag24 = fn59(arg) > triggerRange
                    end

                    if flag24 then
                      local normalV2Wait = tbl26.NormalV2Wait
                      flag24 = os.clock() - now5 < normalV2Wait
                    end

                    if flag24 then
                      RunService.Heartbeat:Wait()
                      continue
                    end
                    break
                  end

                  if not fn68(v100, prompt) then
                    fn65()
                    fn67(v99, "Cancelled")
                    return
                  end

                  local now6 = os.clock()

                  while fn68(v100, prompt) and os.clock() - now6 < n43 do
                    fn66(math.clamp(n41 + (os.clock() - now6) / n40, n41, 1), "finishing")
                    RunService.Heartbeat:Wait()
                  end

                  local v101 = fn68(v100, prompt) and fn64(prompt, v99)

                  if not v101 then
                    fn65()
                  end

                  if v101 then
                    fn66(1, "done")
                    task.wait(math.max(n40 * 0.08, 0.08))
                  end

                  fn67(v99, v101 and "Stole" or "Failed")
                end)
              end

              local function fn72()
                if hookStealGen ~= _G.HookStealGen then
                  fn55("Scan")
                  return
                end
                local active = not tbl26.Enabled or tbl26.Active

                if not active then
                  local pausedUntil = tbl26.PausedUntil
                  active = os.clock() < pausedUntil
                end

                if active then
                  return
                end

                if tbl26.Mode == "semi" then
                  local v99 = fn60(tbl26.SemiPrimeRange)

                  if v99 then
                    fn70(v99)
                  end
                elseif tbl26.Mode == "normalv2" then
                  local v99 = fn60(tbl26.NormalRadius)

                  if v99 then
                    fn71(v99)
                  end
                else
                  local v99 = fn60(tbl26.NormalRadius)

                  if v99 then
                    fn69(v99)
                  end
                end
              end

              local vampireStealModes

              vampireStealModes = {
                State = tbl26,
                Start = function()
                  if flag23 then
                    return
                  end
                  tbl26.Enabled = true

                  if not tbl28.Scan then
                    local v99 = 0

                    tbl28.Scan = RunService.Heartbeat:Connect(function(deltaTime)
                      v99 += deltaTime or 0
                      if v99 < n35 then
                        return
                      end
                      v99 = 0
                      fn72()
                    end)
                  end
                end,
                Stop = function()
                  tbl26.Enabled = false
                  n39 += 1
                  fn55("Scan")
                  fn65()
                  tbl26.Active = false
                  tbl26.Phase = "idle"
                  tbl26.Progress = 0

                  for _, v99 in pairs(obj) do
                    v99.Ready = true
                  end
                end,
                SetMode = function(arg)
                  local mode = tostring(arg):lower():gsub("%s+", "")

                  if mode == "normalv2" or mode == "normal2" or mode == "v2" then
                    mode = "normalv2"
                  end

                  if mode ~= "normal" and mode ~= "semi" and mode ~= "normalv2" then
                    return false
                  end
                  local enabled = tbl26.Enabled
                  vampireStealModes.Stop()
                  tbl26.Mode = mode

                  if enabled then
                    vampireStealModes.Start()
                  end

                  return true
                end,
                SetNormalRadius = function(arg)
                  local num = tonumber(arg)

                  if num then
                    tbl26.NormalRadius = math.clamp(math.floor(num + 0.5), 5, 300)
                  end
                end,
                SetNormalDuration = function(arg)
                  local num = tonumber(arg)

                  if num then
                    tbl26.NormalDuration = math.clamp(num, 0.01, 5)
                  end
                end,
                SetSemiRadius = function(arg)
                  local num = tonumber(arg)

                  if num then
                    tbl26.SemiRadius = math.clamp(num, 1, 300)
                  end
                end,
                SetNormalV2StopAt = function(arg)
                  local normalV2StopAt = tonumber(arg)

                  if normalV2StopAt == 75 or normalV2StopAt == 80 or normalV2StopAt == 85 or normalV2StopAt == 90 then
                    tbl26.NormalV2StopAt = normalV2StopAt
                  end
                end,
                Pause = function(arg)
                  tbl26.PausedUntil = os.clock() + math.max(tonumber(arg) or 0, 0)
                end,
                Destroy = function()
                  if flag23 then
                    return
                  end
                  vampireStealModes.Stop()
                  flag23 = true

                  if _G.VampireStealModes == vampireStealModes then
                    _G.VampireStealModes = nil
                  end
                end,
              }

              _G.VampireStealModes = vampireStealModes

              local function cancelAndRecoverAutoGrab()
                vampireStealModes.Stop()

                for _, v99 in pairs(obj) do
                  local v100 = "table"

                  if type(v99) == v100 then
                    v99.Ready = true
                  end
                end

                tbl29 = {}
                n36 = 0

                if tbl26.autoGrabEnabled then
                  task.defer(vampireStealModes.Start)
                end
              end

              tbl26.cancelAndRecoverAutoGrab = cancelAndRecoverAutoGrab

              tbl26._cancelAutoGrabInFlight = function()
                cancelAndRecoverAutoGrab("ManualCancel")
              end

              v95.cancelAndRecoverAutoGrab = cancelAndRecoverAutoGrab
              v95._cancelAutoGrabInFlight = tbl26._cancelAutoGrabInFlight

              fn39 = function(autoGrabEnabled)
                tbl26.autoGrabEnabled = autoGrabEnabled
                v95.autoGrabEnabled = autoGrabEnabled
                tbl26.SemiPrimeRange = tonumber(v95.primeRange) or tbl26.SemiPrimeRange
                tbl26.NormalRadius = tonumber(v95.primeRange) or tbl26.NormalRadius

                if v86 and v86.setState then
                  pcall(function()
                    v86.setState(autoGrabEnabled)
                  end)
                end

                local setState = nil

                if v88 then
                  setState = v88.setState
                end

                if setState then
                  pcall(function()
                    v88.setState(autoGrabEnabled)
                  end)
                end

                if autoGrabEnabled then
                  vampireStealModes.SetMode(tbl27[v95.autoGrabMode] or "semi")
                  vampireStealModes.Start()
                else
                  vampireStealModes.Stop()
                end

                saveConfig()
              end

              LocalPlayer.CharacterAdded:Connect(function()
                cancelAndRecoverAutoGrab("Respawn")

                if tbl26.autoGrabEnabled then
                  task.delay(0.3, vampireStealModes.Start)
                end
              end)
            end

            fn54()
          end

          do
            local now3 = 0

            fn40 = function(arg, arg2, arg3)
              if tpDownRunning then
                return
              end
              tpDownRunning = true

              pcall(function()
                local character = LocalPlayer.Character
                local humanoidRootPart = character and character:FindFirstChild("HumanoidRootPart")
                local humanoid = character and character:FindFirstChildOfClass("Humanoid")
                if not humanoidRootPart or not humanoid then
                  return
                end
                local position = humanoidRootPart.Position

                if
                  position.X ~= position.X
                  or position.Y ~= position.Y
                  or position.Z ~= position.Z
                  or math.abs(position.X) > 1000000
                  or math.abs(position.Y) > 1000000
                  or math.abs(position.Z) > 1000000
                then
                  if tick() - now3 > 5 then
                    now3 = tick()

                    pcall(function()
                      LocalPlayer:LoadCharacter()
                    end)
                  end

                  return
                end

                pcall(function()
                  WorkspaceService.FallenPartsDestroyHeight = -50000
                  humanoid.BreakJointsOnDeath = false
                  humanoid.RequiresNeck = false
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
                end)

                pcall(function()
                  if stopNamed then
                    stopNamed(humanoidRootPart, "InfJump")
                  end
                end)

                pcall(function()
                  local torso = character:FindFirstChild("Torso") or character:FindFirstChild("UpperTorso")

                  if torso then
                    torso.CanCollide = true
                  end

                  local lowerTorso = character:FindFirstChild("LowerTorso")

                  if lowerTorso then
                    lowerTorso.CanCollide = true
                  end
                end)

                local x = arg2 or humanoidRootPart.Position.X
                local z = arg3 or humanoidRootPart.Position.Z
                local raycastParams = RaycastParams.new()
                raycastParams.FilterType = Enum.RaycastFilterType.Exclude
                raycastParams.IgnoreWater = true
                local filterDescendantsInstances = { character }

                for _, player in ipairs(Players:GetPlayers()) do
                  if player ~= LocalPlayer and player.Character then
                    table.insert(filterDescendantsInstances, player.Character)
                  end
                end

                raycastParams.FilterDescendantsInstances = filterDescendantsInstances
                local vector = Vector3.new(x, humanoidRootPart.Position.Y, z)
                local y = nil

                for i = 1, 15 do
                  local hit = WorkspaceService:Raycast(vector, Vector3.new(0, -3000, 0), raycastParams)
                  y = nil

                  if hit then
                    local instance = hit.Instance
                    local parent = instance
                    local v95 = nil

                    for i2 = 1, 6 do
                      local flag22 = not parent or parent == WorkspaceService
                      v95 = nil

                      if not flag22 then
                        if parent:IsA("Model") and parent:FindFirstChildOfClass("Humanoid") then
                          v95 = parent
                          break
                        else
                          parent = parent.Parent
                          v95 = nil
                          continue
                        end
                      end

                      break
                    end

                    if instance.Transparency >= 0.9 or instance.CanCollide == false or v95 then
                      table.insert(filterDescendantsInstances, v95 or instance)
                      raycastParams.FilterDescendantsInstances = filterDescendantsInstances
                      vector = hit.Position - Vector3.new(0, 0.2, 0)
                      y = nil
                      continue
                    else
                      y = hit.Position.Y
                      break
                    end
                  end

                  break
                end

                if not y then
                  return
                end
                local n35 = y + 2.8
                local x2 = humanoidRootPart.AssemblyLinearVelocity.X
                local z2 = humanoidRootPart.AssemblyLinearVelocity.Z

                if x2 ~= x2 then
                  x2 = 0
                end

                if z2 ~= z2 then
                  z2 = 0
                end

                local ok, result = pcall(fn48)
                local n36 = math.max(ok and result or 60, 40)
                local v95 = math.sqrt(x2 * x2 + z2 * z2)

                if v95 > n36 and v95 > 0 then
                  x2 = x2 / v95 * n36
                  z2 = z2 / v95 * n36
                end

                humanoidRootPart.CFrame = CFrame.new(x, n35, z)
                humanoidRootPart.AssemblyLinearVelocity = Vector3.new(x2, 0, z2)
                humanoidRootPart.AssemblyAngularVelocity = Vector3.zero

                pcall(function()
                  humanoidRootPart.Velocity = Vector3.new(x2, 0, z2)
                  humanoidRootPart.RotVelocity = Vector3.zero
                end)

                pcall(function()
                  humanoid.PlatformStand = false
                  humanoid:ChangeState(Enum.HumanoidStateType.GettingUp)

                  if not Config.antiDieEnabled then
                    humanoid.BreakJointsOnDeath = true
                    humanoid.RequiresNeck = true
                    humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, true)
                  end
                end)
              end)

              tpDownRunning = false
            end
          end
        end

        do
          local connection2, fn54

          do
            connection2 = nil

            do
              local n35 = 0

              fn54 = function()
                if connection2 then
                  return
                end

                connection2 = RunService.Heartbeat:Connect(function()
                  if not Config.autoTpDown or flag21 or flag20 then
                    return
                  end
                  local character = LocalPlayer.Character
                  local humanoid = character and character:FindFirstChildOfClass("Humanoid")
                  local humanoidRootPart = character and character:FindFirstChild("HumanoidRootPart")
                  if not character or not humanoid or not humanoidRootPart or humanoid.Health <= 0 then
                    return
                  end
                  local now3 = tick()
                  if now3 - n35 < 0.08 then
                    return
                  end
                  local flag22 = not (
                    humanoidRootPart.AssemblyLinearVelocity.Y < -2 or humanoidRootPart.Velocity and humanoidRootPart.Velocity.Y < -2
                  )

                  if flag22 then
                    local freefall = Enum.HumanoidStateType.Freefall
                    flag22 = humanoid:GetState() ~= freefall
                  end

                  if flag22 then
                    return
                  end
                  local raycastParams = RaycastParams.new()
                  raycastParams.FilterType = Enum.RaycastFilterType.Exclude
                  raycastParams.IgnoreWater = true
                  raycastParams.FilterDescendantsInstances = { character }
                  local hit = WorkspaceService:Raycast(humanoidRootPart.Position, Vector3.new(0, -3000, 0), raycastParams)

                  if hit then
                    local n36 = humanoidRootPart.Position.Y - hit.Position.Y - 3
                    local autoTpDownHeight = Config.autoTpDownHeight or 15
                    local flag23 = humanoid.FloorMaterial == Enum.Material.Air
                    local flag24

                    if flag23 then
                      flag24 = flag23
                    else
                      local freefall = Enum.HumanoidStateType.Freefall
                      flag24 = humanoid:GetState() == freefall
                    end

                    if flag24 and n36 >= autoTpDownHeight then
                      n35 = now3
                      fn40(false)
                    end
                  end
                end)
              end
            end
          end

          do
            local function fn55()
              if connection2 then
                connection2:Disconnect()
                connection2 = nil
              end
            end

            fn47 = function(autoTpDown)
              Config.autoTpDown = autoTpDown

              if autoTpDown then
                fn54()
              else
                fn55()
              end

              saveConfig()
            end
          end
        end

        Config._circleTrack = {
          conn = nil,
          target = nil,
          lastPos = nil,
          velocity = Vector3.zero,
        }

        do
          local function fn54()
            local character = LocalPlayer.Character
            if not character then
              return nil
            end
            local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
            if not humanoidRootPart then
              return nil
            end
            local position = humanoidRootPart.Position
            local huge = math.huge
            local v95 = nil

            for _, player in ipairs(Players:GetPlayers()) do
              if player ~= LocalPlayer and player.Character then
                local humanoidRootPart2 = player.Character:FindFirstChild("HumanoidRootPart")
                local humanoid = player.Character:FindFirstChildOfClass("Humanoid")

                if humanoidRootPart2 and humanoid and humanoid.Health > 0 then
                  local magnitude = (position - humanoidRootPart2.Position).Magnitude

                  if magnitude < huge then
                    huge = magnitude
                    v95 = player
                  end
                end
              end
            end

            return v95, huge
          end

          connection = nil
          local v95 = 0

          local function fn55(arg)
            if not arg then
              return
            end
            local now3 = tick()
            if now3 - v95 < 0.12 then
              return
            end

            for _, child in ipairs(arg:GetChildren()) do
              if child:IsA("Tool") and child.Name:lower():find("bat", 1, true) then
                pcall(function()
                  child:Activate()
                end)

                v95 = now3
              end
            end
          end

          fn53 = function()
            if connection then
              return
            end
            local n35 = 0

            connection = RunService.Heartbeat:Connect(function(deltaTime)
              n35 += deltaTime
              if n35 < 0.05 then
                return
              end
              n35 = 0
              if not Config.autoHitEnabled then
                return
              end
              local character = LocalPlayer.Character
              local humanoidRootPart = character and character:FindFirstChild("HumanoidRootPart")
              if not humanoidRootPart then
                return
              end
              local v96 = fn54()
              local humanoidRootPart2 = v96 and v96.Character and v96.Character:FindFirstChild("HumanoidRootPart")

              if humanoidRootPart2 and (humanoidRootPart2.Position - humanoidRootPart.Position).Magnitude <= 10 then
                fn55(character)
              end
            end)
          end
        end
      end

      do
        do
          do
            local function fn54()
              if connection then
                connection:Disconnect()
                connection = nil
              end
            end

            Config._setAutoHit = function(autoHitEnabled)
              Config.autoHitEnabled = autoHitEnabled

              if autoHitEnabled then
                fn53()
              else
                fn54()
              end

              saveConfig()
            end
          end
        end

        do
          local fn54, fn55

          do
            do
              local function fn56(arg)
                if not arg or not arg:IsA("Tool") then
                  return false
                end
                local str8 = arg.Name:lower()
                return str8:find("bat", 1, true) ~= nil
                  or str8:find("slap", 1, true) ~= nil
                  or str8:find("club", 1, true) ~= nil
                  or str8:find("hammer", 1, true) ~= nil
              end

              fn54 = function(arg)
                if not arg or not arg:IsA("Tool") then
                  return
                end

                pcall(function()
                  arg.Enabled = true

                  for _, descendant in ipairs(arg:GetDescendants()) do
                    if descendant:IsA("BasePart") then
                      descendant.CanCollide = false
                    end
                  end
                end)

                pcall(function()
                  arg.Equipped:Connect(function()
                    pcall(function()
                      for _, descendant in ipairs(arg:GetDescendants()) do
                        if descendant:IsA("BasePart") then
                          descendant.CanCollide = false
                        end
                      end
                    end)
                  end)
                end)
              end

              fn55 = function()
                local character = LocalPlayer.Character
                if not character then
                  return nil
                end
                local humanoid = character:FindFirstChildOfClass("Humanoid")
                if not humanoid or humanoid.Health <= 0 then
                  return nil
                end

                for _, child in ipairs(character:GetChildren()) do
                  if fn56(child) then
                    return child
                  end
                end

                local backpack = LocalPlayer:FindFirstChildOfClass("Backpack") or LocalPlayer:FindFirstChild("Backpack")

                if backpack then
                  for _, child in ipairs(backpack:GetChildren()) do
                    if fn56(child) then
                      pcall(function()
                        humanoid:EquipTool(child)
                      end)

                      return child
                    end
                  end
                end

                return nil
              end
            end
          end

          do
            local function fn56(arg)
              local backpack = LocalPlayer:FindFirstChildOfClass("Backpack") or LocalPlayer:FindFirstChild("Backpack")

              if backpack then
                for _, child in ipairs(backpack:GetChildren()) do
                  if child:IsA("Tool") then
                    fn54(child)
                  end
                end

                backpack.ChildAdded:Connect(function(child)
                  if child:IsA("Tool") then
                    task.wait(0.05)
                    fn54(child)
                  end
                end)
              end

              if arg then
                for _, child in ipairs(arg:GetChildren()) do
                  if child:IsA("Tool") then
                    fn54(child)
                  end
                end

                arg.ChildAdded:Connect(function(child)
                  if child:IsA("Tool") then
                    task.wait(0.05)
                    fn54(child)
                  end
                end)
              end
            end

            LocalPlayer.CharacterAdded:Connect(function(character)
              task.wait(0.05)

              pcall(function()
                fn56(character)
              end)

              if Config.autoEquipBat then
                task.delay(0.2, function()
                  pcall(fn55)
                end)
              end
            end)

            if LocalPlayer.Character then
              task.spawn(fn56, LocalPlayer.Character)
            end
          end
        end
      end
    end

    local fn53

    do
      do
        local function fn54()
          local character = LocalPlayer.Character
          if not character then
            return nil
          end
          local humanoid = character:FindFirstChildOfClass("Humanoid")
          local tool = character:FindFirstChildOfClass("Tool")
          if tool then
            return tool
          end

          for _, child in ipairs(character:GetChildren()) do
            if child:IsA("Tool") then
              return child
            end
          end

          local backpack = LocalPlayer:FindFirstChild("Backpack")

          if backpack then
            for _, child in ipairs(backpack:GetChildren()) do
              if child:IsA("Tool") then
                local str8 = child.Name:lower()

                if
                  str8:find("bat")
                  or str8:find("slap")
                  or str8:find("sword")
                  or str8:find("blade")
                  or str8:find("hit")
                  or str8:find("club")
                then
                  if humanoid then
                    pcall(function()
                      humanoid:EquipTool(child)
                    end)
                  end

                  return child
                end
              end
            end

            local tool2 = backpack:FindFirstChildOfClass("Tool")

            if tool2 then
              if humanoid then
                pcall(function()
                  humanoid:EquipTool(tool2)
                end)
              end

              return tool2
            end
          end

          return nil
        end

        local function fn55()
          local humanoidRootPart = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
          if not humanoidRootPart then
            return nil
          end
          local huge = math.huge
          local v95 = nil

          for _, player in ipairs(Players:GetPlayers()) do
            if player ~= LocalPlayer and player.Character then
              local humanoidRootPart2 = player.Character:FindFirstChild("HumanoidRootPart")
              local humanoid = player.Character:FindFirstChildOfClass("Humanoid")

              if humanoidRootPart2 and humanoid and humanoid.Health > 0 then
                local magnitude = (humanoidRootPart2.Position - humanoidRootPart.Position).Magnitude

                if magnitude < huge then
                  huge = magnitude
                  v95 = humanoidRootPart2
                end
              end
            end
          end

          return v95
        end

        fn53 = function()
          Config._circleTrack = Config._circleTrack or { conn = nil, target = nil, lastPos = nil, velocity = Vector3.zero }
          local circleTrack = Config._circleTrack

          if circleTrack.conn then
            circleTrack.conn:Disconnect()
            circleTrack.conn = nil
          end

          circleTrack.target = nil
          circleTrack.lastPos = nil
          circleTrack.velocity = Vector3.zero
          local character = LocalPlayer.Character
          if not character then
            return
          end
          local humanoid = character:FindFirstChildOfClass("Humanoid")
          local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
          if not humanoid or not humanoidRootPart then
            return
          end
          humanoid.AutoRotate = false
          pcall(function()
            humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
          end)
          local v95 = 0

          circleTrack.conn = RunService.RenderStepped:Connect(function()
            if not Config.circleEnabled then
              if circleTrack.conn then
                circleTrack.conn:Disconnect()
                circleTrack.conn = nil
              end

              return
            end

            local character2 = LocalPlayer.Character
            if not character2 then
              return
            end
            local humanoidRootPart2 = character2:FindFirstChild("HumanoidRootPart")
            if not humanoidRootPart2 then
              return
            end
            local humanoid2 = character2:FindFirstChildOfClass("Humanoid")
            if not humanoid2 or humanoid2.Health <= 0 then
              return
            end

            if not character2:FindFirstChildOfClass("Tool") then
              local v96 = fn54()

              if v96 then
                pcall(function()
                  humanoid2:EquipTool(v96)
                end)
              end
            end

            local v96 = fn55()

            if not v96 then
              pcall(function()
                humanoidRootPart2.AssemblyLinearVelocity = Vector3.new(0, humanoidRootPart2.AssemblyLinearVelocity.Y, 0)
                humanoidRootPart2.AssemblyAngularVelocity = Vector3.zero
              end)

              return
            end

            local assemblyLinearVelocity = v96.AssemblyLinearVelocity
            local position = humanoidRootPart2.Position
            local position2 = v96.Position
            local laggerCarrySpeed = Config.laggerCarryEnabled and (Config.laggerCarrySpeed or 40) or 58
            local n35 = position2 + assemblyLinearVelocity * 0.12 - position
            local vector = Vector3.new(n35.X, 0, n35.Z)
            local unit = vector.Magnitude > 0.1 and vector.Unit
              or Vector3.new(humanoidRootPart2.CFrame.LookVector.X, 0, humanoidRootPart2.CFrame.LookVector.Z)
            local vector2

            if unit.Magnitude < 0.01 then
              vector2 = Vector3.new(0, 0, -1)
            else
              vector2 = unit.Unit
            end

            local verticalVelocity = humanoidRootPart2.AssemblyLinearVelocity.Y

            if humanoid2.FloorMaterial ~= Enum.Material.Air and position2.Y - position.Y > 3 then
              verticalVelocity = 50
            end

            local chaseSpeed = laggerCarrySpeed * math.clamp(vector.Magnitude / 3, 0, 1)

            humanoidRootPart2.AssemblyLinearVelocity =
              Vector3.new(vector2.X * chaseSpeed, math.clamp(verticalVelocity, -80, 100), vector2.Z * chaseSpeed)

            pcall(function()
              local enabled = nil

              if v84 then
                enabled = v84.Enabled
              end

              if enabled then
                v84.PlaneVelocity = Vector2.zero
                v84.Enabled = false
              end
            end)

            if vector.Magnitude > 0.5 then
              humanoidRootPart2.CFrame = CFrame.lookAt(position, position + vector2)
            end

            humanoidRootPart2.AssemblyAngularVelocity = Vector3.zero

            if (position2 - position).Magnitude <= 12 then
              local now3 = tick()

              if now3 - v95 >= 0.12 then
                v95 = now3
                local tool = character2:FindFirstChildOfClass("Tool")

                if tool then
                  local remoteEvent = tool:FindFirstChildOfClass("RemoteEvent") or tool:FindFirstChildOfClass("RemoteFunction")

                  if remoteEvent and remoteEvent:IsA("RemoteEvent") then
                    pcall(function()
                      remoteEvent:FireServer()
                    end)
                  else
                    pcall(function()
                      tool:Activate()
                    end)
                  end
                end
              end
            end
          end)
        end
      end
    end

    do
      local function fn54()
        Config._circleTrack = Config._circleTrack or { conn = nil, target = nil, lastPos = nil, velocity = Vector3.zero }
        local circleTrack = Config._circleTrack

        if circleTrack.conn then
          circleTrack.conn:Disconnect()
          circleTrack.conn = nil
        end

        local character = LocalPlayer.Character

        if character then
          local humanoid = character:FindFirstChildOfClass("Humanoid")

          if humanoid then
            humanoid.AutoRotate = true

            pcall(function()
              if not Config.antiRagdollEnabled then
                humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, true)
              end

              humanoid:Move(Vector3.zero, false)
            end)
          end

          local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")

          if humanoidRootPart then
            humanoidRootPart.AssemblyAngularVelocity = Vector3.zero
            humanoidRootPart.AssemblyLinearVelocity = Vector3.zero
          end
        end

        if v84 then
          v84.PlaneVelocity = Vector2.zero
          v84.Enabled = false
        end

        circleTrack.target = nil
        circleTrack.lastPos = nil
        circleTrack.velocity = Vector3.zero
      end

      fn32 = function(circleEnabled)
        if flag20 and circleEnabled then
          if v87 and v87.setState then
            v87.setState(false)
          end

          return
        end

        if circleEnabled and tbl23.active then
          fn49()
        end

        Config.circleEnabled = circleEnabled
        local setState = nil

        if v89 then
          setState = v89.setState
        end

        if setState then
          pcall(function()
            v89.setState(circleEnabled)
          end)
        end

        if v87 and v87.setState then
          pcall(function()
            v87.setState(circleEnabled)
          end)
        end

        if circleEnabled then
          fn53()
        else
          fn54()
        end

        saveConfig()
      end
    end
  end

  local fn48, fn49, fn50, fn51, fn52, fn53, tbl24, fn54, fn55, fn56

  do
    do
      do
        do
          local tbl25, connection, fn57

          do
            local fn58

            do
              tbl25 = {}

              do
                local function fn59(arg, cameraSubject, arg2)
                  pcall(function()
                    cameraSubject:ChangeState(Enum.HumanoidStateType.GettingUp)
                    cameraSubject:ChangeState(Enum.HumanoidStateType.Running)

                    for _, descendant in ipairs(arg:GetDescendants()) do
                      if descendant:IsA("Motor6D") then
                        descendant.Enabled = true
                      end

                      if descendant:IsA("Constraint") then
                        descendant.Enabled = true
                      end
                    end

                    arg2.Velocity = Vector3.zero
                    arg2.RotVelocity = Vector3.zero
                    arg2.AssemblyLinearVelocity = Vector3.zero
                    arg2.AssemblyAngularVelocity = Vector3.zero

                    if workspace.CurrentCamera then
                      workspace.CurrentCamera.CameraSubject = cameraSubject
                    end

                    local playerModule = LocalPlayer.PlayerScripts:FindFirstChild("PlayerModule")

                    if playerModule then
                      local ControlModule = require(playerModule:FindFirstChild("ControlModule"))

                      if ControlModule then
                        ControlModule:Enable()
                      end
                    end

                    cameraSubject.AutoRotate = true
                    cameraSubject.PlatformStand = false
                    cameraSubject.Sit = false
                  end)

                  if Config.cancelAndRecoverAutoGrab then
                    pcall(function()
                      Config.cancelAndRecoverAutoGrab("AntiRagdoll")
                    end)
                  end
                end

                fn58 = function(arg)
                  for _, v88 in ipairs(tbl25) do
                    pcall(function()
                      v88:Disconnect()
                    end)
                  end

                  tbl25 = {}
                  if not arg then
                    return
                  end
                  local humanoid = arg:WaitForChild("Humanoid", 5)
                  local humanoidRootPart = arg:WaitForChild("HumanoidRootPart", 5)
                  if not humanoid or not humanoidRootPart then
                    return
                  end

                  local connection2 = RunService.Heartbeat:Connect(function()
                    if not Config.antiRagdollEnabled then
                      return
                    end

                    if humanoid.Health <= 0 then
                      return
                    end

                    local state = humanoid:GetState()

                    if
                      state == Enum.HumanoidStateType.Physics
                      or state == Enum.HumanoidStateType.Ragdoll
                      or state == Enum.HumanoidStateType.FallingDown
                      or humanoid.PlatformStand == true
                    then
                      fn59(arg, humanoid, humanoidRootPart)
                    end
                  end)

                  table.insert(tbl25, connection2)

                  local connection3 = humanoid.StateChanged:Connect(function(old, new)
                    if not Config.antiRagdollEnabled then
                      return
                    end

                    if humanoid.Health <= 0 then
                      return
                    end

                    if
                      new == Enum.HumanoidStateType.Physics
                      or new == Enum.HumanoidStateType.Ragdoll
                      or new == Enum.HumanoidStateType.FallingDown
                    then
                      fn59(arg, humanoid, humanoidRootPart)
                    end
                  end)

                  table.insert(tbl25, connection3)

                  local connection4 = humanoid:GetPropertyChangedSignal("PlatformStand"):Connect(function()
                    if not Config.antiRagdollEnabled then
                      return
                    end

                    if humanoid.PlatformStand then
                      fn59(arg, humanoid, humanoidRootPart)
                    end
                  end)

                  table.insert(tbl25, connection4)

                  local connection5 = humanoid:GetPropertyChangedSignal("Sit"):Connect(function()
                    if not Config.antiRagdollEnabled then
                      return
                    end

                    if humanoid.Sit then
                      humanoid.Sit = false
                      fn59(arg, humanoid, humanoidRootPart)
                    end
                  end)

                  table.insert(tbl25, connection5)
                  local health = humanoid.Health

                  local connection6 = humanoid:GetPropertyChangedSignal("Health"):Connect(function()
                    if not flag21 and humanoid.Health < health then
                      if Config.cancelAndRecoverAutoGrab then
                        pcall(function()
                          Config.cancelAndRecoverAutoGrab("HitDamage")
                        end)
                      end
                    end

                    health = humanoid.Health
                  end)

                  table.insert(tbl25, connection6)
                end
              end
            end

            connection = nil

            fn57 = function()
              if LocalPlayer.Character then
                fn58(LocalPlayer.Character)
              end

              if not connection then
                connection = LocalPlayer.CharacterAdded:Connect(function(character)
                  if Config.antiRagdollEnabled then
                    task.wait(0.1)
                    fn58(character)
                  end
                end)
              end
            end
          end

          do
            local function fn58()
              for _, v88 in ipairs(tbl25) do
                pcall(function()
                  v88:Disconnect()
                end)
              end

              tbl25 = {}

              if connection then
                connection:Disconnect()
                connection = nil
              end
            end

            fn48 = function(antiRagdollEnabled)
              Config.antiRagdollEnabled = antiRagdollEnabled

              if antiRagdollEnabled then
                fn57()
              else
                fn58()
              end

              saveConfig()
            end
          end
        end

        do
          local n32

          do
            n32 = 0

            do
              local function fn57()
                local tbl25 = {}
                local n33 = 0
                local flag22 = false

                local function fn58()
                  local character = LocalPlayer.Character

                  local function fn59(arg)
                    if not arg then
                      return nil
                    end

                    for _, child in ipairs(arg:GetChildren()) do
                      if child:IsA("Tool") then
                        local str8 = child.Name:lower()
                        if str8:find("medusa") or str8:find("head") or str8:find("stone") then
                          return child
                        end
                      end
                    end
                  end

                  return character and fn59(character) or fn59(LocalPlayer:FindFirstChild("Backpack"))
                end

                local function fn59()
                  if flag22 then
                    return
                  end

                  if tick() - n33 < 1.5 then
                    return
                  end
                  local character = LocalPlayer.Character
                  if not character then
                    return
                  end
                  flag22 = true
                  local v88 = fn58()

                  if v88 then
                    if v88.Parent ~= character then
                      local humanoid = character:FindFirstChildOfClass("Humanoid")

                      if humanoid then
                        humanoid:EquipTool(v88)
                      end
                    end

                    if v88.Parent == character then
                      pcall(function()
                        v88:Activate()
                      end)
                    end

                    n33 = tick()
                  end

                  flag22 = false
                end

                local function fn60(arg)
                  return arg:GetPropertyChangedSignal("Anchored"):Connect(function()
                    if arg.Anchored and arg.Transparency == 1 then
                      n32 = tick()
                      fn59()
                    end
                  end)
                end

                local function fn61(arg)
                  for _, v88 in ipairs(tbl25) do
                    pcall(function()
                      v88:Disconnect()
                    end)
                  end

                  tbl25 = {}
                  if not arg then
                    return
                  end

                  for _, descendant in ipairs(arg:GetDescendants()) do
                    if descendant:IsA("BasePart") then
                      table.insert(tbl25, fn60(descendant))
                    end
                  end

                  table.insert(
                    tbl25,
                    arg.DescendantAdded:Connect(function(descendant)
                      if descendant:IsA("BasePart") then
                        table.insert(tbl25, fn60(descendant))
                      end
                    end)
                  )
                end

                local function fn62()
                  for _, v88 in ipairs(tbl25) do
                    pcall(function()
                      v88:Disconnect()
                    end)
                  end

                  tbl25 = {}
                end

                fn36 = function(medusaCounterEnabled)
                  Config.medusaCounterEnabled = medusaCounterEnabled

                  if medusaCounterEnabled then
                    if LocalPlayer.Character then
                      fn61(LocalPlayer.Character)
                    end
                  else
                    fn62()
                  end

                  saveConfig()
                end

                LocalPlayer.CharacterAdded:Connect(function(character)
                  if Config.medusaCounterEnabled then
                    fn61(character)
                  end
                end)
              end

              fn57()
            end
          end

          local tbl25 = {
            "HumanoidRootPart",
            "UpperTorso",
            "LowerTorso",
            "Torso",
            "Head",
          }

          local function fn57(arg)
            arg:WaitForChild("HumanoidRootPart", 12)
            task.wait(0.2)

            for _, v88 in ipairs(tbl25) do
              local v89 = arg:FindFirstChild(v88)

              if v89 and v89:IsA("BasePart") then
                v89:GetPropertyChangedSignal("Anchored"):Connect(function()
                  if v89.Anchored and v89.Transparency >= 1 then
                    n32 = tick()
                  end
                end)
              end
            end
          end

          if LocalPlayer.Character then
            task.spawn(fn57, LocalPlayer.Character)
          end

          LocalPlayer.CharacterAdded:Connect(function(character)
            task.spawn(fn57, character)
          end)
        end

        do
          local function fn57()
            local flag22 = false
            local connection = nil

            local function fn58()
              local playerGui2 = LocalPlayer:FindFirstChild("PlayerGui") or LocalPlayer:WaitForChild("PlayerGui", 10)
              if not playerGui2 then
                return
              end

              local function fn59(descendant)
                if descendant:IsA("GuiButton") and descendant.Name == "JumpButton" and not descendant:GetAttribute("XluIJHooked") then
                  descendant:SetAttribute("XluIJHooked", true)

                  descendant.MouseButton1Down:Connect(function()
                    if Config.infJumpEnabled then
                      flag22 = true
                    end
                  end)

                  descendant.MouseButton1Up:Connect(function()
                    flag22 = false
                  end)

                  descendant.MouseLeave:Connect(function()
                    flag22 = false
                  end)
                end
              end

              for _, descendant in ipairs(playerGui2:GetDescendants()) do
                fn59(descendant)
              end

              playerGui2.DescendantAdded:Connect(fn59)
            end

            local function fn59()
              if connection then
                connection:Disconnect()
                connection = nil
              end

              connection = RunService.Heartbeat:Connect(function()
                if not Config.infJumpEnabled then
                  return
                end
                local character = LocalPlayer.Character
                if not character then
                  return
                end
                local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
                local humanoid = character:FindFirstChildOfClass("Humanoid")
                if not humanoidRootPart or not humanoid then
                  return
                end
                local flag23 = UserInputService:IsKeyDown(Enum.KeyCode.Space) or flag22 or humanoid.Jump == true
                local assemblyLinearVelocity = humanoidRootPart.AssemblyLinearVelocity

                if flag23 and assemblyLinearVelocity.Y < 35 then
                  humanoidRootPart.AssemblyLinearVelocity = Vector3.new(assemblyLinearVelocity.X, 55, assemblyLinearVelocity.Z)

                  pcall(function()
                    humanoidRootPart.Velocity = Vector3.new(assemblyLinearVelocity.X, 55, assemblyLinearVelocity.Z)
                  end)
                end

                assemblyLinearVelocity = humanoidRootPart.AssemblyLinearVelocity

                if assemblyLinearVelocity.Y < -100 then
                  humanoidRootPart.AssemblyLinearVelocity = Vector3.new(assemblyLinearVelocity.X, -100, assemblyLinearVelocity.Z)

                  pcall(function()
                    humanoidRootPart.Velocity = Vector3.new(assemblyLinearVelocity.X, -100, assemblyLinearVelocity.Z)
                  end)
                end
              end)
            end

            local function fn60()
              flag22 = false

              if connection then
                connection:Disconnect()
                connection = nil
              end
            end

            fn35 = function(infJumpEnabled)
              Config.infJumpEnabled = infJumpEnabled

              if infJumpEnabled then
                pcall(function()
                  if workspace.FallenPartsDestroyHeight > -50000 then
                    workspace.FallenPartsDestroyHeight = -50000
                  end

                  local character = LocalPlayer.Character
                  character = character and character:FindFirstChildOfClass("Humanoid")

                  if character then
                    character.BreakJointsOnDeath = false
                    character.RequiresNeck = false
                    character:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
                    character:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
                    character:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
                  end
                end)

                fn59()
              else
                fn60()
              end

              saveConfig()
            end

            RunService.Heartbeat:Connect(function()
              if not Config.infJumpEnabled then
                return
              end
              local character = LocalPlayer.Character
              if not character then
                return
              end
              local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
              local humanoid = character:FindFirstChildOfClass("Humanoid")
              if not humanoidRootPart or not humanoid then
                return
              end

              if humanoid.FloorMaterial ~= Enum.Material.Air then
                local assemblyLinearVelocity = humanoidRootPart.AssemblyLinearVelocity

                if assemblyLinearVelocity.Y < 0 then
                  humanoidRootPart.AssemblyLinearVelocity = Vector3.new(assemblyLinearVelocity.X, 0, assemblyLinearVelocity.Z)

                  pcall(function()
                    humanoidRootPart.Velocity = Vector3.new(assemblyLinearVelocity.X, 0, assemblyLinearVelocity.Z)
                  end)
                end

                pcall(function()
                  humanoid.PlatformStand = false
                  humanoid.BreakJointsOnDeath = false
                  humanoid.RequiresNeck = false
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
                  humanoid.MaxHealth = math.huge
                  humanoid.Health = math.huge
                end)
              end
            end)

            UserInputService.InputBegan:Connect(function(input, gameProcessed)
              if gameProcessed then
                return
              end

              if input.KeyCode == Enum.KeyCode.Space then
                if Config.infJumpEnabled then
                  flag22 = true
                end
              end
            end)

            UserInputService.InputEnded:Connect(function(input)
              if input.KeyCode == Enum.KeyCode.Space then
                flag22 = false
              end
            end)

            task.spawn(fn58)

            LocalPlayer.CharacterAdded:Connect(function()
              task.wait(0.2)
              fn58()

              if Config.infJumpEnabled then
                fn59()
              end
            end)
          end

          fn57()
        end
      end

      do
        local tbl25, currentAnimPack, v88, connection, clone, fn57

        do
          tbl25 = {
            Zombie = {
              idle1 = "rbxassetid://616158929",
              idle2 = "rbxassetid://616158929",
              walk = "rbxassetid://616168032",
              run = "rbxassetid://616163682",
              jump = "rbxassetid://616161997",
              fall = "rbxassetid://616157476",
              climb = "rbxassetid://616156119",
            },
            Ninja = {
              idle1 = "rbxassetid://656117400",
              idle2 = "rbxassetid://656117400",
              walk = "rbxassetid://656121766",
              run = "rbxassetid://656118852",
              jump = "rbxassetid://656117878",
              fall = "rbxassetid://656115606",
              climb = "rbxassetid://656114359",
            },
            Knight = {
              idle1 = "rbxassetid://657595757",
              idle2 = "rbxassetid://657595757",
              walk = "rbxassetid://657552124",
              run = "rbxassetid://657564596",
              jump = "rbxassetid://658409194",
              fall = "rbxassetid://657600338",
              climb = "rbxassetid://658360781",
            },
            Elder = {
              idle1 = "rbxassetid://845397899",
              idle2 = "rbxassetid://845397899",
              walk = "rbxassetid://845403856",
              run = "rbxassetid://845386501",
              jump = "rbxassetid://845398858",
              fall = "rbxassetid://845397673",
              climb = "rbxassetid://845392038",
            },
            Levitate = {
              idle1 = "rbxassetid://616006778",
              idle2 = "rbxassetid://616006778",
              walk = "rbxassetid://616013216",
              run = "rbxassetid://616013216",
              jump = "rbxassetid://616008936",
              fall = "rbxassetid://616005863",
              climb = "rbxassetid://616003713",
            },
            Astronaut = {
              idle1 = "rbxassetid://891621366",
              idle2 = "rbxassetid://891621366",
              walk = "rbxassetid://891636393",
              run = "rbxassetid://891636393",
              jump = "rbxassetid://891627522",
              fall = "rbxassetid://891617961",
              climb = "rbxassetid://891609353",
            },
            Pirate = {
              idle1 = "rbxassetid://750781874",
              idle2 = "rbxassetid://750781874",
              walk = "rbxassetid://750785693",
              run = "rbxassetid://750783738",
              jump = "rbxassetid://750782230",
              fall = "rbxassetid://750780242",
              climb = "rbxassetid://750779899",
            },
            Toy = {
              idle1 = "rbxassetid://782841498",
              idle2 = "rbxassetid://782841498",
              walk = "rbxassetid://782843345",
              run = "rbxassetid://782842708",
              jump = "rbxassetid://782847020",
              fall = "rbxassetid://782846423",
              climb = "rbxassetid://782843869",
            },
            Vampire = {
              idle1 = "rbxassetid://1083445855",
              idle2 = "rbxassetid://1083445855",
              walk = "rbxassetid://1083473930",
              run = "rbxassetid://1083462077",
              jump = "rbxassetid://1083455352",
              fall = "rbxassetid://1083443587",
              climb = "rbxassetid://1083439238",
            },
            Werewolf = {
              idle1 = "rbxassetid://1083195517",
              idle2 = "rbxassetid://1083195517",
              walk = "rbxassetid://1083178339",
              run = "rbxassetid://1083216690",
              jump = "rbxassetid://1083218792",
              fall = "rbxassetid://1083189019",
              climb = "rbxassetid://1083182000",
            },
            Rthro = {
              idle1 = "rbxassetid://2510196951",
              idle2 = "rbxassetid://2510196951",
              walk = "rbxassetid://2510202577",
              run = "rbxassetid://2510198475",
              jump = "rbxassetid://2510197830",
              fall = "rbxassetid://2510195892",
              climb = "rbxassetid://2510192778",
            },
            Stylish = {
              idle1 = "rbxassetid://616136790",
              idle2 = "rbxassetid://616136790",
              walk = "rbxassetid://616146177",
              run = "rbxassetid://616140816",
              jump = "rbxassetid://616139451",
              fall = "rbxassetid://616134815",
              climb = "rbxassetid://616133594",
            },
            ["Hit Harder"] = {
              idle1 = "rbxassetid://133806214992291",
              idle2 = "rbxassetid://94970088341563",
              walk = "rbxassetid://707897309",
              run = "rbxassetid://707861613",
              jump = "rbxassetid://116936326516985",
              fall = "rbxassetid://116936326516985",
              climb = "rbxassetid://116936326516985",
            },
            Crazy = {
              idle1 = "rbxassetid://133806214992291",
              idle2 = "rbxassetid://94970088341563",
              walk = "rbxassetid://134824450619865",
              run = "rbxassetid://134824450619865",
              jump = "rbxassetid://121454505477205",
              fall = "rbxassetid://94788218468396",
              climb = "rbxassetid://121454505477205",
            },
          }

          currentAnimPack = "OFF"
          v88 = nil
          connection = nil
          clone = nil

          do
            local function fn58(arg)
              for _, v89 in pairs(tbl25) do
                for _, v90 in pairs(v89) do
                  if v90 == arg then
                    return true
                  end
                end
              end

              return false
            end

            fn57 = function(arg)
              arg = arg and arg:FindFirstChild("Animate")
              if not arg or v88 ~= nil then
                return
              end

              local function fn59(arg2)
                return arg2 and arg2.AnimationId or nil
              end

              local tbl26 = {
                idle1 = fn59(arg.idle and arg.idle:FindFirstChild("Animation1")),
                idle2 = fn59(arg.idle and arg.idle:FindFirstChild("Animation2")),
                walk = fn59(arg.walk and arg.walk:FindFirstChild("WalkAnim")),
                run = fn59(arg.run and arg.run:FindFirstChild("RunAnim")),
                jump = fn59(arg.jump and arg.jump:FindFirstChild("JumpAnim")),
                fall = fn59(arg.fall and arg.fall:FindFirstChild("FallAnim")),
                climb = fn59(arg.climb and arg.climb:FindFirstChild("ClimbAnim")),
              }

              if not fn58(tbl26.walk) then
                v88 = tbl26
              end
            end
          end
        end

        do
          local function fn58(arg)
            arg = arg and arg:FindFirstChildOfClass("Humanoid")
            if not arg then
              return
            end

            for _, v89 in ipairs(arg:GetPlayingAnimationTracks()) do
              pcall(function()
                v89:Stop(0)
              end)
            end
          end

          local function fn59(arg, animationId)
            if arg and animationId then
              pcall(function()
                arg.AnimationId = animationId
              end)
            end
          end

          local function fn60(parent)
            if parent and not parent:FindFirstChild("Animate") and clone then
              clone:Clone().Parent = parent
              clone = nil
            end
          end

          local function fn61(arg)
            currentAnimPack = arg or "OFF"
            Config.currentAnimPack = currentAnimPack

            if connection then
              connection:Disconnect()
              connection = nil
            end

            local character = LocalPlayer.Character
            if not character then
              return
            end

            if currentAnimPack == "Unwalk" then
              local animate = character:FindFirstChild("Animate")

              if animate then
                if not clone then
                  clone = animate:Clone()
                end

                fn58(character)
                animate:Destroy()
              end

              return
            end

            fn60(character)

            if currentAnimPack == "OFF" or currentAnimPack == "Off" then
              currentAnimPack = "OFF"
              Config.currentAnimPack = "OFF"
              local animate = character:FindFirstChild("Animate")

              if animate and v88 then
                fn58(character)
                fn59(animate.idle and animate.idle:FindFirstChild("Animation1"), v88.idle1)
                fn59(animate.idle and animate.idle:FindFirstChild("Animation2"), v88.idle2)
                fn59(animate.walk and animate.walk:FindFirstChild("WalkAnim"), v88.walk)
                fn59(animate.run and animate.run:FindFirstChild("RunAnim"), v88.run)
                fn59(animate.jump and animate.jump:FindFirstChild("JumpAnim"), v88.jump)
                fn59(animate.fall and animate.fall:FindFirstChild("FallAnim"), v88.fall)
                fn59(animate.climb and animate.climb:FindFirstChild("ClimbAnim"), v88.climb)
              end

              return
            end

            local v89 = tbl25[currentAnimPack]
            if not v89 then
              return
            end
            fn57(character)
            local animate = character:FindFirstChild("Animate")

            if animate then
              fn59(animate.idle and animate.idle:FindFirstChild("Animation1"), v89.idle1)
              fn59(animate.idle and animate.idle:FindFirstChild("Animation2"), v89.idle2)
              fn59(animate.walk and animate.walk:FindFirstChild("WalkAnim"), v89.walk)
              fn59(animate.run and animate.run:FindFirstChild("RunAnim"), v89.run)
              fn59(animate.jump and animate.jump:FindFirstChild("JumpAnim"), v89.jump)
              fn59(animate.fall and animate.fall:FindFirstChild("FallAnim"), v89.fall)
              fn59(animate.climb and animate.climb:FindFirstChild("ClimbAnim"), v89.climb)
            end

            fn58(character)
            local humanoid = character:FindFirstChildOfClass("Humanoid")

            if humanoid then
              pcall(function()
                humanoid:ChangeState(Enum.HumanoidStateType.Landed)
              end)
            end

            connection = RunService.Heartbeat:Connect(function()
              local character2 = LocalPlayer.Character
              local animate2 = character2 and character2:FindFirstChild("Animate")
              if not animate2 then
                return
              end
              fn59(animate2.idle and animate2.idle:FindFirstChild("Animation1"), v89.idle1)
              fn59(animate2.idle and animate2.idle:FindFirstChild("Animation2"), v89.idle2)
              fn59(animate2.walk and animate2.walk:FindFirstChild("WalkAnim"), v89.walk)
              fn59(animate2.run and animate2.run:FindFirstChild("RunAnim"), v89.run)
              fn59(animate2.jump and animate2.jump:FindFirstChild("JumpAnim"), v89.jump)
              fn59(animate2.fall and animate2.fall:FindFirstChild("FallAnim"), v89.fall)
              fn59(animate2.climb and animate2.climb:FindFirstChild("ClimbAnim"), v89.climb)
            end)
          end

          fn49 = function(arg)
            fn61(arg)
            saveConfig(true)
          end

          LocalPlayer.CharacterAdded:Connect(function()
            v88 = nil
            clone = nil

            if currentAnimPack ~= "OFF" and currentAnimPack ~= "Off" then
              task.wait(0.3)
              fn61(currentAnimPack)
            end
          end)
        end
      end

      do
        local flag22 = false

        setUnwalkEnabled = function(unwalkEnabled)
          Config.unwalkEnabled = unwalkEnabled

          if unwalkEnabled then
            if flag22 then
              return
            end
            flag22 = true
            local character = LocalPlayer.Character
            if not character then
              return
            end
            local humanoid = character:FindFirstChildOfClass("Humanoid")

            if humanoid then
              for _, v88 in ipairs(humanoid:GetPlayingAnimationTracks()) do
                v88:Stop()
              end
            end

            local animate = character:FindFirstChild("Animate")

            if animate then
              AnimRefs.savedAnimate = animate:Clone()
              animate:Destroy()
            end
          else
            if not flag22 then
              return
            end
            flag22 = false
            local character = LocalPlayer.Character

            if character and AnimRefs.savedAnimate then
              AnimRefs.savedAnimate.Parent = character
              AnimRefs.savedAnimate.Disabled = false
              AnimRefs.savedAnimate = nil
            end
          end

          saveConfig()
        end
      end

      do
        local tbl25 = {}

        local function fn57()
          for _, player in ipairs(Players:GetPlayers()) do
            if player ~= LocalPlayer and player.Character then
              for _, child in ipairs(player.Character:GetChildren()) do
                if child:IsA("BasePart") then
                  child.CanCollide = false
                end
              end
            end
          end
        end

        local flag22 = false
        local v88 = nil

        local function fn58()
          if flag22 then
            return
          end

          if flag20 then
            return
          end
          local character = LocalPlayer.Character
          if not character then
            return
          end
          local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
          if not humanoidRootPart then
            return
          end
          local humanoid = character:FindFirstChildOfClass("Humanoid")
          if not humanoid or humanoid.Health <= 0 then
            return
          end

          for _, v89 in ipairs(tbl25) do
            if typeof(v89) == "RBXScriptConnection" then
              v89:Disconnect()
            elseif type(v89) == "thread" then
              pcall(coroutine.close, v89)
            end
          end

          tbl25 = {}
          flag22 = true
          flag21 = true

          pcall(function()
            if humanoidRootPart.SetNetworkOwner then
              humanoidRootPart:SetNetworkOwner(LocalPlayer)
            end
          end)

          if Config.cancelAndRecoverAutoGrab then
            pcall(function()
              Config.cancelAndRecoverAutoGrab("Drop")
            end)
          end

          local connection = RunService.Stepped:Connect(function()
            if flag21 then
              fn57()
            end
          end)

          table.insert(tbl25, connection)
          local enabled = nil

          if v84 then
            enabled = v84.Enabled
          end

          if enabled then
            v84.PlaneVelocity = Vector2.zero
          end

          humanoidRootPart.AssemblyAngularVelocity = Vector3.zero
          humanoidRootPart.AssemblyLinearVelocity = Vector3.new(0, 150, 0)

          task.delay(0.2, function()
            for _, v89 in ipairs(tbl25) do
              if typeof(v89) == "RBXScriptConnection" then
                v89:Disconnect()
              elseif type(v89) == "thread" then
                pcall(coroutine.close, v89)
              end
            end

            tbl25 = {}

            pcall(function()
              fn40()
            end)

            task.delay(0.05, function()
              if Config.cancelAndRecoverAutoGrab then
                pcall(function()
                  Config.cancelAndRecoverAutoGrab("DropLanded")
                end)
              end

              if Config.autoGrabEnabled and _G.VampireStealModes and _G.VampireStealModes.Start then
                pcall(_G.VampireStealModes.Start)
              end
            end)

            if Config.autoBatOnDropBrainrot then
              task.spawn(function()
                task.wait(0.1)

                if fn32 then
                  fn32(true)
                end
              end)
            end

            if Config.tpBatOnDropBrainrot then
              task.spawn(function()
                task.wait(0.05)

                if fn33 then
                  fn33(true)
                end
              end)
            end

            flag22 = false

            task.delay(0.3, function()
              flag21 = false
            end)
          end)
        end

        fn50 = function()
          fn58()
        end

        LocalPlayer.CharacterRemoving:Connect(function()
          flag21 = false
          flag22 = false

          if v88 then
            pcall(function()
              v88:Disconnect()
            end)

            v88 = nil
          end

          _dropBrainrotActive = false

          if _dropBrainrotConn then
            pcall(function()
              _dropBrainrotConn:Disconnect()
            end)

            _dropBrainrotConn = nil
          end

          if tbl22 then
            local v89 = tbl22
            local v90 = tbl22
            tbl22.humanoid = nil
            v89.hrp = nil
            v90.speedLabel = nil
          end

          local v89 = ipairs
          local tbl26 = tbl25 or {}

          for _, v90 in v89(tbl26) do
            if typeof(v90) == "RBXScriptConnection" then
              v90:Disconnect()
            elseif type(v90) == "thread" then
              pcall(coroutine.close, v90)
            end
          end

          tbl25 = {}
        end)
      end
    end

    do
      do
        local tbl25 = {}

        local function fn57()
          if flag20 then
            return
          end
          flag20 = true

          if Config.circleEnabled then
            Config.circleEnabled = false
            task.defer(stopCircle)
          end
        end

        local function fn58()
          flag20 = false
        end

        local function fn59(arg)
          if not arg or not arg:IsA("Sound") or tbl25[arg] then
            return
          end

          tbl25[arg] = {
            playingConn = arg:GetPropertyChangedSignal("Playing"):Connect(function()
              if arg.Playing then
                fn57()
              else
                fn58()
              end
            end),
            endedConn = arg.Ended:Connect(fn58),
            ancestryConn = arg.AncestryChanged:Connect(function()
              if not arg:IsDescendantOf(game) then
                tbl25[arg] = nil
                fn58()
              end
            end),
          }

          if arg.Playing then
            fn57()
          end
        end

        WorkspaceService.DescendantAdded:Connect(function(descendant)
          if descendant:IsA("Sound") and descendant.Name:lower():find("countdown") then
            fn59(descendant)
          end
        end)

        task.defer(function()
          findDescendant(WorkspaceService, function(arg)
            if arg:IsA("Sound") and arg.Name:lower():find("countdown") then
              fn59(arg)
            end

            return false
          end, 180)
        end)
      end

      do
        local connection, v88, fn57, fn58

        do
          connection = nil

          do
            local flag22 = false
            v88 = nil

            fn57 = function(arg)
              if not arg then
                return nil, nil
              end
              local n32 = 1e9
              local v89 = nil
              local v90 = nil

              for _, player in ipairs(Players:GetPlayers()) do
                if player ~= LocalPlayer then
                  local character = player.Character

                  if character then
                    local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
                    local humanoid = character:FindFirstChildOfClass("Humanoid")

                    if humanoidRootPart and humanoid and humanoid.Health > 0 and humanoidRootPart.Position.Y >= -25 then
                      local magnitude = (humanoidRootPart.Position - arg.Position).Magnitude

                      if magnitude < n32 then
                        n32 = magnitude
                        v89 = player
                        v90 = humanoidRootPart
                      end
                    end
                  end
                end
              end

              return v89, v90
            end

            local function fn59()
              local character = LocalPlayer.Character
              if not character then
                return nil
              end

              for _, child in ipairs(character:GetChildren()) do
                if child:IsA("Tool") then
                  local str8 = child.Name:lower()
                  if
                    str8:find("bat")
                    or str8:find("slap")
                    or str8:find("sword")
                    or str8:find("knife")
                    or str8:find("blade")
                    or str8:find("mace")
                  then
                    return child
                  end

                  if child:FindFirstChildWhichIsA("RemoteEvent") or child:FindFirstChild("Activate") then
                    return child
                  end
                end
              end

              local backpack = LocalPlayer:FindFirstChild("Backpack")

              if backpack then
                for _, child in ipairs(backpack:GetChildren()) do
                  if child:IsA("Tool") then
                    local str8 = child.Name:lower()

                    if
                      str8:find("bat")
                      or str8:find("slap")
                      or str8:find("sword")
                      or str8:find("knife")
                      or str8:find("blade")
                      or str8:find("mace")
                    then
                      local humanoid = character:FindFirstChildOfClass("Humanoid")

                      if humanoid then
                        pcall(function()
                          humanoid:EquipTool(child)
                        end)
                      end

                      child.Parent = character
                      return child
                    end
                  end
                end

                local anyTool = backpack:FindFirstChildOfClass("Tool")

                if anyTool then
                  local humanoid = character:FindFirstChildOfClass("Humanoid")

                  if humanoid then
                    pcall(function()
                      humanoid:EquipTool(anyTool)
                    end)
                  end

                  return anyTool
                end
              end

              return nil
            end

            fn58 = function()
              if flag22 then
                return
              end
              flag22 = true

              pcall(function()
                local v89 = fn59()

                if v89 then
                  if v89.Parent ~= LocalPlayer.Character then
                    v89.Parent = LocalPlayer.Character
                    local humanoid = LocalPlayer.Character and LocalPlayer.Character:FindFirstChildOfClass("Humanoid")

                    if humanoid then
                      pcall(function()
                        humanoid:EquipTool(v89)
                      end)
                    end
                  end

                  pcall(function()
                    v89:Activate()
                  end)

                  local remoteEvent = v89:FindFirstChildWhichIsA("RemoteEvent") or v89:FindFirstChildOfClass("RemoteEvent")

                  if remoteEvent then
                    pcall(function()
                      remoteEvent:FireServer()
                    end)
                  end
                end
              end)

              task.delay(Config.tpBatSwingDelay or 0.1, function()
                flag22 = false
              end)
            end
          end
        end

        do
          local function fn59()
            if connection then
              return
            end
            v88 = nil

            pcall(function()
              local humanoid = LocalPlayer.Character and LocalPlayer.Character:FindFirstChildOfClass("Humanoid")

              if humanoid then
                humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
              end
            end)

            if Config._tpBatStepConn then
              Config._tpBatStepConn:Disconnect()
            end

            Config._tpBatStepConn = RunService.Stepped:Connect(function()
              for _, player in ipairs(Players:GetPlayers()) do
                if player ~= LocalPlayer and player.Character then
                  for _, part in ipairs(player.Character:GetChildren()) do
                    if part:IsA("BasePart") then
                      part.CanCollide = false
                    end
                  end
                end
              end
            end)

            connection = RunService.Heartbeat:Connect(function()
              if not Config.tpBatEnabled then
                return
              end

              if Config.safeModeEnabled then
                local character = LocalPlayer.Character
                local humanoid = character and character:FindFirstChildOfClass("Humanoid")

                if humanoid and humanoid.WalkSpeed < 25 then
                  fn33(false)

                  if win and win.Notify then
                    win:Notify("Safe Mode", "Blocked · Safe Mode · brainrot", 1.5)
                  end

                  return
                end
              end

              local character = LocalPlayer.Character
              if not character then
                return
              end
              local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
              local humanoid = character:FindFirstChildOfClass("Humanoid")
              if not humanoidRootPart or not humanoid or humanoid.Health <= 0 then
                return
              end
              local v89 = v88
              local v90 = v88

              if v89 then
                local humanoid2 = v89.Parent and v89.Parent:FindFirstChildOfClass("Humanoid")

                if not humanoid2 or humanoid2.Health <= 0 then
                  v88 = nil
                  v90 = nil
                else
                  v90 = v89
                end
              end

              if not v90 then
                local v91
                v91, v90 = fn57(humanoidRootPart)
                v88 = v90
              end

              if not v90 then
                return
              end
              local v91 = v90

              pcall(function()
                if sethiddenproperty then
                  sethiddenproperty(humanoidRootPart, "PhysicsRepRootPart", v91)
                end
              end)

              local assemblyLinearVelocity = v91.AssemblyLinearVelocity or Vector3.zero
              local n32 = v91.Position + assemblyLinearVelocity * 0.05 + Vector3.new(0, 0.35, 0)
              local vector = Vector3.new(assemblyLinearVelocity.X, 0, assemblyLinearVelocity.Z)

              if vector.Magnitude < 0.2 then
                vector = Vector3.new(v91.Position.X - humanoidRootPart.Position.X, 0, v91.Position.Z - humanoidRootPart.Position.Z)
              end

              pcall(function()
                if 0.1 < vector.Magnitude then
                  humanoidRootPart.CFrame = CFrame.lookAt(n32, n32 + vector.Unit)
                else
                  humanoidRootPart.CFrame = CFrame.new(n32)
                end

                if (humanoidRootPart.Position - v91.Position).Magnitude > 3.5 then
                  local position = v91.Position
                  humanoidRootPart.CFrame = CFrame.lookAt(v91.Position + Vector3.new(0, 0.4, 0), position)
                end

                humanoidRootPart.AssemblyLinearVelocity = assemblyLinearVelocity
                humanoidRootPart.AssemblyAngularVelocity = Vector3.zero
              end)

              local currentCamera = workspace.CurrentCamera

              if currentCamera then
                pcall(function()
                  currentCamera.CFrame = CFrame.lookAt(currentCamera.CFrame.Position, v91.Position + Vector3.new(0, 1, 0))
                end)
              end

              fn58()
            end)
          end

          local function fn60()
            Config.tpBatEnabled = false

            if connection then
              connection:Disconnect()
              connection = nil
            end

            v88 = nil

            if Config._tpBatStepConn then
              Config._tpBatStepConn:Disconnect()
              Config._tpBatStepConn = nil
            end

            local character = LocalPlayer.Character
            local humanoidRootPart = character and character:FindFirstChild("HumanoidRootPart")

            pcall(function()
              local humanoid = character and character:FindFirstChildOfClass("Humanoid")

              if humanoid and not Config.antiRagdollEnabled then
                humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, true)
              end
            end)

            if humanoidRootPart then
              pcall(function()
                if sethiddenproperty then
                  sethiddenproperty(humanoidRootPart, "PhysicsRepRootPart", nil)
                end
              end)

              pcall(function()
                humanoidRootPart.AssemblyLinearVelocity = Vector3.zero
                humanoidRootPart.AssemblyAngularVelocity = Vector3.zero
              end)
            end
          end

          fn33 = function(tpBatEnabled)
            if tpBatEnabled and Config.safeModeEnabled then
              local character = LocalPlayer.Character
              character = character and character:FindFirstChildOfClass("Humanoid")

              if character and character.WalkSpeed < 25 then
                if win and win.Notify then
                  win:Notify("Safe Mode", "Cannot use TP Bat while carrying in Safe Mode!", 2)
                end

                if tpBatButton then
                  tpBatButton.setState(false)
                end

                return
              end
            end

            Config.tpBatEnabled = tpBatEnabled

            if tpBatButton then
              tpBatButton.setState(tpBatEnabled)
            end

            if tpBatEnabled then
              fn59()
            else
              fn60()
            end

            saveConfig()
          end
        end

        Config._bindTpBatStopEvent = function()
          pcall(function()
            local packages = ReplicatedStorage:WaitForChild("Packages", 3)
            local net = packages and packages:WaitForChild("Net", 3)
            net = net and net:WaitForChild("RE/9f6f251400de424a5105a9ea47b3acb7df3f36f460594bf2d2167c7e2272d468", 3)
            if not net or not net:IsA("RemoteEvent") then
              return
            end

            if Config._tpBatStopEventConn then
              Config._tpBatStopEventConn:Disconnect()
            end

            Config._tpBatStopEventConn = net.OnClientEvent:Connect(function()
              if Config.tpBatEnabled or connection then
                fn33(false)
              end
            end)
          end)
        end
      end
    end

    do
      task.spawn(Config._bindTpBatStopEvent)

      do
        local tbl25 = {}
        local connection = nil
        local tbl26 = {}

        local function fn57(arg)
          local v88 = tbl25[arg]

          if v88 then
            if v88.gui then
              pcall(function()
                v88.gui:Destroy()
              end)
            end

            tbl25[arg] = nil
          end
        end

        local function fn58(arg)
          if not Config.playerSpeedEnabled then
            return
          end

          if arg == LocalPlayer then
            return
          end
          local character = arg.Character
          if not character then
            return
          end
          local head = character:FindFirstChild("Head") or character:WaitForChild("Head", 5)
          if not head then
            return
          end
          fn57(arg)
          local billboardGui = Instance.new("BillboardGui")
          billboardGui.Name = "PlrSpeedBillboard"
          billboardGui.Size = UDim2.new(0, 120, 0, 42)
          billboardGui.StudsOffset = Vector3.new(0, 3.5, 0)
          billboardGui.AlwaysOnTop = true
          billboardGui.MaxDistance = 250
          billboardGui.Adornee = head
          billboardGui.Parent = head
          local textLabel = Instance.new("TextLabel")
          textLabel.Size = UDim2.new(1, 0, 0.45, 0)
          textLabel.BackgroundTransparency = 1
          textLabel.Text = arg.DisplayName
          textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
          textLabel.Font = Enum.Font.MontserratBold
          textLabel.TextScaled = true
          textLabel.TextStrokeTransparency = 0.2
          textLabel.Parent = billboardGui
          local textLabel2 = Instance.new("TextLabel")
          textLabel2.Size = UDim2.new(1, 0, 0.55, 0)
          textLabel2.Position = UDim2.new(0, 0, 0.45, 0)
          textLabel2.BackgroundTransparency = 1
          textLabel2.Text = "Speed: 0"
          textLabel2.TextColor3 = color
          textLabel2.Font = Enum.Font.MontserratBlack
          textLabel2.TextScaled = true
          textLabel2.TextStrokeTransparency = 0
          textLabel2.Parent = billboardGui
          tbl25[arg] = { gui = billboardGui, label = textLabel2, lastPos = nil, smooth = 0 }
        end

        fn51 = function(playerSpeedEnabled)
          Config.playerSpeedEnabled = playerSpeedEnabled

          if playerSpeedEnabled then
            for _, player in ipairs(Players:GetPlayers()) do
              if player ~= LocalPlayer then
                task.spawn(fn58, player)

                if not tbl26[player] then
                  tbl26[player] = player.CharacterAdded:Connect(function()
                    if Config.playerSpeedEnabled then
                      task.spawn(fn58, player)
                    end
                  end)
                end
              end
            end

            if not connection then
              connection = RunService.Heartbeat:Connect(function(deltaTime)
                local now2 = tick()

                for k, v88 in pairs(tbl25) do
                  local character = k.Character
                  character = character and character:FindFirstChild("HumanoidRootPart")

                  if character and v88.label and v88.label.Parent then
                    local position = character.Position
                    local assemblyLinearVelocity = character.AssemblyLinearVelocity
                    local n32 =
                      math.sqrt(assemblyLinearVelocity.X * assemblyLinearVelocity.X + assemblyLinearVelocity.Z * assemblyLinearVelocity.Z)

                    if v88.lastPos and v88.lastTime then
                      local n33 = now2 - v88.lastTime

                      if n33 > 0.01 then
                        local n34 = position.X - v88.lastPos.X
                        local n35 = position.Z - v88.lastPos.Z
                        n32 = math.max(n32, math.sqrt(n34 * n34 + n35 * n35) / n33)
                      end
                    end

                    v88.smooth = v88.smooth + (n32 - v88.smooth) * math.clamp(deltaTime * 14, 0, 1)

                    if v88.smooth < 0.2 then
                      v88.smooth = 0
                    end

                    v88.label.Text = string.format("Speed: %.1f", v88.smooth)
                    v88.label.TextColor3 = color
                    v88.lastPos = position
                    v88.lastTime = now2
                  end
                end
              end)
            end
          else
            if connection then
              connection:Disconnect()
              connection = nil
            end

            for _, v88 in pairs(tbl26) do
              pcall(function()
                v88:Disconnect()
              end)
            end

            tbl26 = {}

            for k in pairs(tbl25) do
              fn57(k)
            end

            tbl25 = {}
          end

          saveConfig()
        end

        Players.PlayerAdded:Connect(function(player)
          if player == LocalPlayer then
            return
          end

          if Config.playerSpeedEnabled then
            tbl26[player] = player.CharacterAdded:Connect(function()
              if Config.playerSpeedEnabled then
                task.spawn(fn58, player)
              end
            end)
          end
        end)

        Players.PlayerRemoving:Connect(function(player)
          if tbl26[player] then
            tbl26[player]:Disconnect()
            tbl26[player] = nil
          end

          fn57(player)
        end)
      end
    end

    do
      do
        local tbl25 = {
          timerActive = false,
          detConns = {},
          charConn = nil,
          timerOn = false,
          animGen = 0,
        }

        local function fn57(arg)
          if not arg then
            return false
          end
          local humanoid = arg:FindFirstChildOfClass("Humanoid")
          if not humanoid or humanoid.Health <= 0 then
            return false
          end

          if humanoid.PlatformStand or humanoid.Sit then
            return true
          end
          local state = humanoid:GetState()
          if
            state == Enum.HumanoidStateType.Physics
            or state == Enum.HumanoidStateType.Ragdoll
            or state == Enum.HumanoidStateType.FallingDown
            or state == Enum.HumanoidStateType.PlatformStanding
          then
            return true
          end

          for _, v88 in ipairs({ "Ragdoll", "Ragdolled", "IsRagdoll", "RagdollTime", "Knocked", "Stunned", "Down" }) do
            if arg:FindFirstChild(v88) then
              return true
            end
          end

          return false
        end

        local function fn58()
          if tbl22.ragLabel and tbl22.ragLabel.Parent then
            return tbl22.ragLabel
          end
          local character = LocalPlayer.Character
          local head = character and (character:FindFirstChild("Head") or character:FindFirstChild("HumanoidRootPart"))
          if not head then
            return nil
          end
          local speedBillboard = head:FindFirstChild("SpeedBillboard")

          if not speedBillboard and character and fn45 then
            pcall(function()
              fn45(character)
            end)

            speedBillboard = head:FindFirstChild("SpeedBillboard")
          end

          if speedBillboard then
            local ragdollLabel = speedBillboard:FindFirstChild("RagdollLabel")

            if not ragdollLabel then
              ragdollLabel = Instance.new("TextLabel")
              ragdollLabel.Name = "RagdollLabel"
              ragdollLabel.Size = UDim2.new(1, 0, 0.35, 0)
              ragdollLabel.Position = UDim2.new(0, 0, 0, 0)
              ragdollLabel.BackgroundTransparency = 1
              ragdollLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
              ragdollLabel.Font = Enum.Font.MontserratBlack
              ragdollLabel.TextScaled = true
              ragdollLabel.TextStrokeTransparency = 0
              ragdollLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
              ragdollLabel.Text = "2.5s"
              ragdollLabel.Visible = false
              ragdollLabel.Parent = speedBillboard
            end

            tbl22.ragLabel = ragdollLabel
            return ragdollLabel
          end

          return nil
        end

        local function fn59()
          if tbl25.timerActive or not Config.ragTimerEnabled then
            return
          end
          local v88 = fn58()
          if not v88 then
            return
          end
          tbl25.timerActive = true
          tbl25.animGen = tbl25.animGen + 1
          local animGen = tbl25.animGen
          local now2 = tick()
          v88.Text = "2.5s"
          v88.TextColor3 = Color3.fromRGB(255, 255, 255)
          v88.Visible = true

          task.spawn(function()
            while true do
              if tbl25.timerActive and tbl25.animGen == animGen then
                local n32 = 2.5 - tick() - now2

                if not (n32 <= 0) then
                  local v89 = fn58()

                  if v89 then
                    v89.Text = string.format("%.1fs", n32)

                    if n32 <= 0.8 then
                      v89.TextColor3 = Color3.fromRGB(255, 80, 80)
                    elseif n32 <= 1.5 then
                      v89.TextColor3 = Color3.fromRGB(255, 200, 80)
                    else
                      v89.TextColor3 = Color3.fromRGB(255, 255, 255)
                    end

                    v89.Visible = true
                  end

                  task.wait(0.03)
                  continue
                end
              end

              break
            end

            if tbl25.animGen == animGen then
              local v89 = fn58()

              if v89 then
                v89.Visible = false
              end

              tbl25.timerActive = false
            end
          end)
        end

        local function fn60(arg)
          for _, detConn in ipairs(tbl25.detConns) do
            pcall(function()
              detConn:Disconnect()
            end)
          end

          tbl25.detConns = {}
          if not arg then
            return
          end
          local humanoid = arg:WaitForChild("Humanoid", 4)

          if humanoid then
            local function fn61()
              if not Config.ragTimerEnabled or tbl25.timerActive then
                return
              end

              if fn57(arg) then
                fn59()
              end
            end

            table.insert(
              tbl25.detConns,
              humanoid.StateChanged:Connect(function(old, new)
                if not Config.ragTimerEnabled or tbl25.timerActive then
                  return
                end

                if
                  new == Enum.HumanoidStateType.Physics
                  or new == Enum.HumanoidStateType.Ragdoll
                  or new == Enum.HumanoidStateType.FallingDown
                  or new == Enum.HumanoidStateType.PlatformStanding
                then
                  fn59()
                end
              end)
            )

            table.insert(
              tbl25.detConns,
              humanoid:GetPropertyChangedSignal("PlatformStand"):Connect(function()
                if humanoid.PlatformStand then
                  fn61()
                end
              end)
            )

            table.insert(
              tbl25.detConns,
              humanoid:GetPropertyChangedSignal("Sit"):Connect(function()
                if humanoid.Sit then
                  fn61()
                end
              end)
            )
          end

          table.insert(
            tbl25.detConns,
            arg.ChildAdded:Connect(function(child)
              if not Config.ragTimerEnabled or tbl25.timerActive then
                return
              end
              local str8 = child.Name:lower()

              if str8:find("ragdoll") or str8:find("knock") or str8:find("stun") then
                fn59()
              end
            end)
          )

          table.insert(
            tbl25.detConns,
            RunService.Heartbeat:Connect(function()
              if not arg.Parent or not Config.ragTimerEnabled then
                return
              end

              if not tbl25.timerActive and fn57(arg) then
                fn59()
              end
            end)
          )
        end

        fn52 = function()
          if not tbl25.timerOn then
            tbl25.timerOn = true

            if LocalPlayer.Character then
              fn60(LocalPlayer.Character)
            end

            tbl25.charConn = LocalPlayer.CharacterAdded:Connect(function(character)
              if Config.ragTimerEnabled then
                task.wait(0.15)
                fn60(character)
              end
            end)

            return
          end
        end

        fn53 = function()
          tbl25.timerOn = false

          if tbl25.charConn then
            tbl25.charConn:Disconnect()
            tbl25.charConn = nil
          end

          for _, detConn in ipairs(tbl25.detConns) do
            pcall(function()
              detConn:Disconnect()
            end)
          end

          tbl25.detConns = {}
          tbl25.timerActive = false
          tbl25.animGen = tbl25.animGen + 1
          local v88 = fn58()

          if v88 then
            v88.Visible = false
          end
        end
      end
    end

    do
      local fn57

      do
        tbl24 = {
          conn = nil,
          debounce = false,
          running = false,
          _batCounterWatchConn = nil,
          _batCounterActivatedTP = false,
          _batCounterTarget = nil,
        }

        do
          local tbl25 = {
            "Bat",
            "Slap",
            "Iron Slap",
            "Gold Slap",
            "Diamond Slap",
            "Emerald Slap",
            "Ruby Slap",
            "Dark Matter Slap",
            "Flame Slap",
            "Nuclear Slap",
            "Galaxy Slap",
            "Glitched Slap",
          }

          fn57 = function()
            local character = LocalPlayer.Character
            if not character then
              return nil
            end
            local backpack = LocalPlayer:FindFirstChildOfClass("Backpack")

            for _, v88 in ipairs(tbl25) do
              local v89 = character:FindFirstChild(v88) or backpack and backpack:FindFirstChild(v88)
              if v89 and v89:IsA("Tool") then
                return v89
              end
            end

            for _, child in ipairs(character:GetChildren()) do
              local isTool = child:IsA("Tool")
              local pos

              if isTool then
                pos = child.Name:lower():find("bat")
                  or child.Name:lower():find("slap")
                  or child.Name:lower():find("sword")
                  or child.Name:lower():find("blade")
              else
                pos = isTool
              end

              if pos then
                return child
              end
            end

            if backpack then
              for _, child in ipairs(backpack:GetChildren()) do
                if
                  child:IsA("Tool")
                  and (
                    child.Name:lower():find("bat")
                    or child.Name:lower():find("slap")
                    or child.Name:lower():find("sword")
                    or child.Name:lower():find("blade")
                  )
                then
                  return child
                end
              end
            end

            for _, child in ipairs(character:GetChildren()) do
              if child:IsA("Tool") then
                return child
              end
            end

            if backpack then
              for _, child in ipairs(backpack:GetChildren()) do
                if child:IsA("Tool") then
                  return child
                end
              end
            end

            return nil
          end
        end
      end

      do
        local function fn58(arg, parent)
          local humanoid = parent:FindFirstChildOfClass("Humanoid")

          if arg.Parent ~= parent then
            arg.Parent = parent

            if humanoid then
              pcall(function()
                humanoid:EquipTool(arg)
              end)
            end

            task.wait(0.04)
          end

          local remoteEvent = arg:FindFirstChildOfClass("RemoteEvent") or arg:FindFirstChildOfClass("RemoteFunction")

          if remoteEvent and remoteEvent:IsA("RemoteEvent") then
            pcall(function()
              remoteEvent:FireServer()
            end)

            task.wait(0.12)

            pcall(function()
              remoteEvent:FireServer()
            end)
          else
            pcall(function()
              arg:Activate()
            end)

            task.wait(0.12)

            pcall(function()
              arg:Activate()
            end)
          end
        end

        fn54 = function(arg)
          if not arg or arg.Health <= 0 then
            return false
          end

          if arg.PlatformStand or arg.Sit then
            return true
          end
          local state = arg:GetState()
          if
            state == Enum.HumanoidStateType.Physics
            or state == Enum.HumanoidStateType.Ragdoll
            or state == Enum.HumanoidStateType.FallingDown
            or state == Enum.HumanoidStateType.PlatformStanding
          then
            return true
          end
          local parent = arg.Parent

          if parent then
            for _, v88 in ipairs({ "Ragdoll", "Ragdolled", "IsRagdoll", "RagdollTime", "Knocked", "Stunned", "Down" }) do
              if parent:FindFirstChild(v88) then
                return true
              end
            end
          end

          return false
        end

        local function fn59()
          local humanoidRootPart = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
          if not humanoidRootPart then
            return nil
          end
          local huge = math.huge
          local v88 = nil

          for _, player in ipairs(Players:GetPlayers()) do
            if player ~= LocalPlayer and player.Character then
              local humanoidRootPart2 = player.Character:FindFirstChild("HumanoidRootPart")
              local humanoid = player.Character:FindFirstChildOfClass("Humanoid")

              if humanoidRootPart2 and humanoid and humanoid.Health > 0 then
                local magnitude = (humanoidRootPart2.Position - humanoidRootPart.Position).Magnitude

                if magnitude < huge then
                  huge = magnitude
                  v88 = player
                end
              end
            end
          end

          return v88
        end

        fn55 = function()
          if tbl24._batCounterWatchConn then
            pcall(function()
              tbl24._batCounterWatchConn:Disconnect()
            end)

            tbl24._batCounterWatchConn = nil
          end

          if tbl24._batCounterActivatedTP then
            tbl24._batCounterActivatedTP = false
            fn33(false)
          end

          tbl24._batCounterTarget = nil
        end

        fn56 = function()
          fn59()
          local character = LocalPlayer.Character
          local v88 = fn57()

          if v88 and character then
            fn58(v88, character)
          end
        end
      end
    end
  end

  local fn57, fn58, fn59, fn60, fn61

  do
    do
      do
        local connection, tbl25, connection2, fn62

        do
          fn57 = function()
            if tbl24.running then
              return
            end
            tbl24.running = true

            if tbl24.conn then
              pcall(function()
                tbl24.conn:Disconnect()
              end)
            end

            tbl24.conn = RunService.Heartbeat:Connect(function()
              if not Config.batCounterEnabled or tbl24.debounce then
                return
              end
              local character = LocalPlayer.Character
              if not character then
                return
              end
              local humanoid = character:FindFirstChildOfClass("Humanoid")
              if not humanoid then
                return
              end

              if fn54(humanoid) then
                tbl24.debounce = true

                task.spawn(function()
                  fn56()
                  task.wait(0.4)
                  tbl24.debounce = false
                end)
              end
            end)
          end

          fn58 = function()
            tbl24.running = false

            if tbl24.conn then
              pcall(function()
                tbl24.conn:Disconnect()
              end)

              tbl24.conn = nil
            end

            tbl24.debounce = false
            fn55()
          end

          connection = nil
          tbl25 = {}
          connection2 = nil

          do
            local function fn63(arg)
              if not arg or _G.HD_RESETTING then
                return
              end
              local humanoid = arg:WaitForChild("Humanoid", 5)
              if not humanoid then
                return
              end

              pcall(function()
                if _G.HD_RESETTING then
                  return
                end
                WorkspaceService.FallenPartsDestroyHeight = -50000
                humanoid.BreakJointsOnDeath = false
                humanoid.RequiresNeck = false
                humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
                humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
                humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
              end)

              humanoid.MaxHealth = math.huge
              humanoid.Health = math.huge

              local connection3 = humanoid.StateChanged:Connect(function(old, new)
                if not Config.antiDieEnabled or _G.HD_RESETTING then
                  return
                end

                if
                  new == Enum.HumanoidStateType.Dead
                  or new == Enum.HumanoidStateType.FallingDown
                  or new == Enum.HumanoidStateType.Ragdoll
                then
                  pcall(function()
                    if _G.HD_RESETTING then
                      return
                    end
                    humanoid.BreakJointsOnDeath = false
                    humanoid.RequiresNeck = false
                    humanoid.MaxHealth = math.huge
                    humanoid.Health = math.huge
                    humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
                    humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
                    humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
                    humanoid.PlatformStand = false
                  end)
                end
              end)

              table.insert(tbl25, connection3)

              pcall(function()
                if _G.HD_RESETTING then
                  return
                end
                humanoid.BreakJointsOnDeath = false
                humanoid.RequiresNeck = false
                humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
                humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
                humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
              end)

              local connection4 = humanoid:GetPropertyChangedSignal("Health"):Connect(function()
                if not Config.antiDieEnabled or _G.HD_RESETTING then
                  return
                end

                if humanoid.Health < math.huge then
                  pcall(function()
                    if _G.HD_RESETTING then
                      return
                    end
                    humanoid.BreakJointsOnDeath = false
                    humanoid.RequiresNeck = false
                    humanoid.MaxHealth = math.huge
                    humanoid.Health = math.huge
                    humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, false)
                  end)
                end
              end)

              table.insert(tbl25, connection4)

              if connection then
                connection:Disconnect()
              end

              connection = RunService.Heartbeat:Connect(function()
                if not Config.antiDieEnabled or _G.HD_RESETTING then
                  return
                end

                if humanoid and humanoid.Parent then
                  if humanoid.MaxHealth ~= math.huge then
                    humanoid.MaxHealth = math.huge
                  end

                  if humanoid.Health < math.huge then
                    humanoid.BreakJointsOnDeath = false
                    humanoid.RequiresNeck = false
                    humanoid.Health = math.huge
                  end
                end
              end)
            end

            fn62 = function()
              for _, v88 in ipairs(tbl25) do
                pcall(function()
                  v88:Disconnect()
                end)
              end

              tbl25 = {}

              if connection then
                connection:Disconnect()
                connection = nil
              end

              if connection2 then
                connection2:Disconnect()
                connection2 = nil
              end

              fn63(LocalPlayer.Character)

              connection2 = LocalPlayer.CharacterAdded:Connect(function(character)
                if not Config.antiDieEnabled then
                  return
                end
                task.wait(0.3)

                for _, v88 in ipairs(tbl25) do
                  pcall(function()
                    v88:Disconnect()
                  end)
                end

                tbl25 = {}
                fn63(character)
              end)
            end
          end
        end

        do
          local function fn63()
            for _, v88 in ipairs(tbl25) do
              pcall(function()
                v88:Disconnect()
              end)
            end

            tbl25 = {}

            if connection then
              connection:Disconnect()
              connection = nil
            end

            if connection2 then
              connection2:Disconnect()
              connection2 = nil
            end

            local character = LocalPlayer.Character

            if character then
              local humanoid = character:FindFirstChildOfClass("Humanoid")

              if humanoid then
                pcall(function()
                  WorkspaceService.FallenPartsDestroyHeight = -500
                  humanoid.RequiresNeck = true
                  humanoid.BreakJointsOnDeath = true
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, true)
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, true)
                  humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, true)

                  if humanoid.MaxHealth == math.huge then
                    humanoid.MaxHealth = 100
                  end

                  if humanoid.Health > 100 then
                    humanoid.Health = 100
                  end
                end)
              end
            end
          end

          fn59 = function(antiDieEnabled)
            Config.antiDieEnabled = antiDieEnabled

            if antiDieEnabled then
              fn62()
            else
              fn63()
            end

            saveConfig()
          end
        end
      end

      do
        local connection, fn62

        do
          connection = nil

          do
            local flag22 = false

            fn62 = function()
              if connection then
                return
              end
              flag22 = false

              connection = RunService.Heartbeat:Connect(function()
                local character = LocalPlayer.Character
                local humanoid = character and character:FindFirstChildOfClass("Humanoid")
                if not character or not humanoid or humanoid.Health <= 0 then
                  flag22 = false
                  return
                end

                if humanoid.WalkSpeed < 25 then
                  if Config.circleEnabled then
                    fn32(false)
                  end

                  if Config.tpBatEnabled then
                    fn33(false)
                  end

                  flag22 = true
                elseif flag22 then
                  flag22 = false

                  if Config.autoBatOnDropBrainrot then
                    task.spawn(function()
                      task.wait(0.1)

                      if fn32 then
                        fn32(true)
                      end
                    end)
                  end

                  if Config.tpBatOnDropBrainrot then
                    task.spawn(function()
                      task.wait(0.05)

                      if fn33 then
                        fn33(true)
                      end
                    end)
                  end
                end
              end)
            end
          end
        end

        do
          local function fn63()
            if connection then
              connection:Disconnect()
              connection = nil
            end
          end

          fn60 = function(arg)
            Config.safeModeEnabled = arg ~= false

            if Config.safeModeEnabled then
              fn62()

              if Config.bodyLockEnabled then
                fn37(false)
              end
            else
              fn63()
            end
          end
        end
      end

      do
        local connection = nil

        local function fn62()
          local character = LocalPlayer.Character
          local humanoid = character and character:FindFirstChildOfClass("Humanoid")

          if humanoid then
            pcall(function()
              humanoid.AutoRotate = true
            end)
          end
        end

        local function fn63()
          local character = LocalPlayer.Character
          character = character and character:FindFirstChild("HumanoidRootPart")
          if not character or character.Position.Y < -20 then
            return nil
          end
          local n32 = tonumber(Config.bodyLockRange) or 50
          local v88 = nil

          for _, player in ipairs(Players:GetPlayers()) do
            if player ~= LocalPlayer and player.Character then
              local humanoidRootPart = player.Character:FindFirstChild("HumanoidRootPart")
              local humanoid = player.Character:FindFirstChildOfClass("Humanoid")

              if humanoidRootPart and humanoid and humanoid.Health > 0 and humanoidRootPart.Position.Y > -20 then
                local magnitude = (character.Position - humanoidRootPart.Position).Magnitude

                if magnitude <= n32 then
                  n32 = magnitude
                  v88 = humanoidRootPart
                end
              end
            end
          end

          return v88
        end

        fn37 = function(bodyLockEnabled)
          if bodyLockEnabled and Config.safeModeEnabled then
            if fn60 then
              fn60(false)
            end

            saveConfig()

            if win and win.Notify then
              win:Notify("Body Lock", "Safe Mode turned OFF for Body Lock.", 2)
            end
          end

          Config.bodyLockEnabled = bodyLockEnabled

          if connection then
            connection:Disconnect()
            connection = nil
          end

          fn62()

          if bodyLockEnabled then
            connection = RunService.RenderStepped:Connect(function()
              if not Config.bodyLockEnabled or Config.safeModeEnabled then
                if connection then
                  connection:Disconnect()
                  connection = nil
                end

                fn62()
                return
              end

              local character = LocalPlayer.Character
              local humanoidRootPart = character and character:FindFirstChild("HumanoidRootPart")
              character = character and character:FindFirstChildOfClass("Humanoid")
              if not humanoidRootPart or not character or character.Health <= 0 or humanoidRootPart.Position.Y < -20 then
                fn62()
                return
              end
              local v88 = fn63()

              if v88 and v88.Position.Y > -20 then
                local position = humanoidRootPart.Position
                local position2 = v88.Position
                local n32 = position2.X - position.X
                local n33 = position2.Z - position.Z

                if n32 * n32 + n33 * n33 > 0.4 then
                  character.AutoRotate = false
                  humanoidRootPart.CFrame =
                    humanoidRootPart.CFrame:Lerp(CFrame.lookAt(position, Vector3.new(position2.X, position.Y, position2.Z)), 0.42)
                else
                  character.AutoRotate = true
                end
              else
                character.AutoRotate = true
              end
            end)
          else
            fn62()
          end

          saveConfig()
        end
      end
    end

    do
      local connection, fn62

      do
        connection = nil

        do
          local v88 = 0

          fn62 = function()
            local now2 = os.clock()
            if now2 - v88 < 0.25 then
              return
            end
            v88 = now2

            for _, player in ipairs(Players:GetPlayers()) do
              if player ~= LocalPlayer and player.Character then
                for _, child in ipairs(player.Character:GetChildren()) do
                  if child:IsA("BasePart") and child.CanCollide then
                    child.CanCollide = false
                  end
                end
              end
            end
          end
        end
      end

      do
        local function fn63()
          if connection then
            return
          end

          connection = RunService.Stepped:Connect(function()
            if not Config.antiCollisionEnabled then
              if connection then
                connection:Disconnect()
                connection = nil
              end

              return
            end

            fn62()
          end)
        end

        fn61 = function()
          Config.antiCollisionEnabled = true
          fn63()
        end

        task.defer(function()
          fn63()
        end)

        LocalPlayer.CharacterAdded:Connect(function()
          task.wait(0.2)
          fn63()
        end)
      end
    end

    do
      local v88, flag22, thread, v89, flag23, flag24, fn62

      do
        v88 = LocalPlayer

        flag22 = false
        thread = nil
        v89 = nil
        flag23 = false
        flag24 = false

        do
          local flag25 = false

          pcall(function()
            RunService:UnbindFromRenderStep("HookResetCamPin")
          end)

          fn62 = function(arg, arg2)
            if not arg or not arg.Parent then
              return false
            end
            local humanoid = arg:FindFirstChildOfClass("Humanoid")
            if not humanoid then
              return false
            end

            pcall(function()
              local v90 = humanoid
              local v91 = arg2
              local hipHeight

              if arg2 then
                hipHeight = v91
              else
                hipHeight = 2
              end

              v90.HipHeight = hipHeight
              local humanoidRootPart = arg:FindFirstChild("HumanoidRootPart")

              if humanoidRootPart then
                local position = humanoidRootPart.Position

                if
                  (
                    position.X ~= position.X
                    or position.Y ~= position.Y
                    or position.Z ~= position.Z
                    or math.abs(position.X) > 1000000
                    or math.abs(position.Y) > 1000000
                    or math.abs(position.Z) > 1000000
                  ) and fn40
                then
                  pcall(fn40, true)
                end

                humanoidRootPart.CanCollide = true
              end

              for _, child in ipairs(arg:GetChildren()) do
                if child:IsA("BasePart") and child.Name ~= "HumanoidRootPart" then
                  child.CanCollide = true
                end
              end
            end)

            return true
          end

          fn38 = function()
            if flag22 then
              return
            end
            flag22 = true
            flag23 = false
            flag24 = false
            _G.HD_RESETTING = true

            if Config.antiDieEnabled and stopCleanAntiDie then
              pcall(stopCleanAntiDie)
            end

            if Config._cancelAutoGrabInFlight then
              pcall(Config._cancelAutoGrabInFlight)
            end

            tbl23.active = false
            local character = v88.Character

            if not character then
              _G.HD_RESETTING = false
              flag22 = false
              return
            end

            local humanoid = character:FindFirstChildOfClass("Humanoid")

            if not humanoid then
              _G.HD_RESETTING = false
              flag22 = false
              return
            end

            pcall(function()
              humanoid.RequiresNeck = true
              humanoid.BreakJointsOnDeath = true
              humanoid:SetStateEnabled(Enum.HumanoidStateType.Dead, true)
            end)

            v89 = character
            local v90 = false

            thread = task.spawn(function()
              local hipHeight = humanoid.HipHeight
              local n32 = 0

              while true do
                if character and character.Parent and humanoid and humanoid.Health > 0 and not v90 and not flag24 then
                  if v88.Character ~= character then
                    v90 = true
                    break
                  else
                    pcall(function()
                      humanoid.HipHeight = 1e30
                      humanoid.AutoRotate = true
                      local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")

                      if humanoidRootPart then
                        humanoidRootPart.CanCollide = false
                      end

                      for _, child in ipairs(character:GetChildren()) do
                        if child:IsA("BasePart") and child.Name ~= "HumanoidRootPart" then
                          child.CanCollide = false
                        end
                      end
                    end)

                    if not character or not character.Parent or not humanoid or humanoid.Health <= 0 or v88.Character ~= character then
                      flag23 = true
                      break
                    else
                      n32 += 1
                      if not (40 <= n32) then
                        task.wait()
                        continue
                      end
                    end
                  end
                end

                break
              end

              if not flag23 then
                if character and character.Parent and humanoid and humanoid.Health > 0 and not v90 then
                  local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")

                  if humanoidRootPart then
                    local position = humanoidRootPart.Position

                    if
                      position.X ~= position.X
                      or position.Y ~= position.Y
                      or position.Z ~= position.Z
                      or math.abs(position.X) > 5000
                      or math.abs(position.Y) > 5000
                      or math.abs(position.Z) > 5000
                    then
                      if fn40 then
                        pcall(fn40, true)
                      end

                      task.wait(0.15)
                    end
                  end

                  pcall(function()
                    character:BreakJoints()
                  end)

                  task.wait()

                  if not character.Parent or humanoid.Health <= 0 then
                    flag23 = true
                  end
                end
              end

              if not flag23 and character and character.Parent and humanoid then
                fn62(character, hipHeight)
              end

              flag22 = false
              thread = nil
              v89 = nil
              flag24 = false

              if
                not flag23
                and not flag25
                and character
                and character.Parent
                and humanoid
                and humanoid.Health > 0
                and v88.Character == character
              then
                flag25 = true
                local v91 = character
                local v92 = humanoid

                task.delay(0.2, function()
                  if v88.Character == v91 and v91.Parent and v92 and v92.Health > 0 then
                    fn38()
                  else
                    flag25 = false
                  end
                end)
              else
                flag25 = false
              end
            end)
          end
        end
      end

      local function fn63()
        flag24 = true

        if thread then
          task.cancel(thread)
          thread = nil
        end

        flag22 = false
        v89 = nil

        if not fn62(v88.Character, 2) then
          task.delay(0.3, function()
            fn62(v88.Character, 2)
          end)
        end
      end

      v88.CharacterAdded:Connect(function()
        _G.HD_RESETTING = false
        fn63()
        flag22 = false
        v89 = nil
        flag23 = false
        flag24 = false

        if Config.antiDieEnabled and startCleanAntiDie then
          task.delay(0.2, startCleanAntiDie)
        end
      end)

      pcall(function()
        local resetLite = playerGui:FindFirstChild("ResetLite")

        if resetLite then
          resetLite:Destroy()
        end

        local resetLite2 = game:GetService("CoreGui"):FindFirstChild("ResetLite")

        if resetLite2 then
          resetLite2:Destroy()
        end
      end)

      pcall(function()
        game:GetService("StarterGui"):SetCore("ResetButtonCallback", true)
      end)

      _G.FrameResetLite = { Reset = fn38, Stop = fn63 }
    end
  end

  local fn62, fn63, fn64, tbl25, thread, thread2, tbl26, obj, n32, fn65
  local fn66, fn67, fn68

  do
    do
      do
        local function fn69()
          local currentCamera = WorkspaceService.CurrentCamera

          if currentCamera then
            pcall(function()
              currentCamera.FieldOfView = Config.fov
            end)
          end
        end

        fn62 = function(arg)
          Config.fov = math.clamp(math.floor((arg or 80) + 0.5), 80, 120)
          fn69()
          saveConfig()
        end

        WorkspaceService:GetPropertyChangedSignal("CurrentCamera"):Connect(fn69)

        LocalPlayer.CharacterAdded:Connect(function()
          task.wait(0.3)
          fn69()
        end)
      end
    end

    fn63 = function(arg)
      Config.stretchRez = math.clamp(arg or 1, 0.1, 1)
      saveConfig()
    end

    RunService.RenderStepped:Connect(function()
      if Config.stretchRez >= 1 then
        return
      end
      local currentCamera = WorkspaceService.CurrentCamera

      if currentCamera then
        currentCamera.CFrame = currentCamera.CFrame * CFrame.new(0, 0, 0, 1, 0, 0, 0, Config.stretchRez, 0, 0, 0, 1)
      end
    end)

    fn64 = function() end

    tbl25 = {}
    thread = nil
    thread2 = nil
    tbl26 = {}
    obj = setmetatable({}, { __mode = "k" })

    do
      local obj2 = setmetatable({}, { __mode = "k" })
      local tbl27 = nil
      local v88 = nil
      n32 = 0

      fn65 = function(arg, arg2)
        if not arg then
          return
        end
        local tbl28 = obj2[arg]

        if not tbl28 then
          tbl28 = { values = {}, captured = {} }
          obj2[arg] = tbl28
        end

        for k, v89 in pairs(arg2) do
          pcall(function()
            if tbl28.captured[k] then
              return
            end

            local ok, result = pcall(function()
              return arg[k]
            end)

            if ok then
              tbl28.values[k] = result
              tbl28.captured[k] = true
              if result == v89 then
                return
              end
            else
              tbl28.captured[k] = true
            end

            arg[k] = v89
          end)
        end
      end

      fn66 = function(arg)
        task.spawn(function()
          local n33 = 0

          for k, v89 in pairs(obj2) do
            if n32 ~= arg or Config.fpsBoostEnabled then
              return
            end

            if k and v89 then
              for k2 in pairs(v89.captured) do
                pcall(function()
                  k[k2] = v89.values[k2]
                end)
              end
            end

            n33 += 1

            if n33 % 100 == 0 then
              task.wait()
            end
          end

          if n32 == arg and not Config.fpsBoostEnabled then
            obj2 = setmetatable({}, { __mode = "k" })
          end
        end)
      end

      fn67 = function()
        if not tbl27 then
          tbl27 = {}

          pcall(function()
            tbl27.QualityLevel = settings().Rendering.QualityLevel
          end)

          pcall(function()
            tbl27.MeshPartDetailLevel = settings().Rendering.MeshPartDetailLevel
          end)
        end

        pcall(function()
          local level01 = Enum.QualityLevel.Level01

          if settings().Rendering.QualityLevel ~= level01 then
            local level012 = Enum.QualityLevel.Level01
            settings().Rendering.QualityLevel = level012
          end
        end)

        pcall(function()
          local level01 = Enum.MeshPartDetailLevel.Level01

          if settings().Rendering.MeshPartDetailLevel ~= level01 then
            local level012 = Enum.MeshPartDetailLevel.Level01
            settings().Rendering.MeshPartDetailLevel = level012
          end
        end)
      end

      fn68 = function()
        if tbl27 then
          if tbl27.QualityLevel then
            pcall(function()
              local qualityLevel = tbl27.QualityLevel
              settings().Rendering.QualityLevel = qualityLevel
            end)
          end

          if tbl27.MeshPartDetailLevel then
            pcall(function()
              local meshPartDetailLevel = tbl27.MeshPartDetailLevel
              settings().Rendering.MeshPartDetailLevel = meshPartDetailLevel
            end)
          end

          tbl27 = nil
        end

        if v88 then
          pcall(function()
            if setfpscap then
              setfpscap(v88)
            end
          end)

          v88 = nil
        end
      end
    end
  end

  do
    do
      local function fn69(arg)
        if not arg or not arg.Parent then
          return
        end
        local character = LocalPlayer.Character

        if character then
          character = arg == character or arg:IsDescendantOf(character)
        end

        if character then
          return
        end

        if arg == playerGui or arg:IsDescendantOf(playerGui) then
          return
        end

        if arg:IsA("Sky") or arg.Name == "HookDuelsDarkCC" then
          return
        end

        pcall(function()
          if
            arg:IsA("ParticleEmitter")
            or arg:IsA("Trail")
            or arg:IsA("Beam")
            or arg:IsA("Smoke")
            or arg:IsA("Fire")
            or arg:IsA("Sparkles")
          then
            fn65(arg, { Enabled = false })
          elseif arg:IsA("Highlight") or arg:IsA("SurfaceLight") or arg:IsA("PointLight") or arg:IsA("SpotLight") then
            fn65(arg, { Enabled = false })
          elseif arg:IsA("SelectionBox") then
            fn65(arg, { Visible = false })
          elseif arg:IsA("PostEffect") then
            if not arg:IsA("ColorCorrectionEffect") then
              fn65(arg, { Enabled = false })
            end
          elseif arg:IsA("Atmosphere") then
            fn65(arg, { Density = 0, Haze = 0, Glare = 0 })
          elseif arg:IsA("Clouds") then
            fn65(arg, { Density = 0, Cover = 0, Enabled = false })
          elseif arg:IsA("Explosion") then
            fn65(arg, { Visible = false })
          elseif arg:IsA("Decal") or arg:IsA("Texture") then
            fn65(arg, { Transparency = 1 })
          elseif arg:IsA("SurfaceAppearance") then
            fn65(arg, { ColorMap = "", MetalnessMap = "", NormalMap = "", RoughnessMap = "" })
          elseif arg:IsA("SpecialMesh") then
            fn65(arg, { TextureId = "" })
          elseif arg:IsA("Shirt") then
            fn65(arg, { ShirtTemplate = "" })
          elseif arg:IsA("Pants") then
            fn65(arg, { PantsTemplate = "" })
          elseif arg:IsA("ShirtGraphic") then
            fn65(arg, { Graphic = "" })
          elseif arg:IsA("MeshPart") then
            fn65(arg, {
              Material = Enum.Material.SmoothPlastic,
              MaterialVariant = "",
              TextureID = "",
              Reflectance = 0,
              CastShadow = false,
              DoubleSided = false,
            })
          elseif arg:IsA("UnionOperation") or arg:IsA("NegateOperation") then
            fn65(arg, {
              Material = Enum.Material.SmoothPlastic,
              MaterialVariant = "",
              Reflectance = 0,
              CastShadow = false,
              UsePartColor = true,
            })
          elseif arg:IsA("BasePart") then
            local tbl27 = {
              Material = Enum.Material.SmoothPlastic,
              MaterialVariant = "",
              Reflectance = 0,
              CastShadow = false,
            }

            if arg:IsA("Part") then
              tbl27.TopSurface = Enum.SurfaceType.Smooth
              tbl27.BottomSurface = Enum.SurfaceType.Smooth
            end

            fn65(arg, tbl27)
          end
        end)
      end

      local function fn70()
        fn65(Lighting, {
          GlobalShadows = false,
          EnvironmentDiffuseScale = 0,
          EnvironmentSpecularScale = 0,
          ShadowSoftness = 0,
          FogEnd = 9e9,
          FogStart = 9e9,
        })

        for _, child in ipairs(Lighting:GetChildren()) do
          if not child:IsA("Sky") and child.Name ~= "HookDuelsDarkCC" then
            fn69(child)
          end
        end

        local terrain = WorkspaceService:FindFirstChildOfClass("Terrain")

        if terrain then
          fn65(terrain, {
            WaterWaveSize = 0,
            WaterWaveSpeed = 0,
            WaterReflectance = 0,
            WaterTransparency = 1,
            Decoration = false,
          })

          for _, child in ipairs(terrain:GetChildren()) do
            if child:IsA("Clouds") then
              fn69(child)
            end
          end
        end

        fn67()
      end

      local flag22 = false

      Config._setFpsBoost = function(arg, arg2)
        local fpsBoostEnabled = not not arg
        if not arg2 and flag22 == fpsBoostEnabled and Config.fpsBoostEnabled == fpsBoostEnabled then
          return
        end
        flag22 = fpsBoostEnabled
        n32 += 1
        local v88 = n32
        Config.fpsBoostEnabled = fpsBoostEnabled
        flag19 = fpsBoostEnabled

        if fpsBoostEnabled then
          fn70()

          task.spawn(function()
            local descendants = WorkspaceService:GetDescendants()
            local n33 = 0

            for i = 1, #descendants do
              if not (not Config.fpsBoostEnabled or n32 ~= v88) then
                fn69(descendants[i])
                n33 += 1

                if n33 >= 60 then
                  RunService.Heartbeat:Wait()
                  n33 = 0
                end

                continue
              end

              break
            end
          end)

          task.spawn(function()
            local descendants = Lighting:GetDescendants()

            for i = 1, #descendants do
              if not (not Config.fpsBoostEnabled or n32 ~= v88) then
                fn69(descendants[i])
                continue
              end
              break
            end
          end)

          if #tbl25 == 0 then
            tbl25[1] = WorkspaceService.DescendantAdded:Connect(function(descendant)
              if Config.fpsBoostEnabled and #tbl26 < 3000 then
                tbl26[#tbl26 + 1] = descendant
              end
            end)

            tbl25[2] = Lighting.DescendantAdded:Connect(function(descendant)
              if Config.fpsBoostEnabled then
                fn69(descendant)
              end
            end)
          end

          if not thread2 then
            thread2 = task.spawn(function()
              while Config.fpsBoostEnabled do
                local v89 = 0

                while v89 < 150 do
                  local v90 = table.remove(tbl26, 1)

                  if v90 ~= nil then
                    v89 += 1

                    if v90.Parent and Config.fpsBoostEnabled then
                      fn69(v90)
                    end

                    continue
                  end

                  break
                end

                task.wait(0.1)
              end

              thread2 = nil
            end)
          end

          if not thread then
            thread = task.spawn(function()
              while Config.fpsBoostEnabled do
                pcall(function()
                  if Lighting.GlobalShadows ~= false then
                    Lighting.GlobalShadows = false
                  end

                  if Lighting.EnvironmentDiffuseScale ~= 0 then
                    Lighting.EnvironmentDiffuseScale = 0
                  end

                  if Lighting.EnvironmentSpecularScale ~= 0 then
                    Lighting.EnvironmentSpecularScale = 0
                  end

                  if Lighting.FogEnd ~= 9e9 then
                    Lighting.FogEnd = 9e9
                  end

                  if Lighting.FogStart ~= 9e9 then
                    Lighting.FogStart = 9e9
                  end
                end)

                fn67()
                task.wait(10)
              end

              thread = nil
            end)
          end
        else
          for _, v89 in ipairs(tbl25) do
            pcall(function()
              v89:Disconnect()
            end)
          end

          tbl25 = {}

          for _, v89 in pairs(obj) do
            pcall(function()
              v89:Disconnect()
            end)
          end

          obj = setmetatable({}, { __mode = "k" })
          tbl26 = {}
          fn68()
          fn66(v88)
        end
      end
    end
  end

  if Config.fpsBoostEnabled then
    task.defer(function()
      pcall(function()
        Config._setFpsBoost(true, true)

        if win and win.particles and win.particles.layer then
          win.particles.layer.Visible = false
        end
      end)
    end)
  end

  UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if flag18 then
      return
    end

    if gameProcessed and UserInputService:GetFocusedTextBox() then
      return
    end

    if input.UserInputType.Name:find("Gamepad") then
      local ok, result = pcall(function()
        return game:GetService("GuiService").SelectedObject
      end)

      if ok and result and result.Name == "HookKeybindBox" then
        local flag22

        while true do
          local flag23 = result and result ~= game
          flag22 = true

          if flag23 then
            if result:IsA("GuiObject") and not result.Visible then
              flag22 = false
              break
            elseif result:IsA("LayerCollector") and not result.Enabled then
              flag22 = false
              break
            else
              result = result.Parent
              continue
            end
          end

          break
        end

        if flag22 then
          return
        end
      end
    end

    if inputMatches(input, Keybinds.speed) then
      Config.speedToggled = not Config.speedToggled

      if carry and carry.setState then
        pcall(function()
          carry.setState(Config.speedToggled)
        end)
      end

      saveConfig()
    elseif inputMatches(input, Keybinds.laggerMode) then
      fn43()
    elseif inputMatches(input, Keybinds.customSpeedMode) then
      fn44()
    elseif inputMatches(input, Keybinds.circle) then
      fn32(not Config.circleEnabled)
    elseif inputMatches(input, Keybinds.dropBrainrot) then
      fn50()
    elseif inputMatches(input, Keybinds.tpDown) then
      fn40()
    elseif inputMatches(input, Keybinds.walkLeft) then
      fn46()
    elseif inputMatches(input, Keybinds.tpBat) then
      fn33(not Config.tpBatEnabled)
    elseif inputMatches(input, Keybinds.bodyLock) then
      fn37(not Config.bodyLockEnabled)
    elseif inputMatches(input, Keybinds.instaReset) then
      fn38()
    end
  end)

  do
    local function fn69()
      fn34 = function(arg)
        local v88 = arg or color
        local hookIntro = playerGui:FindFirstChild("HookIntro")

        if hookIntro then
          hookIntro:Destroy()
        end

        local instance = Instance.new("ScreenGui")
        instance.Name = "HookIntro"
        instance.ResetOnSpawn = false
        instance.IgnoreGuiInset = true
        instance.DisplayOrder = 9999
        instance.Parent = playerGui
        local imageLabel = Instance.new("ImageLabel")
        imageLabel.AnchorPoint = Vector2.new(0.5, 0.5)
        imageLabel.Position = UDim2.fromScale(0.5, 0.46)
        imageLabel.Size = UDim2.fromScale(0.2, 0.1)
        imageLabel.BackgroundTransparency = 1
        imageLabel.Image = "rbxassetid://5028857472"
        imageLabel.ImageColor3 = v88
        imageLabel.ImageTransparency = 1
        imageLabel.ScaleType = Enum.ScaleType.Slice
        imageLabel.SliceCenter = Rect.new(24, 24, 276, 276)
        imageLabel.ZIndex = 1
        imageLabel.Parent = instance
        local imageLabel2 = Instance.new("ImageLabel")
        imageLabel2.AnchorPoint = Vector2.new(0.5, 0.5)
        imageLabel2.Position = UDim2.fromScale(0.5, 0.46)
        imageLabel2.Size = UDim2.fromOffset(40, 40)
        imageLabel2.BackgroundTransparency = 1
        imageLabel2.Image = "rbxassetid://266543268"
        imageLabel2.ImageColor3 = v88
        imageLabel2.ImageTransparency = 0.4
        imageLabel2.ZIndex = 0
        imageLabel2.Parent = instance
        local frame = Instance.new("Frame")
        frame.AnchorPoint = Vector2.new(0.5, 0.5)
        frame.Position = UDim2.fromScale(0.5, 0.46)
        frame.Size = UDim2.fromOffset(520, 96)
        frame.BackgroundTransparency = 1
        frame.ZIndex = 2
        frame.Parent = instance

        local function fn70(textColor3, zIndex)
          local instance2 = Instance.new("TextLabel")
          instance2.AnchorPoint = Vector2.new(0.5, 0.5)
          instance2.Position = UDim2.fromScale(0.5, 0.5)
          instance2.Size = UDim2.fromScale(1, 1)
          instance2.BackgroundTransparency = 1
          instance2.Text = "HOOK DUELS"
          instance2.Font = Enum.Font.MontserratBlack
          instance2.TextScaled = true
          instance2.TextColor3 = textColor3
          instance2.ZIndex = zIndex
          instance2.Parent = frame
          instance2.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
          instance2.TextStrokeTransparency = 0.25
          return instance2
        end

        local v89 = fn70(Color3.fromRGB(255, 45, 70), 2)
        local v90 = fn70(Color3.fromRGB(50, 180, 255), 2)
        local v91 = fn70(Color3.fromRGB(255, 255, 255), 4)
        local frame2 = Instance.new("Frame")
        frame2.Size = UDim2.fromScale(1, 1)
        frame2.BackgroundTransparency = 1
        frame2.ClipsDescendants = true
        frame2.ZIndex = 10
        frame2.Parent = frame
        local frame3 = Instance.new("Frame")
        frame3.Size = UDim2.new(0, 70, 1.8, 0)
        frame3.Position = UDim2.new(-0.4, 0, -0.4, 0)
        frame3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        frame3.BackgroundTransparency = 0.55
        frame3.BorderSizePixel = 0
        frame3.Rotation = 16
        frame3.ZIndex = 6
        frame3.Parent = frame2
        local instance2 = Instance.new("UIGradient", frame3)
        local numberSequence = NumberSequence.new
        local tbl27 = {}
        local v92 = NumberSequenceKeypoint.new(0, 1)
        local v93 = NumberSequenceKeypoint.new(0.5, 0.2)
        tbl27[1] = v92
        tbl27[2] = v93

        do
          local values = table.pack(NumberSequenceKeypoint.new(1, 1))
          table.move(values, 1, values.n, 3, tbl27)
        end

        instance2.Transparency = numberSequence(tbl27)
        local frame4 = Instance.new("Frame")
        frame4.AnchorPoint = Vector2.new(0.5, 0.5)
        frame4.Position = UDim2.fromScale(0.5, 0.66)
        frame4.Size = UDim2.fromOffset(0, 3)
        frame4.BackgroundColor3 = v88
        frame4.BorderSizePixel = 0
        frame4.ZIndex = 3
        frame4.Parent = instance
        Instance.new("UICorner", frame4).CornerRadius = UDim.new(1, 0)
        local textLabel = Instance.new("TextLabel")
        textLabel.AnchorPoint = Vector2.new(0.5, 0.5)
        textLabel.Position = UDim2.fromScale(0.5, 0.72)
        textLabel.Size = UDim2.fromOffset(420, 24)
        textLabel.BackgroundTransparency = 1
        textLabel.Text = "lukas meu meu piruzao"
        textLabel.Font = Enum.Font.MontserratBold
        textLabel.TextSize = 16
        textLabel.TextColor3 = v88
        textLabel.TextTransparency = 1
        textLabel.ZIndex = 3
        textLabel.Parent = instance
        textLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
        textLabel.TextStrokeTransparency = 0.4
        frame.Size = UDim2.fromOffset(286, 53)
        v91.TextTransparency = 1
        v89.TextTransparency = 1
        v90.TextTransparency = 1
        TweenService
          :Create(frame, TweenInfo.new(0.55, Enum.EasingStyle.Back, Enum.EasingDirection.Out), { Size = UDim2.fromOffset(520, 96) })
          :Play()
        TweenService:Create(v91, TweenInfo.new(0.3), { TextTransparency = 0 }):Play()
        TweenService:Create(v89, TweenInfo.new(0.3), { TextTransparency = 0.25 }):Play()
        TweenService:Create(v90, TweenInfo.new(0.3), { TextTransparency = 0.25 }):Play()
        TweenService
          :Create(imageLabel, TweenInfo.new(0.6, Enum.EasingStyle.Quad), { Size = UDim2.fromScale(0.75, 0.5), ImageTransparency = 0.5 })
          :Play()
        TweenService:Create(
          imageLabel2,
          TweenInfo.new(0.7, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
          { Size = UDim2.fromOffset(560, 560), ImageTransparency = 1 }
        ):Play()
        local now2 = tick()

        local connection = RunService.RenderStepped:Connect(function()
          if tick() - now2 < 0.42 then
            local n33 = math.random(-10, 7)
            v89.Position = UDim2.new(0.5, -3 + n33, 0.5, math.random(-3, 3))
            v90.Position = UDim2.new(0.5, 3 - n33, 0.5, math.random(-3, 3))
            local v94 = v91
            local v95 = 0.2
            v94.TextTransparency = math.random() < v95 and 0.5 or 0
          else
            v89.Position = UDim2.new(0.5, -2, 0.5, 0)
            v90.Position = UDim2.new(0.5, 2, 0.5, 0)
            v91.TextTransparency = 0
          end
        end)

        task.delay(0.3, function()
          TweenService:Create(frame3, TweenInfo.new(0.6, Enum.EasingStyle.Quad), { Position = UDim2.new(1.1, 0, -0.4, 0) }):Play()
          TweenService
            :Create(frame4, TweenInfo.new(0.45, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), { Size = UDim2.fromOffset(300, 3) })
            :Play()
          TweenService:Create(textLabel, TweenInfo.new(0.4), { TextTransparency = 0 }):Play()
        end)

        task.delay(1.25, function()
          if connection.Connected then
            connection:Disconnect()
          end

          TweenService:Create(
            frame,
            TweenInfo.new(0.45, Enum.EasingStyle.Quad, Enum.EasingDirection.In),
            { Position = UDim2.fromScale(0.5, 0.3), Size = UDim2.fromOffset(560, 104) }
          ):Play()

          for _, v94 in ipairs({ v91, v89, v90, textLabel }) do
            TweenService:Create(v94, TweenInfo.new(0.4), { TextTransparency = 1 }):Play()
          end

          TweenService:Create(imageLabel, TweenInfo.new(0.4), { ImageTransparency = 1 }):Play()
          TweenService:Create(frame4, TweenInfo.new(0.3), { BackgroundTransparency = 1 }):Play()

          task.delay(0.5, function()
            instance:Destroy()
          end)
        end)
      end
    end

    fn69()
  end

  index._startUI = function()
    fn41()
    Config.circleEnabled = false
    Config.tpBatEnabled = false
    tbl23.active = false

    Config._clearAutoGrabHud = function()
      for _, child in ipairs(playerGui:GetChildren()) do
        if child.Name == "AutoStealBar" or child.Name == "HookDuelPreDuelWidget" then
          pcall(function()
            child:Destroy()
          end)
        end
      end
    end

    Config._clearAutoGrabHud()

    local tbl27 = {
      ["Velvet Rose"] = Color3.fromRGB(190, 32, 168),
      ["Neon Pink"] = Color3.fromRGB(255, 45, 185),
      ["Neon Cyan"] = Color3.fromRGB(0, 240, 255),
      ["Electric Violet"] = Color3.fromRGB(168, 85, 247),
      ["Blood Red"] = Color3.fromRGB(255, 45, 70),
      ["Lime Green"] = Color3.fromRGB(60, 235, 100),
      ["Golden Yellow"] = Color3.fromRGB(255, 185, 40),
      ["Pure White"] = Color3.fromRGB(255, 255, 255),
      Blurple = Color3.fromRGB(126, 134, 255),
      Emerald = Color3.fromRGB(52, 216, 153),
      ["Sunset Orange"] = Color3.fromRGB(255, 120, 50),
      ["Hot Magenta"] = Color3.fromRGB(255, 20, 147),
    }

    local v88 = index.new({
      title = "Hook Duels",
      subtitle = "lukas senta na banana",
      theme = "Velvet Rose",
      width = Config.guiWidth or 500,
      height = Config.guiHeight or 600,
      layout = 2,
      background = 1,
      imageTransparency = 1,
    })

    win = v88

    local color2 = Color3.fromRGB(175, 65, 255)
    v88:SetTheme("Velvet Rose")
    v88:SetAccent(color2)
    color = v88.theme.Data.Accent
    BarBgImage = Assets.Backgrounds[v88._bgIndex] or ""
    local setAccent = v88.SetAccent
    local setTheme = v88.SetTheme

    v88.SetAccent = function(arg, arg2)
      setAccent(arg, arg2)
      color = arg2
    end

    v88.SetTheme = function(arg, arg2)
      setTheme(arg, arg2)
      color = arg.theme.Data.Accent
    end

    local Movement = v88:Tab("Movement", "Speed, jump tools and path automation")
    Movement:Section("SPEED MODES & SWITCHING", "Switch between Normal, Lagger, and Custom speed profiles")

    Movement:Toggle("Auto Switch Speed", Config.autoSwitchSpeedEnabled or false, function(autoSwitchSpeedEnabled)
      Config.autoSwitchSpeedEnabled = autoSwitchSpeedEnabled
      saveConfig()
    end)

    Movement:Keybind("Carry Key", Keybinds.speed, function(speed)
      Keybinds.speed = speed
      saveConfig()
    end)

    Movement:Keybind("Lagger Key", Keybinds.laggerMode or Enum.KeyCode.R, function(laggerMode)
      Keybinds.laggerMode = laggerMode
      saveConfig()
    end)

    Movement:Keybind("Custom Key", Keybinds.customSpeedMode or Enum.KeyCode.None, function(customSpeedMode)
      Keybinds.customSpeedMode = customSpeedMode
      saveConfig()
    end)

    Movement:Section("NORMAL MODE SPEEDS", "Standard match speeds")

    Movement:Slider("Normal Speed", 0, 200, Config.normalSpeed or 59, function(normalSpeed)
      Config.normalSpeed = normalSpeed
      saveConfig()
    end)

    Movement:Slider("Normal Carry Speed", 0, 200, Config.normalCarrySpeed or 29, function(normalCarrySpeed)
      Config.normalCarrySpeed = normalCarrySpeed
      saveConfig()
    end)

    Movement:Section("LAGGER MODE SPEEDS", "Lower speeds for lagger carry optimization")

    Movement:Slider("Lagger Normal Speed", 0, 200, Config.laggerNormalSpeed or 35, function(laggerNormalSpeed)
      Config.laggerNormalSpeed = laggerNormalSpeed
      saveConfig()
    end)

    Movement:Slider("Lagger Carry Speed", 0, 200, Config.laggerCarrySpeed or 15, function(laggerCarrySpeed)
      Config.laggerCarrySpeed = laggerCarrySpeed
      saveConfig()
    end)

    Movement:Section("CUSTOM MODE SPEEDS", "Customizable profile speeds")

    Movement:Slider("Custom Normal Speed", 0, 150, Config.customNormalSpeed or 70, function(customNormalSpeed)
      Config.customNormalSpeed = customNormalSpeed
      saveConfig()
    end)

    Movement:Slider("Custom Carry Speed", 0, 150, Config.customCarrySpeed or 35, function(customCarrySpeed)
      Config.customCarrySpeed = customCarrySpeed
      saveConfig()
    end)

    Movement:Section("JUMP & MOBILITY", "Infinite jump normal and hold mode")

    Movement:Toggle("Infinite Jump", Config.infJumpEnabled, function(arg)
      fn35(arg)
    end)

    local v89 = Movement
    local dropdown = v89.Dropdown
    local tbl28 = { "Normal Mode", "Hold Mode" }

    local function fn69(infJumpMode)
      Config.infJumpMode = infJumpMode

      if Config.infJumpEnabled then
        fn35(true)
      end

      saveConfig()
    end

    dropdown(v89, "Method", tbl28, fn69, Config.infJumpMode or "Normal Mode")
    Movement:Section("AUTO LEFT/RIGHT", "Semi Auto Play auto-detects your side from your plot sign or location")

    Movement:Keybind("Auto Left/Right Bind", Keybinds.walkLeft, function(walkLeft)
      Keybinds.walkLeft = walkLeft
      saveConfig()
    end)

    pcall(function()
      local character = LocalPlayer.Character
      character = character and character:FindFirstChild("Head")
      character = character and character:FindFirstChild("RagStealBillboard")

      if character then
        character:Destroy()
      end
    end)

    local Combat = v88:Tab("Combat", "Auto hit, grabbing, bat tools and defense")
    Combat:Section("AUTO GRAB", "Nearby target scanning, progress bar and grab version")

    v86 = Combat:Toggle("Auto Grab", Config.autoGrabEnabled, function(autoGrabEnabled)
      if fn39 then
        fn39(autoGrabEnabled)
      else
        Config.autoGrabEnabled = autoGrabEnabled
      end
    end)

    Combat:Dropdown("Version", { "V1", "V2", "V3" }, function(autoGrabMode)
      Config.autoGrabMode = autoGrabMode
      local tbl29 = { V1 = "semi", V2 = "normal", V3 = "normalv2" }

      if _G.VampireStealModes and _G.VampireStealModes.SetMode then
        pcall(_G.VampireStealModes.SetMode, tbl29[autoGrabMode] or "semi")
      end

      saveConfig()
    end, Config.autoGrabMode)

    Combat:Slider("Radius", 5, 300, Config.primeRange, function(arg)
      Config.primeRange = math.clamp(arg, 5, 300)

      if _G.VampireStealModes and _G.VampireStealModes.State then
        _G.VampireStealModes.State.SemiPrimeRange = Config.primeRange
        _G.VampireStealModes.State.NormalRadius = Config.primeRange
      end

      saveConfig()
    end)

    Combat:Toggle("Ragdoll Timer", Config.ragTimerEnabled, function(ragTimerEnabled)
      Config.ragTimerEnabled = ragTimerEnabled

      if ragTimerEnabled then
        fn52()
      else
        fn53()
      end

      saveConfig()
    end)

    Combat:Section("BAT TOOLS", "Auto hit, bats and on-drop automation")

    Combat:Toggle("Auto Hit", Config.autoHitEnabled, function(arg)
      Config._setAutoHit(arg)
    end)

    Combat:Keybind("Auto Bat Key", Keybinds.circle, function(circle)
      Keybinds.circle = circle
      saveConfig()
    end)

    Combat:Keybind("TP Bat Key", Keybinds.tpBat, function(tpBat)
      Keybinds.tpBat = tpBat
      saveConfig()
    end)

    Combat:Toggle("Auto Bat on Drop Brainrot", Config.autoBatOnDropBrainrot or false, function(autoBatOnDropBrainrot)
      Config.autoBatOnDropBrainrot = autoBatOnDropBrainrot
      saveConfig()
    end)

    Combat:Toggle("TP Bat on Drop Brainrot", Config.tpBatOnDropBrainrot or false, function(tpBatOnDropBrainrot)
      Config.tpBatOnDropBrainrot = tpBatOnDropBrainrot
      saveConfig()
    end)

    Combat:Section("TELEPORTS", "Quick vertical descent and automatic ground slamming")

    Combat:Toggle("Auto TP Down", Config.autoTpDown or false, function(arg)
      fn47(arg)
    end)

    Combat:Slider("Studs", 5, 100, Config.autoTpDownHeight or 15, function(autoTpDownHeight)
      Config.autoTpDownHeight = autoTpDownHeight
      saveConfig()
    end)

    Combat:Keybind("TP Down Key", Keybinds.tpDown, function(tpDown)
      Keybinds.tpDown = tpDown
      saveConfig()
    end)

    Combat:Section("DEFENSE", "Full godmode anti die, auto safe mode, body tracking, anti ragdoll and instant recovery")

    Combat:Keybind("Drop Brainrot", Keybinds.dropBrainrot, function(dropBrainrot)
      Keybinds.dropBrainrot = dropBrainrot
      saveConfig()
    end)

    Combat:Toggle("Anti Die", Config.antiDieEnabled or false, function(arg)
      fn59(arg)
    end)

    bodyLockToggleRef = Combat:Toggle("Body Lock", Config.bodyLockEnabled, function(arg)
      fn37(arg)
    end)

    Combat:Slider("Body Lock Range", 10, 200, Config.bodyLockRange or 50, function(bodyLockRange)
      Config.bodyLockRange = bodyLockRange
      saveConfig()
    end)

    Combat:Toggle("Anti Ragdoll", Config.antiRagdollEnabled, function(arg)
      fn48(arg)
    end)

    Combat:Toggle("Medusa Counter", Config.medusaCounterEnabled, function(arg)
      fn36(arg)
    end)

    local v90 = nil

    v90 = Combat:Toggle("Bat Counter", Config.batCounterEnabled, function(batCounterEnabled)
      if batCounterEnabled and Config.circleEnabled then
        v90.setState(false)
        v88:Notify("Bat Counter", "Disable Auto Bat first.", 3)
        return
      end

      Config.batCounterEnabled = batCounterEnabled

      if batCounterEnabled then
        fn57()
      else
        fn58()
      end

      saveConfig()
    end)

    Combat:Toggle("Show Player Speeds", Config.playerSpeedEnabled, function(arg)
      fn51(arg)
      saveConfig()
    end)

    Combat:Keybind("Insta Reset", Keybinds.instaReset, function(instaReset)
      Keybinds.instaReset = instaReset
      saveConfig()
    end)

    local Settings = v88:Tab("Settings", "Display, performance, mobile and UI configuration")
    Settings:Section("OUTFIT & ANIMATIONS", "Animation packs and character movement styles")

    local tbl29 = {
      "OFF",
      "Zombie",
      "Ninja",
      "Knight",
      "Elder",
      "Levitate",
      "Astronaut",
      "Pirate",
      "Toy",
      "Vampire",
      "Werewolf",
      "Rthro",
      "Stylish",
      "Hit Harder",
      "Crazy",
      "Unwalk",
    }

    local v91 = Settings
    local dropdown2 = v91.Dropdown

    local function fn70(currentAnimPack)
      fn49(currentAnimPack)
      Config.currentAnimPack = currentAnimPack
      saveConfig()
    end

    dropdown2(v91, "Animation Pack", tbl29, fn70, Config.currentAnimPack or "OFF")
    Settings:Section("DISPLAY & PERFORMANCE", "Camera view, stretched resolution and anti-lag optimization")

    Settings:Slider("FOV", 80, 120, Config.fov or 80, function(arg)
      fn62(arg)
    end)

    Settings:Slider("Stretch Rez", 0.1, 1, Config.stretchRez or 1, function(arg)
      fn63(arg)
    end, 2)

    Settings:Toggle("FPS Boost (Anti-Lag)", Config.fpsBoostEnabled or false, function(arg)
      Config._setFpsBoost(arg, true)

      if v88.particles and v88.particles.layer then
        v88.particles.layer.Visible = not arg
      end

      saveConfig()
    end)

    Settings:Section("FLOATING BUTTONS SETTINGS", "Global scaling, locking and visibility")

    Settings:Toggle("Show All Side Buttons", Config.floatingBtnsVisible, function(floatingBtnsVisible)
      v88:SetSideBarVisible(floatingBtnsVisible)
      Config.floatingBtnsVisible = floatingBtnsVisible
      saveConfig()
    end)

    Settings:Toggle("Lock Side Buttons", Config.lockSideButtons or false, function(lockSideButtons)
      v88:SetSideBarLocked(lockSideButtons)

      Config.lockSideButtons = lockSideButtons
      saveConfig()
    end)

    Settings:Stepper("Side Buttons Size (%)", 60, 160, 10, math.floor((Config.buttonScale or 1) * 100), function(arg)
      Config.buttonScale = arg / 100
      v88:SetSideBarScale(Config.buttonScale)
      saveConfig()
    end)

    Settings:Button("Reset Button Positions", function()
      v88:ResetSideButtons()
      Config.sideBtnPositions = {}
      saveConfig()
    end)

    carry = v88:SideButton("CARRY", function(speedToggled)
      Config.speedToggled = speedToggled
      local setState = nil

      if v85 then
        setState = v85.setState
      end

      if setState then
        pcall(function()
          v85.setState(speedToggled)
        end)
      end

      saveConfig()
    end, true)

    carry.setState(Config.speedToggled)

    lagger = v88:SideButton("LAGGER", function(arg)
      fn42(arg and "Lagger" or "Normal")
    end, true)

    lagger.setState(Config.speedProfile == "Lagger")

    custom = v88:SideButton("CUSTOM", function(arg)
      fn42(arg and "Custom" or "Normal")
    end, true)

    custom.setState(Config.speedProfile == "Custom")

    autoPlayButton = v88:SideButton("AUTO PLAY", function()
      fn46()
      autoPlayButton.setState(tbl23.active)
    end, true)

    autoPlayButton.setState(false)

    v88:SideButton("TP DOWN", function()
      fn40()
    end, false)

    v88:SideButton("DROP", function()
      fn50()
    end, false)

    v87 = v88:SideButton("AUTO BAT", function(arg)
      fn32(arg)
    end, true)

    v87.setState(Config.circleEnabled)

    local function fn71(arg)
      fn33(arg)
    end

    tpBatButton = v88:SideButton("TP BAT", fn71, true)
    tpBatButton.setState(Config.tpBatEnabled)

    v88:SideButton("RESET", function()
      fn38()
    end, false)

    v88:SetSideBarVisible(Config.floatingBtnsVisible)

    pcall(function()
      v88:SetSideButtonPositions(Config.sideBtnPositions)
    end)

    v88:OnSideButtonMoved(function()
      Config.sideBtnPositions = v88:GetSideButtonPositions()
      saveConfig()
    end)

    if Config.sideBtnVisibility and type(Config.sideBtnVisibility) == "table" then
      for k, v92 in pairs(Config.sideBtnVisibility) do
        pcall(function()
          v88:SetSideButtonVisible(k, v92)
        end)
      end
    end

    v88:FinalizeBuild()

    if Config.fpsBoostEnabled and Config._setFpsBoost then
      task.defer(function()
        pcall(function()
          Config._setFpsBoost(true, true)

          if v88 and v88.particles and v88.particles.layer then
            v88.particles.layer.Visible = false
          end
        end)
      end)
    end

    pcall(function()
      Config.phoneScale = UserInputService.TouchEnabled and not UserInputService.MouseEnabled and 0.85 or 1
      v88:SetScale(Config.phoneScale)
      saveConfig()
    end)

    pcall(function()
      v88:SetImageTransparency(1 - (Config.guiImageVis or 85) / 100)
    end)

    pcall(function()
      if Config.laggerCarryEnabled then
        setLaggerCarry(true)
      end
    end)

    pcall(function()
      if Config.autoTpDown then
        fn47(true)
      end
    end)

    pcall(function()
      if Config.autoGrabEnabled then
        fn39(true)
      end
    end)

    pcall(function()
      if Config.autoHitEnabled then
        Config._setAutoHit(true)
      end
    end)

    pcall(function()
      if Config.safeModeEnabled then
        fn60(true)
      end
    end)

    pcall(function()
      fn61(true)
    end)

    pcall(function()
      if Config.bodyLockEnabled then
        fn37(true)
      end
    end)

    pcall(function()
      if Config.antiRagdollEnabled then
        fn48(true)
      end
    end)

    pcall(function()
      if Config.currentAnimPack and Config.currentAnimPack ~= "OFF" and Config.currentAnimPack ~= "Off" then
        fn49(Config.currentAnimPack)
      end
    end)

    pcall(function()
      if Config.playerSpeedEnabled then
        fn51(true)
      end
    end)

    pcall(function()
      if Config.ragTimerEnabled then
        fn52()
      end
    end)

    pcall(function()
      if Config.medusaCounterEnabled then
        fn36(true)
      end
    end)

    pcall(function()
      if Config.batCounterEnabled then
        fn57()
      end
    end)

    pcall(function()
      if Config.autoEquipBat then
        equipBat()
      end
    end)

    pcall(function()
      if Config.infJumpEnabled then
        fn35(true)
      end
    end)

    pcall(fn64)

    if Config.guiPosition and v88 and v88.main then
      pcall(function()
        v88.main.Position = UDim2.new(
          Config.guiPosition.xScale or 0.5,
          Config.guiPosition.xOffset or 0,
          Config.guiPosition.yScale or 0.5,
          Config.guiPosition.yOffset or 0
        )
      end)
    end
  end

  index._startUI()
end
