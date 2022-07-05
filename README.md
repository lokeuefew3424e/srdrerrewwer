local library = loadstring(game:HttpGet("https://pastebin.com/raw/RvJ0qewm", true))() --UI библиотека
local main = library:CreateWindow("RdxHacks") -- создаёт окно

function x10gun() -- функция ган мода
for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetDescendants()) do -- берёт все объекты из бекпака
	if v:IsA("LocalScript") and v.Parent.Name ~= "Phone" then --если это локал скрипт, и место где он находится не равно телефону, то
		for i = 1, 10 do -- повторяет 10 раз
		local a = v:Clone() --клонирует
		a.Parent = v.Parent --перемещает в папку с локал скриптом
	end
end
end
end

local Section = main:Section("OOF") --создаёт скцию с вашим текстом

local mod = main:Button("x10 Gun Mode", function() -- создаёт кнопку
x10gun()
end)
local Secion = main:Section("OOooooofF")--создаёт скцию с вашим текстом

local AAA = main:Button("x20 Gun Mode", function()-- создаёт кнопку
x10gun()
x10gun()
end)

local noclip = main:Toggle("noclip", {flag="noclipON"}) --создаёт флаг(noclipON) в нашем окне(main)
spawn(function()
while game:GetService("RunService").RenderStepped:wait() do--Начало цикла
	if main.flags.noclipON then--проверка включен ли флаг
		if game.Players.LocalPlayer.Character:FindFirstChild("Humanoid") then--есть ли хуманоид у персонажа
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)--убирает колизию у хуманоида
		end
	end
end
end)

local nocli = main:Toggle("noclip", {flag="noclipO"}) --создаёт флаг(noclipO) в нашем окне(main)
spawn(function()
while game:GetService("RunService").RenderStepped:wait() do --Начало цикла
	if main.flags.noclipO then --проверка включен ли флаг
		if game.Players.LocalPlayer.Character:FindFirstChild("Humanoid") then --есть ли хуманоид у персонажа
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11) --убирает колизию у хуманоида
		end
	end
end
end)

local hipheight = main:Slider("Hip Height", { --Создаёт ползунок в главном окне
min=0; --минимальное число которое можно будет выставить слайдером
max=100; --максимальное число которое можно будет выставить слайдером
flag="wawawadwafeagjege"},function(v) -- флаг можно написать любой, буква v будет хранить в себе число, которое мы выставили слайдером
game.Players.LocalPlayer.Character.Humanoid.HipHeight = v -- меняет высоту персонажа
end)
