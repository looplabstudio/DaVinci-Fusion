# DaVinci Resolve Fusion: Node Dimensions

How to get the dimensions of a Fusion node.

```lua
-- Node Pixel Width
Node_Name.Output.Width
Text.Output.Width

-- Node Pixel Height
Node_Name.Output.Height

-- Node Left Edge
Node_Name.Output.DataWindow[1]

-- Node Right Edge
Node_Name.Output.DataWindow[3]

-- Node Top Edge
Node_Name.Output.DataWindow[4]

-- Node Bottom Edge
Node_Name.Output.DataWindow[2]

-- Node Width Normalized
((Node_Name.Output.DataWindow[3] - Node_Name.Output.DataWindow[1]) / Node_Name.Output.Width)

-- Node Height Normalized
((Node_Name.Output.DataWindow[4] - Node_Name.Output.DataWindow[2]) / Node_Name.Output.Height)

```

