# colorbuddy.vim

## Benefits

Live changing of colors (and inherited colors!)

![changing_colors](./example/demos/_simple.svg)

## Example

Your color buddy for making cool neovim color schemes. Write your colorscheme in lua!

Example:

```lua
local Color = require('colorbuddy.init').Color
local colors = require('colorbuddy.init').colors

local Group = require('colorbuddy.init').Group
local groups = require('colorbuddy.init').groups

local styles = require('colorbuddy.init').styles

Color.new('red', '#cc6666')
Color.new('green', '#99cc99')
Color.new('yellow', '#f0c674')
Color.new('background', '#1d1f21')

Group.new('Function', colors.yellow, colors.background, styles.bold)
Group.new('mFunction', groups.Function, groups.Function, groups.Function)

-- If you want multiple styles, just add them!
Group.new('italicBoldFunction', groups.Function, colors.background, styles.bold + styles.italic)

-- If you want the same style as a different group, but without a style
-- just subtract it!
Group.new('boldFunction', colors.yellow, colors.background, groups.italicBoldFunction - styles.italic)
```

## TODO:
- [ ] Highlight links
- [ ] Highlight defaults
