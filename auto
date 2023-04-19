h:AddToggle(
    {
        Name = "Autofarm",
        Default = false,
        Flag = "KeyToginuogle",
        Save = true,
        Callback = function(w)
            AutoFarm = w
            game:GetService("RunService").Stepped:connect(
                function()
                    if AutoFarm then
                        game.Players.LocalPlayer.Character:WaitForChild("Humanoid"):ChangeState(11)
                    end
                end
            )
            local x = 12
            local o = game:GetService("Players").LocalPlayer
            local function y()
                local Closest, Distance = nil, 99999
                for v, u in pairs(game.Workspace.BossFolder:GetChildren()) do
                    if u:FindFirstChild("Head") ~= nil then
                        local z =
                            (game:GetService("Players").LocalPlayer.Character.Head.Position - u.Head.Position).magnitude
                        if z < Distance then
                            Distance = z
                            Closest = u
                        end
                    end
                end
                for v, u in pairs(game.Workspace.enemies:GetChildren()) do
                    if u:FindFirstChild("Head") ~= nil then
                        local z = (game.Players.LocalPlayer.Character.Head.Position - u.Head.Position).magnitude
                        if z < Distance then
                            Distance = z
                            Closest = u
                        end
                    end
                end
                return Closest
            end
            OOO = nil
            game:GetService("RunService").RenderStepped:Connect(
                function()
                    if AutoFarm then
                        local A = y()
                        if A ~= nil then
                            game:GetService("Workspace").CurrentCamera.CFrame =
                                CFrame.new(game:GetService("Workspace").CurrentCamera.CFrame.p, A.Head.Position)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =
                                A.HumanoidRootPart.CFrame * CFrame.new(0, x, 9)
                            OOO = A
                        end
                    end
                end
            )
            spawn(
                function()
                    while AutoFarm and wait() do
                        c()
                        game.Players.LocalPlayer.Character.HumanoidRootPart.Velocity = Vector3.new(0, 0, 0)
                        game.Players.LocalPlayer.Character.Torso.Velocity = Vector3.new(0, 0, 0)
                    end
                end
            )
            while AutoFarm do
                wait()
                if
                    OOO ~= nil and OOO:FindFirstChild("Head") and
                        game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool")
                 then
                    local A = OOO
                    game.ReplicatedStorage.Gun:FireServer(
                        {
                            ["Normal"] = Vector3.new(0, 0, 0),
                            ["Direction"] = A.Head.Position,
                            ["Name"] = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name,
                            ["Hit"] = A.Head,
                            ["Origin"] = A.Head.Position,
                            ["Pos"] = A.Head.Position
                        }
                    )
                    wait()
                end
            end
        end
    }
)
