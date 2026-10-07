PERNI - MOTION FIELD v14

PUBLIC LINKS
App: https://dperns44.github.io/perni-motion-field/
Download: https://dperns44.github.io/perni-motion-field/Perni-Motion-Field-v14.zip
Repository: https://github.com/dperns44/perni-motion-field

RUN
Unzip and open Salesforce Blue RAy MotionField v14.html in current Chrome or Edge.
The original image tools work offline. No account or installation is needed.
AI depth is optional: its first use downloads a roughly 27 MB model plus the
browser engine. Internet is required for these dependencies; normal browser
caching may reuse them. Inference runs locally, without uploading the image.
Generated depth travels inside Save setup JSON, so using that saved map needs
no AI download. Quick relief and imported depth maps also work offline.
Webcam requires camera permission. If file-based camera access is blocked,
use a localhost or HTTPS server. Phones require HTTPS hosting for camera use.
No microphone is requested. Video and camera frames stay on the device.

SOURCE VS MAPPING
Source = what you bring in: import image/video, choose webcam, start/stop camera,
mirror camera, capture a still frame, and load supplied reference images.
Mapping = how the tool reads it. This tab is immediately after Source.
  Image contours: the original edge/texture analysis, quality, fine contours,
  shimmer placement and debug network tools. This is the default.
  Depth / surface: reveals Create depth map and the optional depth tools.
  Where light can go: shared brightness/detail limits and a mask-brush shortcut.
  Video/webcam: Follow motion, Motion smoothing and Detail cutoff.
Layers = the look and behavior of Trails, Whole image, Traveling dots and Shimmer.
Master = speed, seed, colors and shared motion. Live trail memory and contour
drift affect multiple layers, so they are shared controls here.
Load setup at the top opens artist presets, classic presets and setup JSON.

DEPTH QUICK START
1. Import an image under Source.
2. Open Mapping > Depth / surface > Create depth map.
3. After creation, Surface blend is selected. Trails, Whole image and traveling
   dots and shimmer follow the mixed image/depth field. Enable the desired layers as usual.
4. Use Surface wrap for depth-led contours; Surface blend retains image texture.
5. Surface curvature controls how strongly the bands bend with depth. Wrap amount
   mixes depth and image directions in Surface blend. Under Surface shaping,
   adjust Band direction, Smoothness, Near / far light, and Invert near / far.
6. Show depth is preview-only. Save depth PNG exports the grayscale map.
   Regular PNG/MP4 exports still render your selected motion output.
Switch to Image contours to return to the original tracing. The depth map is
retained for comparison. Importing a different image clears the old depth map.
Artist presets preserve mapping settings. Save/load and Undo/Redo include depth.
Other depth options contain offline Quick relief, Import depth and Remove map.
Imported maps must match the source aspect ratio. White means near, black far.
Quick relief makes a stylized silhouette bulge; it is not an AI depth estimate.
Shimmer dots automatically follow the depth surface in depth mapping mode.
Their drift and trails use cached curved tracks. Near / far light affects their opacity. The separate Scale by depth control
sets size, independently of random variation. Existing shimmer
amount, size, opacity, speed, trails and bright-area cutoff still apply.
Motion amount 0 keeps shimmer stationary; increase it to see surface travel.
Switching to Image contours restores the original shimmer movement.
Existing bright-area cutoffs and painted masks still limit motion. Choose All
image detail if you want to follow dark surfaces too.

SHIMMER DEPTH CONTROLS (v12)
Open Shimmer dots > Depth response while Depth / surface mapping is active.
- Scale by depth: toggle depth-based dot and trail sizing. Scale amount 0 gives
  uniform base size; higher amounts increase the near/far size difference.
- Displace by depth: toggle an offset of dots and their trails using depth.
  Near dots move farther; the farthest dots remain at their original positions.
  Displacement is in original-image pixels, consistent across preview/export.
  Direction: 0 degrees right, 90 down, -90 up. This is a 2D offset driven by depth,
  not a camera move or deformation of the original image.
Both toggles are independent. Existing shimmer masks still clip the result.
Motion amount controls travel along the surface; displacement sets an additional
offset even when Motion amount is zero. Image contours disables depth effects.
Type numbers to extend the slider ranges (scale up to 4, displacement up to
4096 pixels, direction +/-360 degrees). Controls respond without rebuilding paths.
Old setups retain their previous size response; new displacement defaults off.
These settings are included in saved setups, presets and Undo/Redo.

DEPTH LIMITS AND PERFORMANCE
This is relative 2.5D depth, not a full 3D object or metric reconstruction. Hidden
surfaces cannot be recovered reliably and stylized imagery may be misinterpreted.
The original image is never displaced. Surface bands come from tilted depth
contours, with optional near/far line-width and light variation.
AI runs in a cancellable worker on demand, at up to 512 px on the longest side.
Depth and direction fields are cached. Point edits still use background routing.
No model is loaded when starting the app or using original image contours.
Finish or cancel depth creation before rendering a shot. Depth mapping is for
stills; capture a video/webcam frame to use it. Live footage keeps optical flow.

