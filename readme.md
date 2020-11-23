Some specifics:
- Use Source version 4.26 preview 7 - Commit f9a75bf03afc9e065682e4cf8b542cb5adc2d9da
- Vive HMD

Steps to reproduce:
1. Create blank C++, no starter content, Build and open the project, Create a default startup map from default map...
2. Check the following Project Settings > Rendering & then restart the project
(RenderSettings_000.ini)
- Forward Renderer > Forward Shading = T
- Default Settings > Anti-Aliasing = MSAA
- VR > Instanced Stereo = T

3. Create a new Niagara Emitter PEN_Hanging from the Hanging particles template, (increase sprite width), put in world
4. Launch in VR mode and see that particles render in left eye.


It seems that this happens only when all 3 settings are set.  If any one of these settings is default then everything works, but when they're all set as specified the bug is visible.
Here are the reuslts of all permutations of these settings (with forward shading going between Temporal & MSAA).


RenderSettings_000.ini (Default Settings)
- Forward Renderer > Forward Shading = F
- Default Settings > Anti-Aliasing = Temporal AA
- VR > Instanced Stereo = F
Result: Good

RenderSettings_001.ini
- Forward Renderer > Forward Shading = F
- Default Settings > Anti-Aliasing = Temporal AA
- VR > Instanced Stereo = T
Result: Good

RenderSettings_010.ini
- Forward Renderer > Forward Shading = F
- Default Settings > Anti-Aliasing = MSAA
- VR > Instanced Stereo = F
Result: Good

RenderSettings_011.ini
- Forward Renderer > Forward Shading = F
- Default Settings > Anti-Aliasing = MSAA
- VR > Instanced Stereo = T
Result: Good

RenderSettings_100.ini
- Forward Renderer > Forward Shading = T
- Default Settings > Anti-Aliasing = Temporal
- VR > Instanced Stereo = F
Result: Good

RenderSettings_101.ini
- Forward Renderer > Forward Shading = T
- Default Settings > Anti-Aliasing = Temporal
- VR > Instanced Stereo = T
Result: Good

RenderSettings_110.ini
- Forward Renderer > Forward Shading = T
- Default Settings > Anti-Aliasing = MSAA
- VR > Instanced Stereo = F
Result: Good

RenderSettings_111.ini
- Forward Renderer > Forward Shading = T
- Default Settings > Anti-Aliasing = MSAA
- VR > Instanced Stereo = T
Result: Bad
