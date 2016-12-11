# Image-to-RBXLua
Converts images to a lua script that you can put into ROBLOX.


### Example output:
```LUA
local GUI_Element = nil
--TODO: Specify which GUI element to put it in.

local IMG_DATA = { --The data of the image.
	{
		Position = UDim2.new(0, 0, 0, 0);
		Size = UDim2.new(0, 1, 0, 1);
		Color = Color3.fromRGB(255, 0, 0);
		Transparency = 0;
	};
	{
		Position = UDim2.new(0, 0, 0, 1);
		Size = UDim2.new(0, 1, 0, 1);
		Color = Color3.fromRGB(0, 0, 255);
		Transparency = 0;
	};
	{
		Position = UDim2.new(0, 1, 0, 0);
		Size = UDim2.new(0, 1, 0, 1);
		Color = Color3.fromRGB(0, 255, 0);
		Transparency = 0;
	};
	{
		Position = UDim2.new(0, 1, 0, 1);
		Size = UDim2.new(0, 1, 0, 1);
		Color = Color3.fromRGB(255, 255, 255);
		Transparency = 0;
	};
}

function Draw()
	local ImgFr = Instance.new('Frame')
	ImgFr.Name = 'Frame'
	ImgFr.Size = UDim2.new(0, 2, 0, 2)
	ImgFr.BackgroundTransparency = 1
	ImgFr.Parent = GUI_Element
	for Index, Data in ipairs(IMG_DATA) do
		local Pos = Data.Position
		local Size = Data.Size
		local Color = Data.Color
		local Transparency = Data.Transparency
		local pixel = Instance.new('Frame')
		pixel.BorderSizePixel = 0
		pixel.Size = Size
		pixel.Position = Pos
		pixel.BackgroundColor3 = Color
		pixel.BackgroundTransparency = Transparency
		pixel.Parent = ImgFr
		
		if Index % 100 == 0 then
			game:GetService('RunService').Heartbeat:wait()
		end
	end
end

Draw()
```
