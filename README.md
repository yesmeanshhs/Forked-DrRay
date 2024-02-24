# DrRay UI Library

Introducing the DrRay UI Library, a Roblox Exploit UI Library created just for fun! Feel free to modify it as you wish, and using our library has already helped us a lot! You can check out an example code [here](./Example.lua).

[Source Code](./DrRay.lua)

[Actual Source (Rbxm)](./ActualSource)

## Getting Started

To begin, you need to declare a variable to access the library.

```lua
local DrRayLibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/AZYsGithub/DrRay-UI-Library/main/DrRay.lua"))()
```

To load the UI, simply call the function:

```lua
local window = DrRayLibrary:Load("DrRay", "Default")
```

**Argument 1: Name of your UI (type: `string`)**

**Argument 2: The Image ID; setting it to "Default" will use the default UI Logo (type: `string`)**

## Implementing Features

We provide pre-made features for your convenience.

(yesmeanshhs message)
The UI library built-in features here isn't stated at all, so maybe stated in the code that the pre-made built-in features are making you aware of the real time (yes it shows up your clock, i made some adjustments to do so), and implementing your avatar profile in the UI library itself.

### Tab

You can create multiple tabs to organize your features.

```lua
local tab = DrRayLibrary.newTab("My Tab", "ImageIdHere")
```

**Argument 1: Name of your tab (type: `string`)**

**Argument 2: The Image ID (type: `string`)**

## Label (Added by editor because it is stated in the code)

Create labels for tabs easily!

```lua
tab.newLabel("This is a new label wow")
```

**Argument 1: The Selected Label Text (type: `string`)**

Update labels for your own importance

```lua
local Label
Label = tab.newLabel("This is a new label wow")
task.wait(1)
-- After 1 seconds it changes the label text into a new one
Label:Update("New Text Label!")
```

**Argument 1: The Selected New Text Label (type: `string`)**

### Button

Create functional buttons with ease!

```lua
tab.newButton("Button", "Prints Hello!", function()
    print('Hello!')
end)
```

**Argument 1: Name of the Button (type: `string`)**

**Argument 2: Description of the button (type: `string`)**

**Argument 3: Function to execute when the button is clicked (type: `function`)**

Update buttons for your own script!

```lua
local Button
Button = tab.newButton("Button", "Prints Hello!", function()
    print('Hello!')
end)
task.wait(3)
-- The button now can only be activated by code
-- It also changes the title of the button
Button:Update("New Button Name!",true)
```

**Variable definer: Defines the selected button you want to update through assigning with variables (type: `variable`)**

**Argument 1: New Name Of The Button (type: `string`)**

**Argument 2: Manual Activation (This makes the user can only activate the button through code) (type: `bool`)**

### Toggle

Use toggles that can be turned on or off.

```lua
-- default togglestate is false
tab.newToggle("Toggle", "Toggle! (prints the state)", function(toggleState)
    print("The state is"..tostring(toggleState))
end)
```

**Argument 1: Name (type: `string`)**

**Argument 2: Description (type: `string`)**

**Argument 3: Function to execute (return: `bool`) (type: `function`, function parameter: `custom`) (default state: `false`)**

*Yesmeanshhs Modificafion*

Updating a toggle state or title.

```lua
-- Create a variable that will define the toggle
local toggle
toggle = tab.newToggle("Toggle", "Toggle! (prints the state)", function(toggleState)
    print("The state is"..tostring(toggleState))
end)

task.wait(1)
-- The toggle is not able to be activated by the user now
-- Update the toggle with the assigned variable and custom function
toggle:Update(false,true,"Manual activation only title!")

task.wait(1)
-- Updating without changing the title
-- It is now able to be activated by the user
toggle:Update(true,false)
```

**Variable definer: Defines the selected toggle you want to update through assigning with variables (type: `variable`)**

**Argument 1: Desired State (type: `bool`)**

**Argument 2: Manual Activation (This makes the user can only activate the toggle through code) (type: `bool`)**

**Argument 3: Optional New Title (Optional) (type: `string` or none)**

### Input Text

Get input text from the user.

```lua
tab.newInput("Input", "Prints your input.", function(text)
    print("Entered text: " .. text)
end)
```

