# Vainilla-theme
Modded snippets for my personal Obsidian theme.

<img src="/Screenshots/light-mode.png" width="49%"> <img src="/Screenshots/dark-mode.png" width="49%">


## All my snippets mods are adjusted so they can work with the [California Coast Theme](https://github.com/mgmeyers/obsidian-california-coast-theme)
- The same accent color selected for the California Coast Theme is used for the colors of some of the snippets.

### Vainilla Theme Settings
<img src="/Screenshots/vainille.png" width="49%" float="left">

It works using the [Style Settings Plugin](https://github.com/mgmeyers/obsidian-style-settings).
With it, is posible to define:
- A different font family for the editor.
- Headers (and H6) preview font family
- Change the UI font size.
- General text-align.
#### EDITOR settings:
- Choose between the accent, mute and normal color for the markdown rendering color (`**`,`__`, `[[]]`) and footnotes.
- The font-family and font-style for the `[Text in brackets]`, the code font-family, the inline font-style and the code color.
#### PREVIEW settings:
- Change the font-family, font-style and font-decoration of internal links, external links, code and tags.
<img src="/Screenshots/Editor-light.png" width="75%">

<img src="/Screenshots/editor-dark.png" width="75%"> 

#### MERMAID settings:
- Change the mermaid font-family, font-color and node stroke, node stroke width and the fill-color of the nodes.
- Select the mermaid scale.
<img src="/Screenshots/mermaid.png" width="49%">


## Vainilla Theme (snippets)
This is where I made some visual changes.
1. I changed the background and foreground color, based in the [Material Ocean](https://github.com/material-ocean) color scheme.
```
  :root{
	--color-black-rgb: 15, 17, 26;
	--color-white-rgb: 229,233,240;
}
```
2. I added some variables to work with shades of the accent color.
```
.theme-light,
.theme-dark {
    --accent-90: hsla(var(--accent-hsl), 0.9);
    --accent-80: hsla(var(--accent-hsl), 0.8);
    --accent-70: hsla(var(--accent-hsl), 0.7);
    --accent-60: hsla(var(--accent-hsl), 0.6);
    --accent-50: hsla(var(--accent-hsl), 0.5);
    --accent-40: hsla(var(--accent-hsl), 0.4);
    --accent-30: hsla(var(--accent-hsl), 0.3);
    --accent-20: hsla(var(--accent-hsl), 0.2);
    --accent-10: hsla(var(--accent-hsl), 0.1);
    --accent-5: hsla(var(--accent-hsl), 0.05);
    --accent-3: hsla(var(--accent-hsl), 0.03);
    --accent-2: hsla(var(--accent-hsl), 0.02);
}
```
  
  #### Nav&tag pane
  mod from [ITS-Theme](https://github.com/SlRvb/Obsidian--ITS-Theme)
  <img src="/Screenshots/navpanel.png" width="49%">
  ##tags
  <img src="/Screenshots/tags.png" width="49%">
  tags have a bullet style. it doesn't affect the tag pane.
  
#### header lines

 Based on the horizontal gradient line in Preview [source](https://github.com/Dmitriy-Shulha/obsidian-css-snippets/blob/master/Snippets/Lines%20-%20horizontal.md), I also added lines before the headings.
 <img src="/Screenshots/header-preview.png" width="49%"> 

##### Quotes
I changed the quote style.
<img src="/Screenshots/quote.png" width="49%">



### Snippets
##### Admonition plus
[Admonition-extras](https://github.com/chetachiezikeuzor/Obsidian-Snippets/blob/main/Admonition%20Extras.css)
Mod style
<img src="/Screenshots/admonition-cite.png" width="49%">
<img src="/Screenshots/admonition-information.png" width="49%">

##### Aside blocks
 They modded from [ITS-Theme](https://github.com/SlRvb/Obsidian--ITS-Theme). This are an aside note and an inline aside note.
<img src="/Screenshots/aside.png" width="49%">
The aside hidden note shows when hovered. 
<img src="/Screenshots/aside-show.png" width="49%">
<img src="/Screenshots/aside-hidden.png" width="49%">

##### Bigger Preview
Bigger preview
  [Source](https://github.com/chetachiezikeuzor/Obsidian-Snippets#Bigger-Popovers)
  <img src="/Screenshots/Bigger-preview.png" width="49%">
  
##### Bullet Point Relationship Lines
   I moded it so it starts with the accent color. Also, I changed to a dotted line.
  [Point relationship lines - rainbow colors](https://forum.obsidian.md/t/meta-post-common-css-hacks/1978/334)
  
  <img src="/Screenshots/outliner-preview.png" width="49%"><img src="/Screenshots/outliner-edit.css.png" width="49%">
 
  ##### Checklist
  <img src="/Screenshots/checklist.png" width="49%"> <img src="/Screenshots/checklist-edit.png" width="49%">
  [Checkbox](https://github.com/deathau/obsidian-snippets/blob/main/checkbox.css) 
  I just changed some colors. 
  
  ##### Image flags
<img src="/Screenshots/image-flag.png" width="49%">
- Image Flags Snippet by [Lithou](http://github.com/lithou/sandbox)
- Almost no modifications.

##### Inline block embeds
Inline block embeds [here](https://github.com/deathau/obsidian-snippets/blob/main/inline-block-embeds.css)  
<img src="/Screenshots/inline.png" width="49%">

##### Org-sidian

Org-sidian bullets headings. [Source](https://github.com/santiyounger/Org-sidian-Bullets)
I changed some of the bullets.
<img src="/Screenshots/header-edit.png" width="49%">
  

##### Pretty highlights

<img src="/Screenshots/highlights_.png" width="49%"> 
- Original snippet [here](https://github.com/chetachiezikeuzor/Obsidian-Snippets#Pretty-Highlights).
- My modded version [here](): I added another marker, the aqua one. I added some colors based Material Ocean palette. [Here are some samples] of how almost all the color options look.
- Then, I added some color codes based on pastel highlighters.

##### Stylized buttons
[Buttons - stylized](https://github.com/Dmitriy-Shulha/obsidian-css-snippets/blob/master/Snippets/Buttons%20-%20stylized.md)
<img src="/Screenshots/Clear button.png" width="49%"> <img src="/Screenshots/Dark button.png" width="49%"> This + the native style settings in the buton plugin. Hover.

##### Tables
##### Tables
[Tables that look like latex tables](https://forum.obsidian.md/t/obsidian-tables-that-look-like-latex-tables-with-css/16683) Mod
<img src="/Screenshots/table-academia.png" width="49%">
[Tables invisibile cssclass](https://github.com/PurpleGuitar/obsidian-snippets/blob/main/tables-invisible-cssclass.css) Mod
<img src="/Screenshots/table-transparent.png" width="49%">
<img src="/Screenshots/table-default.png" width="49%">

##### VIM MODE
<img src="/Screenshots/Vim.png" width="49%">

Vim mode with line focus [Source](https://forum.obsidian.md/t/meta-post-common-css-hacks/1978/17) No mod.




#### Fonts:
  - UI font: Poppins Latin
  - Body Font: Atkinson Hyperlegible
  - body font features: Niramit
  - Monospace font: Victor Mono

### Plugin for Misc-Kustom snippet settings
  - 
####  Kustom fonts
  - Headers: Bondi
  - Editor font: Victor Mono
  - \[In brackets font]: Ticketing
  - Tag font: Unica One
  - Internal links: KG Hard Candy Striped
  - External links: Trochut
  - Mermaid font: Alegreya Sans SC

