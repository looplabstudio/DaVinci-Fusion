# Fusion Macro Reference: Fusion Composition Frames

A quick grab for dynamically getting Fusion composition frames information. 

## Documentation

```lua
-- Frame Rate (60)
Tool_Name.Proj_FPS

  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Rate\")", 

-- Time (frames) converted to seconds.
Tool_Name.Norm_Time

  (time / Proj_FPS)

-- Normalized duration of 1 frame.
Tool_Name.Frame_Norm_Duration

  (1 / Proj_FPS)

-- Total frames available for animation.
-- Equals comp duration minus 1 frame.
-- This is perfect for having a 1-frame
-- buffer after outro animation.
Tool_Name.Available_Frames

  comp.RenderEnd

```

## Inputs

```lua
-- Inputs Comp_Frames
Proj_FPS = Input { 
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Rate\")", 
},
Norm_Time = Input {
  Expression = "(time / Proj_FPS)",
},				
Frame_Norm_Duration = Input { 
  Expression = "(1 / Proj_FPS)", 
},		
Available_Frames = Input { 
  Expression = "comp.RenderEnd", 
},

```

## UserControls

```lua
Comp_Frames = {
  LINKS_Name = "Comp_Frames",
  LBLC_NumInputs = 4,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Proj_FPS = {
  LINKS_Name = "Proj_FPS",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Norm_Time = {
  LINKS_Name = "Norm_Time",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Frame_Norm_Duration = {
  LINKS_Name = "Frame_Norm_Duration",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Available_Frames = {
  LINKS_Name = "Available_Frames",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},

```
