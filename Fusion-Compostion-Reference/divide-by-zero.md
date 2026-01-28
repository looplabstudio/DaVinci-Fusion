# DaVinci Resolve Fusion: Divide by Zero and Nill Protection

How to protect Fusion from silent fails when using division in expressions.

```lua
-- Instead of this:
Value / 2
-- Use this:
Value * 0.5

-- If Value_B is guaranteed to be a number,
-- you can use max() to ensure a small but
-- visually insignificant divisor exists. 
Value_A / max(0.001, Value_B)

Motion.Factor_X_Calc = (Start_Scale_X ~= 0) and (End_Scale_X / Start_Scale_X) or 1
Motion.Factor_Y_Calc = (Start_Scale_Y ~= 0) and (End_Scale_Y / Start_Scale_Y) or 1

```
