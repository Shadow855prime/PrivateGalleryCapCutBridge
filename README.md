# Private Gallery → CapCut Bridge

Android 16 (API 36) privacy-focused bridge app for user-authorized Gallery/Photos images.

## What it does

- Select one or many images with Android's system Photo Picker.
- Receive images explicitly shared from Gallery/Photos with `ACTION_SEND` / `ACTION_SEND_MULTIPLE`.
- Immediately copy authorized incoming URIs to app-private temporary storage so short-lived URI grants are safe.
- Preserve original image bytes: no recompression, resize, watermark, or edits.
- Share temporary copies to CapCut with secure `content://` FileProvider URIs.
- If CapCut cannot be targeted directly, open Android's chooser.
- Export copies to `Pictures/CapCut Bridge` through MediaStore as a compatibility fallback.
- Optional temporary cleanup with WorkManager.
- No root, ADB, Shizuku, accessibility automation, sandbox bypass, or private-album authentication bypass.
- No `INTERNET`, `READ_MEDIA_IMAGES`, or broad storage permission.

## Android 16 build

The app targets Android 16 / API 36. The GitHub Actions workflow decodes the project source archive, installs API 36, uses JDK 17 + Gradle 8.13 + AGP 8.13.2, builds `app-debug.apk`, and publishes the APK as a workflow artifact.

The full Android Studio project is stored in `project.zip.b64` as a base64-encoded ZIP so the build can be reproduced in GitHub Actions.
