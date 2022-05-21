# 3dPPlaneDesign - 3D Printed Model Plane Non-destructive Blender Design Tools
   
V2.0.0 Blender 3.1 Version

Blender File Download : [3dpPlaneDesign_2_0_0.zip](https://github.com/nerk987/3dpPlaneDesign/releases/download/v2.0.0/3dpPlaneDesign_2_0_0.zip) 

Non-destructive 3D Printed Model Plane Design using Geometry Nodes (Blender 3.1 or higher)

Youtube Overview (For the Blend File, not the addon...):https://youtu.be/w0Qn-hiX6Dg

## Introduction
This is a blender file containing a number of design tools using Blender's Geometry Nodes.

## Installation
Download the zip file, and extract the 3dpPlaneDesignV2.blend file. Open it up and start designing a plane.

Alternatively you can append collections for a Wing, TailPlane, Fin, or Fuselage into your blend file. Or just use the Geometry Node Groups descibed below.

## Included Node Groups

### WingV2 - Design the shell of a wing
Uses curves to define the planform, twist, airfoil interpolation, and thickness. It can take two airfoil shapes as inputs, and has paramters to define the desired resolution.

Parameters:

Basic Resolution  
* Ribcount - The number of airfoil shaped edge loops in the main part of the wing.
* TipRibcount - The number of airfoil shaped edge loops in the tip of the wing.
* TipFraction - The fraction of the wing considered to be in the tip
* FoilCount - The number of vertices in each airfoil edge loop in the highest resolution

Guide Curves and airfoils
* Root - Airfoil at the root of the wing
* Tip - Airfoil at the tip of the wing
* Leading - Curve to guide the leading edge of the wing in both horizontal and vertical planes
* Trailing - Curve to determine the chord width of the wing along it's length
* TwistCurve - Curve to determine the amount of twist along the wing. The number of millimetres movement of the curve in the Z direction is taken as the degrees of downwash.
* TwistCentre - Curve to determine the axis of twist along the wing
* Interpolate - Curve to determine the interpolation between the root and the tip airfoil along the span of the wing.
* Thickness - Curve to determine any extra thickness in the wing. If altered, it will affect the chosen airfoil shape.

Material
* Material - Allows a choice of Blender's display material for the wing

Additional reolution parameters  
These parameters allow more control of the distribution and resolution of the wing vertex structure. It can be handy if the node group is applied, and the wing is manually joined into other structures.
* HiresTopPct - The percentage of the top part of the leading edge that will remin high resolution.
* HiresLowerPct - The percentage of the lower part of the leading edge that will remin high resolution.
* Reduction - If this parameter is greater than one, vertices on each airfoil edge loop will be reduced in this ratio except for the potions on the leading edge specified by the previous parameters, and immediate adjacent to the trailing edge. For example, if this paramter is '3', only one out of 3 vertices will be retained.

### FuseSection - Create a fuselage template using sections

This node group produces a simple fuselage shape using up to ten section shapes. Each of the section shapes are curves representing half of the fuselage sections at diffent locations. The section shapes can be relocated as objects as required to match a plan. It's the vertex/control point location relative to the origin that's important. The node group incudes a final subdivision surface node to allow smoothing.

The node group assumes that we are working in  millimetres, and that the nose of the fuselage is facing in the negative Y direction.

Parameters:

* Resolution - The number of vertices for each section, which controls the lateral resolution
* Sections - The number of sections to be used, between 2 and 10.
* SubD - Subdivision surface levels to be applied at the end
* Y_Tail/Z_Tail - The X and Z locations for the single tail vertex
* Sectionxx - The curve objects that define the section shapes
* Yxx - The Y location of the section.
* Y_Nose/Z_Nose - The X and Z locations for the single nose vertex

### Control Horn - Parametrically create a control horn

This node group creates a simple control horn

Parameters:

* Pad_x_mm - the width of the pad that glues to the control surface
* Pad_y_mm - the depth of the pad that glues to the control surface
* Thickness_mm - the thickness of both the mounting pad and the control horn
* Height_mm - the of the control horn (from control surface to top hole)
* Tip_y_mm - the depth of the control horn at the tip
* Hole_dia_mm - the diameter of the hole for the control linkage
* Hole_space_mm - the spacing between the centre point of each additional hole
* Hole_count - the number of holes














 