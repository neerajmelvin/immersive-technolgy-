# AR Ball Toss

Throw a virtual ball at a target placed on a real surface. Unity 6 + AR Foundation.

Flow: detect plane -> tap to place target -> swipe up to throw -> trigger collision scores.

## Setup (once)
1. Unity Hub > Add project from disk > select this folder. Use Unity 6 (6000.x) with Android and/or iOS build support installed.
   If Unity reports package version problems, open Window > Package Manager and update AR Foundation, ARCore, ARKit.
2. Create/open a scene. In the Hierarchy: right-click > XR > AR Session, then XR > XR Origin (Mobile AR).
3. On the XR Origin add AR Plane Manager (assign a plane prefab: right-click > XR > AR Default Plane, drag into Project to make a prefab, delete from scene) and AR Raycast Manager.
4. Menu **AR Ball Toss > Create Gameplay Objects**. It creates the Ball and Target prefabs, the UI, and a GameManager wired to everything. Save the scene.
5. Edit > Project Settings > XR Plug-in Management: tick ARCore (Android tab) and/or ARKit (iOS tab).
6. Edit > Project Settings > Player > Active Input Handling: Input System Package (New).

## Run on your phone
**Android**: enable Developer options + USB debugging, plug in the phone (it must support ARCore). File > Build Profiles > Android > Switch Platform. Player Settings: Minimum API Level 24+, Scripting Backend IL2CPP, ARM64 only, remove Vulkan if the camera feed is black. Build And Run.

**iOS**: needs a Mac with Xcode. Build to an Xcode project, fill in Camera Usage Description in Player Settings, sign with your Apple ID, run.

## Tuning
- BallLauncher: min/max speed, upward bias, swipe threshold.
- Target: points per hit. Resize the ScoreZone box collider to make scoring easier/harder.
