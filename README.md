# structure.sk
Structure block API for Skript

### requires:
*   skript-mirror: https://github.com/btk5h/skript-mirror/releases
*   StructureBlockLib: https://github.com/Shynixn/StructureBlockLib/releases
*   spigot: versions 1.9.0 - 1.12.0, note that it does NOT work on versions > 1.12.0

### effects
```
   load structure of %block%
   load structure %string% from [author] %string% at %location% rotated by %number%, mirrored %string% and ignoring entities %boolean%
   save structure of %block%
   save structure %string% from [author] %string% between %location% and %location%
   set structure corners of %block% to %location% and %location%
```
### expressions
```
   structure author of %block% -> %string%
   structure meta data of %block% -> %string%
   structure integrity of %block% -> %number%
   structure mirror type of %block% -> %string%
   structure rotation of %block% -> %number%
   structure name of %block% -> %string%
   structure seed of %block% -> %number%
   structure [(1¦x|2¦y|3¦z)][-]size of %block% -> %number% or %vector% if x/y/z is omitted
   structure relative (1¦location|2¦vector) of %block% -> %location% or %vector%
   structure (1¦min|2¦max)[imum] location of %block% -> %location%
   structure mode of %block% -> %string%
   structure bounding box of %block% is visible -> %boolean%
   structure of %block% ignores entities -> %boolean%
   structure of %block% shows invisible blocks -> %boolean%
```
### comments about rotations:
*   the rotation is always either 0, 90, 180 or 270
*   rotations that are smaller than 0 or bigger than 360 are increased / decreased by mutliples of 360 until they are between 0-360
*   rotations that do not match one of the given options are rounded to the closest multiple of 90
*   if the final value is 360 it will be set to 0
*   increasing the rotation rotates the structure clockwise
*   decreasing the rotation rotates the structure anti-clockwise
### comment about mirroring:
*   possible values are: "NONE", "LEFT_RIGHT" and "FRONT_BACK"
