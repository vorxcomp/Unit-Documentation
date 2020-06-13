# Unit Lua API Documentation
### Quick Navigation
[Reflection Functions](#Reflection-Functions)\
[Table Modification Functions](#Table-Modification-Functions)\
[Keyboard and Mouse Functions](#Keyboard-and-Mouse-Functions)\
[Hooking Functions](#Hooking-Functions)\
[Unit Library](#Unit-Library)

## Reflection Functions
```lua
<function> loadstring(<string> chunk)
```
Loads *chunk* as a lua script, and returns it if compiled successfully. If there's an error, the error message will be returned.

```lua
<bool> islclosure(<function> f)
```
Returns *true or false* based on if *f* is an LClosure.

## Table Modification Functions
```lua
<table, nil> getrawmetatable(<T> value)
```
Retrieve the metatable of value regardless of value's metatable's *\_\_metatable* field. Returns *nil* if it doesn't exist.

```lua
<void> makereadonly(<table> table)
```
Sets *table*'s read-only value to *true*.

```lua
<void> makewriteable(<table> table)
```
Sets *table*'s read-only value to *false*.

```lua
<bool> isreadonly(<table> table)
```
Returns *true or false* based off of *table*'s read-only condition.

## Environment Functions
```lua
<table> getgenv(<void>)
```
Returns the environment that is applied to each script executed.

```lua
<table> getrenv(<void>)
```
Returns the global environment for the LocalScript state.

```lua
<table> getreg(<void>)
```
Returns the Lua registry.

## Keyboard and Mouse Functions
```lua
<void> keypress(<int> keycode)
```
Simulates a key press for *keycode*. More information about keycodes can be found here: http://keycode.info/

```lua
<void> mouse1click(<void>)
```
Simulates a left mouse click.

```lua
<void> mouse1press(<void>)
```
Simulates a left mouse press without releasing.

```lua
<void> mouse1release(<void>)
```
Simulates a left mouse release.

```lua
<void> mouse2click(<void>)
```
Simulates a right mouse click.

```lua
<void> mouse2press(<void>)
```
Simulates a right mouse press without releasing.

```lua
<void> mouse2release(<void>)
```
Simulates a right mouse release.

```lua
<void> mousemoveabs(<int> x, <int> y)
```
Moves to cursor to the provided *x* and *y* coordinates.

```lua
<void> mousemoverel(<int> x, <int> y)
```
Moves to cursor to the provided *x* and *y* coordinates.

## Hooking Functions
```lua
<function> newcclosure(<function> f)
```
Pushes a new CClosure that uses function *f* upon calling.

## Unit Library
```lua
<function> setthreadcontext(<int> identity)
```
Sets Unit's identity to *identity*

```lua
<objects> game:GetObjects(<string> contenturl)
```
Returns an array of instances from the *contenturl*. For more information, visit the official roblox documentation; https://developer.roblox.com/en-us/api-reference/function/DataModel/GetObjects

```lua
<string> game:HttpGet(<string> url)
```
Returns content/text at *url*.

```lua
<string> game:HttpGetAsync(<string> url, <bool> cache)
```
Returns content/text at *url*, if *cache* is *true*, the request caches the response.

```lua
<void> setclipboard(<string> data)
```
Sets *data* to clipboard.

## Drawing Library
```lua
<drawable> DrawingLib.Create(<string> type)
```
Creates a new drawable object. *type* must be *"Circle"*, *"Line"*, *"Box"*, or *"Text"*.

```lua
<function> DrawingLib.Clear(<void>)
```
Clears the Drawing canvas.

### Drawable (Base Class)

```lua
<string> ClassName [readonly]
```
The type of drawable.

```lua 
<Vector2> Position
```
The position of the drawable. (0, 0) represents the top left corner of the screen.

```lua
<Color3> Color
```
The color of the drawable.

```lua
<boolean> Visible
```
The drawable's visibility.

```
<int> ZIndex
```
The drawable's layer. This integer can be 0 to 25. Drawables on higher layers render over drawables on lower layers.

```
<float> Transparency
```
A value from 0 to 1. A value of 1 meeans the drawable is transparent.

### Circle
