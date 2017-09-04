# Preferences.sublime-settings

```
{
```

## MiniMap

It's always on.

I never use it though. Maybe I should turn it off?

```
	"always_show_minimap_viewport": true,
```

## Bold Folder Labels

Making them bold makes it easier to differentiate.

```
	"bold_folder_labels": true,
```

## Easily identify tabs for files with changes

This works different in different themes. It's helpful in the default theme,
minimally, and may be helpful in other themes.

```
	"highlight_modified_tabs": true,
```

If you are using Sublime Linter and you switch color schemes the linter plugin will analyze your scheme and likely create a modified copy of it.

See here: http://www.sublimelinter.com/en/latest/usage.html#choosing-color-schemes

```
	"color_scheme": "Packages/User/SublimeLinter/base16-ocean.dark (SL).tmTheme",
```

## Always End with a Newline

```
	"ensure_newline_at_eof_on_save": true,
```

## Folders That Should Not Be Searched

```
	"folder_exclude_patterns":
	[
		".svn",
		".git",
		".hg",
		"CVS",
		"node_modules"
	],
```

## Font Options.. Not Sure What These Do

```
	"font_options":
	[
		"gray_antialias"
	],
```

## Font Size

I change this all the time with `CTRL++` and `CTRL+-`.

```
	"font_size": 22,
```

## Not Sure What This Is

..Or how it got here.

```
	"ignored_packages":
	[
		"Vintage"
	],
```

## Indent Guidelines

I should put a picture here. These help you understand indentation.

```
	"indent_guide_options":
	[
		"draw_normal",
		"draw_active"
	],
```

## Line Padding

I don't know what any of these are.

I think they came from [Tristan Hume's Config][thume-config].

[thume-config]: https://gist.github.com/trishume/1427df16f57e65dba9670539410abdb5

While Tristan's name has come up-- he's got some good stuff:

* http://thume.ca/2016/12/03/disassembling-sublime-text/

Ahh-- looks like much of this stuff comes from [these Materialize suggestions][materialize-suggestion].

[materialize-suggestion]: https://github.com/saadq/Materialize/blob/master/messages/install.txt#L42-L52



```
	"line_padding_bottom": 3,
	"line_padding_top": 3,
	"overlay_scroll_bars": "enabled",
	"spacegray_fileicons": true,
	"spacegray_sidebar_font_large": true,
```

## Tab Size

I like 2 *space* indent.

```
	"tab_size": 2,
	"translate_tabs_to_spaces": true,
```

## Theme

In Sublime, a "theme" is a thing that impactsdasda the sidebar, your tabs, and the window that pops up at the bottom when finding and replacing, for example.

This is different from a "color_scheme."

```
	"theme": "Material Spacegray Light.sublime-theme",
```

## No Trailing Space

```
	"trim_trailing_white_space_on_save": true
```

```
}
```