**Argument 1: Name/Title (type: `string`)**

**Argument 2: Description  (type: `string`)**

**Argument 3: Function to execute (type: `function`)**

## Dropdown

Create dropdown menus easily.

```lua
tab.newDropdown("SelectedDropdownName", "Select one of these options!", {"water", "dog", "air", "bb", "airplane", "wohhho", "yeay", "delete"}, function(selectedOption)
    print(selectedOption)
end)
```

**Argument 1: Name/Title (type: `string`)**

**Argument 2: Description  (type: `string`)**

**Argument 3: Table listing the options (type: `table`)**

**Argument 4: Function to execute, returns the selected option inside the table (return: table_value) (type: `function`)**

*Yesmeanshhs Modification*

Updating dropdown menus easily.

```lua
-- Define the selected dropdown by variable
local dropdown
dropdown = tab.newDropdown("SelectedDropdownName", "Select one of these options!", {"water", "dog", "air", "bb", "airplane", "wohhho", "yeay", "delete"}, function(selectedOption)
    print(selectedOption)
end)

task.wait(1)
-- Refresh the dropdown by calling the variable custom function
-- The dropdown buttons after 3 seconds is unable to be activated
dropdown:Refresh({"You cant activate this!"},true)
```

**Variable definer: Defines the selected dropdown you want to refresh through assigning with variables (type: `variable`)**

**Argument 1: Table listing the new options (type: `table`)**

**Argument 2: Manual Activation (This makes the user can only activate the dropdown buttons through code) (type: `bool`)**

### Keybind

Get user input when the keybind button is clicked.

```lua
tab.newKeybind("Input Key", "Press the key to start; it will be printed out.", function(key)
    print(key)
end)
```

**Argument 1: Name/Title (type: `string`)**

**Argument 2: Description  (type: `string`)**

**Argument 3: Function to execute (return: input) (type: `function`)**

### Slider

Add sliders, which work well for mobile users too!

```lua
tab.newSlider("Slider", "Epic slider", 1000, false, function(num)
    print(num)
end)
```

**Argument 1: Name/Title (type: `string`)**

**Argument 2: Description  (type: `string`)**

**Argument 3: Maximum value for the slider (type: `int`)**

**Argument 4: Set to `false` for now (type: `boolean`)**

**Argument 5: Function to execute (return: int) (type: `function`)**

Update sliders easily!

```lua
local Slider
Slider = tab.newSlider("Slider", "Epic slider", 1000, false, function(num)
    print(num)
end)
task.wait(3)
-- After 3 seconds the slider is only able to be activated by code
-- It is also making the title changed
Slider:Update("New Slider Name!",true)
```

**Variable definer: Defines the selected slider you want to update through assigning with variables (type: `variable`)**

**Argument 1: New Name For Slider (type: `string`)**

**Argument 2: Manual Activation (This makes the user can only activate the slider through code) (type: `bool`)**

## Built-in UI Features

We also provide features to toggle the UI, change the theme, and more.

### Toggle UI

To toggle the UI, use the following:

```lua
window:Toggle()
```

### Open UI

To open the UI, simply use:

```lua
window:Open()
```

### Close UI

To close the UI, you can use:

```lua
window:Close()
```

### Hide UI

To hide the UI, use:

```lua
window:Hide()
```

### Unhide/Show UI

To show the UI, use:

```lua
window:Show()
```

### Customize Theme

You can customize the theme colors with two accent colors.

```lua
local mainColor = Color3.fromRGB(10, 30, 10) -- Customize as you wish; these are in RGB format. (mainColor applies to main colors like background, buttons, etc.)

local secondColor = Color3.fromRGB(50, 50, 10) -- Secondary Color; applies to Toggle when activated and slider background.

window:SetTheme(mainColor, secondColor)
```

**Argument 1: Main Color, background, button color, etc. (type: `Color3`)**

**Argument 2: Secondary Color, toggle when activated, slider color background. (type: `Color3`)**

# Credit
This UI library made by **.chillz.** (Discord)
UI Library Modified by **yesmeanshhs**, we live on the same country.

[MIT License](./LICENSE)

Enjoy using the DrRay UI Library! 
Have fun.
