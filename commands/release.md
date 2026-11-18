---
name: release
description: "Prepare a release. Check the new version, test it, write What's New and the review notes, choose how it goes live, and submit it."
argument-hint: "[app name or bundle ID]"
---

The app: $ARGUMENTS (when that's empty, the app in this repository; ask me which when AppScend has several).

Prepare that app's next release with AppScend. 1) scan_app, then get_app area "approval": anything blocking it? 2) test_run action "start", then get_app area "run": fix what it finds. 3) What's New: change_store_setting action "release_text" with what changed since the last version, in plain words (it asks first: show me willDo and the preview, and confirm with its confirm_token only after my yes, or send it to me with approve: "website"). 4) When the release changes sign-in, purchases or anything a reviewer needs to know: analyze scope "review_notes", then store_setup mode "edit" with the notes. 5) How it goes live: store_setup mode "edit" with release_type, and phased_release for a rollout over seven days. 6) submit_for_review (it asks first: show me willDo and the preview, and confirm with its confirm_token only after my yes, or send it to me with approve: "website"). After approval: app_review action "release" for a manual release, and action "auto_pause" to pause the rollout if the new version turns unhealthy.
