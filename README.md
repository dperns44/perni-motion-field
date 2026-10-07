# Perni - Motion Field v16

[Open the app](https://dperns44.github.io/perni-motion-field/) | [Download v16 ZIP](https://dperns44.github.io/perni-motion-field/Perni-Motion-Field-v16.zip)

An artist-facing browser tool for image-guided trails, traveling dots, shimmer and motion-reference videos. Your source image stays fixed. Export MP4 at 24 fps, or export spline geometry for Cinema 4D.

## Run
Open the app in Chrome or Edge, or unzip and open the HTML. Image tools work offline. Optional AI depth downloads its engine/model on first use and runs locally.

## Cinema 4D
Export > Cinema 4D > Animated light streams or Full paths > Export C4D splines. Uses the shot name, take version and seconds. The ZIP contains JSON, a Python importer and instructions. Run the importer in C4D Script Manager and choose the JSON. It creates a new scene with editable multi-segment splines and native 24 fps PLA animation. Save as .c4d; no plugin or external animation cache is needed.

Enable Displace with depth map to add depth at export, independently of the Mapping mode. If needed, export creates a map while preserving your designed paths. Offline relief is also available. This is a 2.5D surface, not a full 3D reconstruction.

Spline export includes enabled Trails and Whole image. Glow, fades, brightness masks, the image plate and dots remain separate from spline geometry. Live sources must be captured to a still first. Browser export, timing, depth preservation and package checks passed; the native C4D engine test is pending a command-line license assignment.

## Share a look
Save setup includes the still image, settings, depth map and guides. Teammates use Load setup. Video files and webcam footage are not embedded.

See [README.txt](README.txt) for controls, export instructions, dependencies and limitations. Live motion tracking is experimental.
