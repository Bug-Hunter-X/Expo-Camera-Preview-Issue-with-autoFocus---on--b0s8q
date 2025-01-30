# Expo Camera Preview Issue with autoFocus: 'on'

This repository demonstrates a bug in the Expo Camera API related to the `autoFocus` property. When `autoFocus` is set to `'on'`, accessing the camera preview before it's fully initialized can result in the preview failing to display or showing an error. The behavior is inconsistent across different devices and Expo SDK versions.

## Bug Description
The bug manifests when trying to render the camera preview immediately after mounting the component. In some cases, the preview will not render. In others, an error will be thrown. This is particularly noticeable when using `autoFocus: 'on'`.

## Solution
The solution involves ensuring the camera is fully initialized before attempting to render the preview. This can be achieved by using the `cameraRef` to check the camera's state and only rendering the preview once it's ready.  A loading indicator can be shown while waiting for the camera to initialize.

## How to Reproduce
1. Clone the repository.
2. Install the dependencies: `npm install` or `yarn install`.
3. Run the app: `expo start`.
4. Observe the inconsistent preview behavior.