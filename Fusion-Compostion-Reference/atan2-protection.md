# DeVinci Resolve Fusion: atan2 Protection

How to protect Fusion from silent fails when using `math.atan2()`


## What is it? 

`math.atan2()` is a function that calculates the angle (in radians) from the positive x-axis to a point (x, y).

```
angle = math.atan2(y, x)

```

## When and how to protect it?

In procedural animation, it's common that the `x` and `y` fed to `atan2` are themselves calculations - often deltas or tangents as seen below. 

When both `x` and `y` are zero, `atan2` is technically undefined, which Fusion interprets as zero.

We need to protect against edge cases where both `x` and `y` could both be zero, but 0 degrees is the wrong calculation. 

```lua
-- Some tangent calculations
Tool_Spiral_C.Tangent_X
Tool_Spiral_C.Tangent_Y

-- Converted to degrees
Tool_Spiral_C.Road_Angle

  math.deg(math.atan2(Tangent_Y, Tangent_X)) 

-- And protected with a non-zero fallback angle
Tool_PAC.Road_Lock 

  (Tangent_X == 0 and Tangent_Y == 0) and 90 or Road_Angle

```

