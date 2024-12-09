-- Script de Teleportação
-- Coloque esse script dentro de uma parte que o jogador irá tocar

local teleportPart = script.Parent -- Parte que vai ser tocada
local teleportDestination = workspace.TeleportDestination -- A parte de destino onde o jogador será teleportado

-- Função que será chamada quando um jogador tocar a parte
local function onTouched(hit)
    local character = hit.Parent -- Verifica se o objeto tocado é parte de um personagem
    local humanoid = character:FindFirstChildOfClass("Humanoid") -- Verifica se é um jogador

    if humanoid then
        -- Teleporta o jogador para a parte de destino
        character:SetPrimaryPartCFrame(teleportDestination.CFrame)
    end
end

-- Conecta a função ao evento de toque da parte
teleportPart.Touched:Connect(onTouched)
