# Tiutiuxit
-- Auto Piano Player v1.1

local VirtualInputManager = game:GetService("VirtualInputManager")

-- Função pra pressionar tecla
local function pressKey(key)
    VirtualInputManager:SendKeyEvent(true, key, false, game)
    task.wait(0.05)
    VirtualInputManager:SendKeyEvent(false, key, false, game)
end

-- Função pra tocar música
local function playSong(song, speed)
    speed = speed or 0.1
    for i = 1, #song do
        local note = song:sub(i, i)
        
        if note ~= " " then
            pressKey(note)
        end
        
        task.wait(speed)
    end
end

-- 🎵 Lista de músicas
local songs = {

    ["RushE"] = "tyu tyu tyu ytr ety uyt ryu", -- exemplo simplificado
    
    ["GoldenBrown"] = "q w e r t y u y t r e w q", -- exemplo
    
    ["FurElise"] = "e d# e d# e b d c a"
}

-- Escolher música
local selectedSong = "RushE"

-- Tocar
playSong(songs[selectedSong], 0.08)
