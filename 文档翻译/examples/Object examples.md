## Agent Cam

[CrowdPov](https://www.sidefx.com/docs/houdini/examples/nodes/obj/agentcam/CrowdPov.html) Example for [Agent Cam](https://www.sidefx.com/docs/houdini/nodes/obj/agentcam.html) object node

This example demonstrates how the agent cam can be assigned to a crowd agent to give you the point of view from someone in a crowd simulation.

## Environment Light

[PortalBox](https://www.sidefx.com/docs/houdini/examples/nodes/obj/envlight/PortalBox.html) Example for [Environment Light](https://www.sidefx.com/docs/houdini/nodes/obj/envlight.html) object node

This example shows how to create a portal light using window geometry. A box is modeled and then split into 2 SOPs - one representing windows and the other walls. The walls are rendered, while the windows are used to specify the portal for an environment light. Toggle on and off the portal to see the render quality difference while rendering in the Render View.

## Extract Transform

[extracttransform](https://www.sidefx.com/docs/houdini/examples/nodes/obj/extractgeo/extracttransform.html) Example for [Extract Transform](https://www.sidefx.com/docs/houdini/nodes/obj/extractgeo.html) object node

This example shows how to parent geometry to a moving piece of geometry that is defined by a prebaked .bgeo sequence.

## Light

[TransparentShadows](https://www.sidefx.com/docs/houdini/examples/nodes/obj/hlight/TransparentShadows.html) Example for [Light](https://www.sidefx.com/docs/houdini/nodes/obj/hlight.html) object node

This example shows how to configure transparent shadows with deep shadow maps. The scene includes a transparent grid which casts a shadow on the scene. The renderer used is micropolygon rendering.

## Indirect Light

[IndirectLightBox](https://www.sidefx.com/docs/houdini/examples/nodes/obj/indirectlight/IndirectLightBox.html) Example for [Indirect Light](https://www.sidefx.com/docs/houdini/nodes/obj/indirectlight.html) object node

This example shows how to set up the indirectlight object for indirect diffuse lighting. The scene consists of a box that has been extruded several times, containing a light source and the camera. The light has been placed so that all light reaching the camera must bounce more than once inside the scene before reaching the camera. The indirectlight object is configured to generate 1000000 photons. To visualize the photon map, change the rendering mode on the light to “Direct Global Photon Map”. To adjust the sampling quality, modify the pixel samples or ray samples on the mantra ROP. The rendering engine used in this example is PBR.

## (TubeCaustic)

[TubeCaustic](https://www.sidefx.com/docs/houdini/examples/nodes/obj/indirectlight/TubeCaustic.html) Example for [Indirect Light](https://www.sidefx.com/docs/houdini/nodes/obj/indirectlight.html) object node

This example shows how to set up the indirectlight object for caustic photon map generation and also how light masks and photon targets should be used. The scene consists of a reflective tube and a point and environment light. Each light has a corresponding indirectlight to generate caustics, with the light mask configured to allow the light to generate photons only from the specified light. The photon target is used to ensure that photons are only sent toward the reflective tube. The mantra ROP will produce deep raster planes for the direct_diffuse component on a per-light basis, showing the diffuse illumination from the two lights and the caustics split into separate planes.

## Path

[PathPathcvWorm](https://www.sidefx.com/docs/houdini/examples/nodes/obj/path/PathPathcvWorm.html) Example for [Path](https://www.sidefx.com/docs/houdini/nodes/obj/path.html) object node

This example shows a use for the Path and Pathcv nodes. These Path CV’s can be rotated greater than 360. They also have an initial twist function under the controls tab. This can be useful for creating a quick spine.

## Rivet

[RivetWaveform](https://www.sidefx.com/docs/houdini/examples/nodes/obj/rivet/RivetWaveform.html) Example for [Rivet](https://www.sidefx.com/docs/houdini/nodes/obj/rivet.html) object node

In this example, a Waveform deformer is applied to a grid. A Rivet is then attached to the surface of the grid, and then parented to a sphere.

## Sticky

[StickyDonut](https://www.sidefx.com/docs/houdini/examples/nodes/obj/sticky/StickyDonut.html) Example for [Sticky](https://www.sidefx.com/docs/houdini/nodes/obj/sticky.html) object node

In this example, a donut is stuck to an animated sticky object on the surface of a grid.

## Switcher

[switchcamera](https://www.sidefx.com/docs/houdini/examples/nodes/obj/switcher/switchcamera.html) Example for [Switcher](https://www.sidefx.com/docs/houdini/nodes/obj/switcher.html) object node

In this example, we demonstrate how a switcher node can be used to switch the view between two cameras and then used by the render node to output the scene.

## /nodes/vop/surfacemodel

[RainbowGeometryLight](https://www.sidefx.com/docs/houdini/examples/nodes/obj/hlight/RainbowGeometryLight.html)

This example highlights several features:

-   Geometry area lights
    
-   Attenuation ramp controls
    
-   Surface model specular layers
    

The example consists of a geometry light based on a wireframe of nurbs curves. The attenuation on the light uses colored keys, allowing for different light colors to be produced at different distances from the light. The ground plane shader uses a surface model with two specular components - one wide component and another narrower glossy component to give a multi-layered appearance.