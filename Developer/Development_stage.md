# Development Stages

Development build IDs are prereleases of the intended release version. The `dev.N` value advances with each development build, regardless of the size of the change. The Minecraft version and loader are recorded as build metadata. Original build IDs are retained for traceability.

## 1.0.0-dev.1+mc1.21.11.fabric

Original build ID: `dev.1.0.0+mc1.21.11.fabric`

### Added mods

| Performance | Quality of Life (QoL) | Misc / Libraries |
| :--- | :--- | :--- |
| BadOptimizations | AppleSkin | Continuity |
| Clumps | BactroMod | ukulib |
| Iris Shaders | Better Tab | YetAnotherConfigLib (YACL) |
| Sodium Extra | BetterF3 | |
| Stfu | Controlling | |
| | Durability Plus | |
| | Searchables | |
| | Shulker Box Tooltip | |
| | uku's Armor HUD | |
| | Zoomify | |

### Purpose

To make the foundation to what Citron will be built off from.

---

## 1.0.0-dev.2+mc1.21.11.fabric

Original build ID: `dev.1.1.0+mc1.21.11.fabric`

### Added mods

- [Status Effect Timer](https://modrinth.com/mod/statuseffecttimer)

#### Purpose

Improve utility and UX

---

## 1.0.0-dev.3+mc1.21.11.fabric

Original build ID: `dev.1.2.0+mc1.21.11.fabric`

### Added mods

- [Mouse Tweaks](https://modrinth.com/mod/mouse-tweaks)
- [Lamp Dynamic Lights](https://modrinth.com/mod/lambdynamiclights)

#### Purpose

Improve utility and UX

---

## 1.0.0-dev.4+mc1.21.11.fabric

Original build ID: `dev.2.0.0+mc1.21.11.fabric`

### Added mods

- [Simple Menu](https://modrinth.com/mod/simple-menu)

### Purpose

Introduce a menu for the main page

### Notes

- Menu and background used were great but the buttons kept colliding and interfering with the background, making it look obstructed
- It's better to change the mod for the menu

---

## 1.0.0-dev.5+mc1.21.11.fabric

Original build ID: `dev.2.1.0+mc1.21.11.fabric`

### Mod changes

| Mod | Purpose | Action |
| :--- | :--- | :--- |
| Simple Menu | Menu | Removed |
| Fancy Menu | Menu | Added |
| Konkrete | Library | Added |
| Melody | Library | Added |

#### Purpose

Improvement carried forward

### Notes

- Uses custom button arrangements to make the menu look better

---

## 1.0.0-dev.6+mc1.21.11.fabric

Original build ID: `dev.2.2.0+mc1.21.11.fabric`

#### Purpose

Main menu UI improvement

### Notes

- Added an "Extra Mods" button to include all the custom mods users may add that I haven't accounted for

---

## 1.0.0-dev.7+mc1.21.11.fabric

Original build ID: `dev.2.3.0+mc1.21.11.fabric`

#### Purpose

Main menu UI improvement

### Notes

- Added a "Citron Menu" button to the default menu to allow users to switch back to Citron's custom menu
- Added custom button textures to Citron's main menu
- Removed the "Extra Mods" button and added a "Default Menu" button that reverts back to Minecraft's default menu

---

## 1.0.0-dev.8+mc1.21.11.fabric

#### Purpose

Main menu UI improvement

### Notes

- Changed the Citron menu from a title screen to a GUI in FancyMenu
- Kept the existing settings and elements, but removed the Accessibility and Language buttons from the Citron menu
- Adjusted the position of the button stack on the right side to give the elements more space
- Buttons added by other mods now appear on the default menu instead of the Citron menu, preserving the custom menu's layout
- Removed the Citron version note from the default menu; it remains on the Citron menu
