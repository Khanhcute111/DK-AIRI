# DK AIRI

DK AIRI is an Android build project based on the upstream [Moeru AI AIRI](https://github.com/moeru-ai/airi) project.

## Current approach

- Uses the upstream `apps/stage-pocket` Capacitor Android application.
- Builds from the upstream source at build time, so the original AIRI packages and feature implementations are retained instead of recreating a reduced demo.
- Applies a small DK AIRI branding overlay (Android launcher/app label only).
- Produces a debug APK through GitHub Actions. No signing keystore or API credentials are required for this debug build.

## Build an APK

1. Open the **Actions** tab.
2. Select **Build DK AIRI Android APK**.
3. Press **Run workflow** on the `main` branch.
4. Wait for the Android build job to finish.
5. Download the `DK-AIRI-debug-apk` artifact from the completed run.

## Important compatibility notes

- The APK is a native Android wrapper around AIRI Stage Pocket; it does not automatically bundle a large local language model.
- Online providers require the user's own provider configuration and credentials in AIRI. Never commit API keys to this repository.
- Offline/local inference depends on the model runtime, model format, device RAM, storage, and Android WebView/WebGPU support. The workflow does not claim every desktop/local engine works on Android.
- Game integrations, bot integrations, and server-backed features still require their respective external services and permissions.
- The app keeps the upstream Android application ID `ai.moeru.airi_pocket` for compatibility at this initial stage. Branding/package identity can be migrated separately after verifying deep links, plugins, and update behavior.

## Character customization

The requested blue-haired navy/white/gold outfit is a **3D model asset change**, not a CSS skin. To preserve the original face, body proportions, rig, and animations, a source VRM/Live2D asset is needed before a safe hair/outfit edit can be made. No replacement model is bundled yet.

## Upstream and license

This project builds the upstream AIRI source from its default branch. AIRI is licensed under MIT; see the upstream repository and license for attribution and third-party notices. Review upstream changes before distributing builds.