LIVE MEDIA
Video: import a browser-supported file (up to 10 minutes), play/pause/scrub.
Webcam: click Start camera and allow access. Stop and switching source release it.
Loading a setup remembers the chosen source but never starts the camera or
restores a video file automatically. Reimport the clip or start the camera.
Live optical flow is experimental. Blur, fast movement, occlusion, flat regions
and repeated textures can lose or misdirect tracks. It is not body/object tracking.
Live media uses separate lightweight contour effects. Still-image painted masks,
guide points, write-on and path crossovers do not apply to live footage.
Capture frame returns to the complete still-image toolset.

EXPORT AND SHARING
Set shot name, version, view and seconds, then Render MP4. Output is silent H.264
at constant 24 fps. Images use whole-number seconds. Video duration rounds up
to the next frame. Webcam records in real time, up to 60 seconds; slow cameras
or computers repeat frames to preserve duration. Cancel discards partial MP4s.
Camera disconnects abort recording. Keep the tab visible while rendering.
Source on/off affects preview; export has its own background/view settings.
Give teammates this ZIP. A saved setup JSON shares the still image, depth map,
settings, guides and masks. It does not include video files or camera footage.
Live-mode JSON also includes your last still image; the save message says so.

TESTED IN v12
Independent scale and displacement controls, GPU/Canvas pixel positions,
no geometry rebuild on adjustment, extended typed values, save/load, Undo,
unchanged original mapping, mobile layout and MP4 export. Measured displacement
matched its expected value within 0.004 preview pixels in the focused test.
Fresh output: 24 frames / 1 second; nominal and average frame rates 24/1.
The surface shimmer checks below also pass with these controls:
Depth shimmer tested with 8,000 dots sharing 2,189 cached surface tracks. Checked
distinct surface-following motion, unchanged source, fixed geometry uploads,
point edits without rebuilding shimmer, save/load, zero-motion behavior, masks,
GPU and Canvas rendering, original-mode restoration and a 24-frame/1-second MP4.
The depth/mapping work below was verified during v10 development:
Real AI inference on the whale reference and the current user image, including
the standalone file:// HTML. Verified a non-flat depth map and curved routes.
Depth worker and main-thread geometry match. Image contours restores the original
route geometry exactly while retaining depth. Presets preserve mapping.
Save/load, Undo/Redo, new-image invalidation, malformed map rejection, failed
network load, cancellation, GPU/Canvas rendering, mobile layout and keyboard tabs.
No model requests at app startup. Source/Mapping/Master controls tested in both
image and live modes. Existing point-worker, GPU and live-media regressions pass.
A fresh depth-guided MP4 decodes as 24 frames / 1 second; nominal and average fps
are both 24/1. Physical-camera quality and After Effects import remain unverified.

DEPENDENCIES / ATTRIBUTION
AI runtime: Hugging Face Transformers.js 3.8.1 (Apache-2.0), loaded on demand:
https://huggingface.co/docs/transformers.js/v3.8.1/index
https://github.com/huggingface/transformers.js
Depth Anything V2 Small ONNX model (Apache-2.0):
https://huggingface.co/onnx-community/depth-anything-v2-small
Pinned model revision: 4472b7362082ad9968fee890ca0f1e5aca36b93d
Runtime/model weights are downloaded by the browser, not bundled in this ZIP.

VERSION
Tool release v14; previous releases are preserved. Setup schema is 1.
Export shot/take version numbers are independent of the tool release.

V13 PUBLICATION
GitHub Pages release of the v12 tool. Rendering behavior is unchanged.

V14 POINT STEERING
Direct motion > add a Waypoint, Attractor or Repeller. Drag its center to move;
drag its ring or edit Influence range to resize; adjust Influence for strength.
Waypoints steer paths through their area, then release them. Nearby guides are
chosen by influence, so a distant waypoint does not block another nearby one.
Attractors pull toward their center. End paths at attractors, shown beside a
selected attractor, controls arrival behavior globally; turning it off allows
paths to continue and no longer disables attraction. Repellers bend paths away.
These guides affect still-image Trails, Whole image and Traveling dots.
Shimmer dots and live video/webcam tracking remain independent of these guides.
Source areas emit Trails and Traveling dots; Whole image keeps distributed starts.
The range fades smoothly at its edge; a zero range has no steering influence.
Guides can bend across local contours, but existing brightness limits, image gaps,
depth discontinuities and output masks still constrain the result. They do not
guarantee arrival across disconnected detail. Large/high-strength guides can
dominate the image flow: lower Influence or shrink their range for gentler motion.
Tests: coherent contour attraction, waypoint pass-through, repulsion, range,
strength, multiple guides, brightness/depth limits, GPU/Canvas, save/load,
mobile layout, background worker parity, pointer drag and stale-result handling.
Repellers now divert routes around a shaded clear center, including crossovers.
Mouse-created guides start at 18% range, matching keyboard placement. Legacy
zero-range waypoints, attractors and repellers recover their former 18% range.
New explicit zero-range values remain zero when saved or undone.
Disabling a soloed layer clears Solo. The active Solo and Show all layers control
are visible above the preview on every tab. Startup shows a preparation message.
