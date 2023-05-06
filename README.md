# HelloXR with Pass thorugh and Hand tracking
This is a modification of the Android HelloXR sample that's included in the [Pico OpenXR SDK](https://developer-global.pico-interactive.com/sdk?platformId=3).
The modifications are essentially:
1. Updating the Android Project to SDK 33 and Gradle 8.1
2. For Hand Tracking: Request the feature, get handles to L/R Hands and then for each render get the joint locations and draw the hand cubes. Also, `<meta-data android:name="handtracking" android:value="1" />` was added to AndroidManifest under the Application node. Hand tracking doesn't work if the controllers are active.
3. For Passthrough: Request the feature, create and start the PassthroughFB Layer, resume/pause the PassthroughFB layer on app resume/pause, add in a Passthrough layer during render before the Projection Layer and changing the `OpenGLESGraphicsPlugin` to clear to a transparent color when rendering the Projection views.
