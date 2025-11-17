-- Variable global para guardar la posición
_G.posicionGuardada = nil

-- Función TP1: guardar la posición actual del jugador
function TP1()
    local jugador = game.Players.LocalPlayer
    if jugador and jugador.Character and jugador.Character:FindFirstChild("HumanoidRootPart") then
        _G.posicionGuardada = jugador.Character.HumanoidRootPart.Position
        print("Posición guardada:", _G.posicionGuardada)
    else
        print("No se pudo guardar la posición")
    end
end

-- Función TP2: teletransportarse a la posición guardada
function TP2()
    local jugador = game.Players.LocalPlayer
    if _G.posicionGuardada and jugador and jugador.Character and jugador.Character:FindFirstChild("HumanoidRootPart") then
        jugador.Character.HumanoidRootPart.CFrame = CFrame.new(_G.posicionGuardada)
        print("Teletransportado a la posición guardada")
    else
        print("No hay posición guardada o el personaje no está listo")
    end
end
