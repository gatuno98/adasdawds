-- Função para desenhar o nome de um jogador na tela
function DrawName(player)
    local screenPos = WorldToScreen(player.position) -- Converter posição do jogador para coordenadas da tela

    if screenPos then
        -- Configurações de estilo do texto
        local font = Drawing.Fonts.PermanentMarker
        local textSize = 15
        local textColor = Color3.fromRGB(255, 255, 255)  -- Branco

        -- Desenhando o nome do jogador
        Drawing.Text(screenPos.x, screenPos.y, player.name, font, textSize, textColor)
    end
end

-- Exemplo de jogadores fictícios
local players = {
    {name = "Jogador1", position = Vector3.new(10, 5, 10)},
    {name = "Jogador2", position = Vector3.new(15, 5, 15)},
    {name = "Jogador3", position = Vector3.new(20, 5, 20)},
}

-- Loop para desenhar o nome de todos os jogadores
while true do
    for _, player in ipairs(players) do
        DrawName(player)
    end
    wait(0.1)  -- Atualiza a cada 0.1 segundos
end
