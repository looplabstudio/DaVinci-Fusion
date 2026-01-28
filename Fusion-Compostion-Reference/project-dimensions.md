# Fusion Macro Reference: Project Dimensions

A quick grab for dynamically getting DaVinci Resolve project dimensions. 

## Documentation

```lua
-- Screen width as pixels
Tool_Name.Proj_Px_Width

  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Width\")",

-- Screen height as pixels
Tool_Name.Proj_Px_Height

  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Height\")",

-- Aspect Ratio (16:9 = 1.777778)
Tool_Name.Proj_Aspect

  (Proj_Px_Width / Proj_Px_Height)

-- Inverse Aspect Ration (16:9 = 0.5625)
Tool_Name.Proj_Aspect_Inv

  (1 / Proj_Aspect)

```

## Inputs

```lua
-- Inputs Proj_Dimensions
Proj_Px_Width = Input {
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Width\")",
},
Proj_Px_Height = Input {
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Height\")",
},
Proj_Aspect = Input { 
  Expression = "(Proj_Px_Width / Proj_Px_Height)", 
},
Proj_Aspect_Inv = Input { 
  Expression = "(1 / Proj_Aspect)", 
},
```

## UserControls

```lua
-- User Controls
Proj_Dimensions = {
  LINKS_Name = "Proj_Dimensions",
  LBLC_NumInputs = 4,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Proj_Px_Width = {
  LINKS_Name = "Proj_Px_Width",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Proj_Px_Height = {
  LINKS_Name = "Proj_Px_Height",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Proj_Aspect = {
  LINKS_Name = "Proj_Aspect",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Proj_Aspect_Inv = {
  LINKS_Name = "Proj_Aspect_Inv",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
```
