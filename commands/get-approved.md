---
name: get-approved
description: "Get the app through App Review. Check what would get the app rejected, fix it, set up the store, run a test run, submit it, and answer a rejection."
argument-hint: "[app name or bundle ID]"
---

The app: $ARGUMENTS (when that's empty, the app in this repository; ask me which when AppScend has several).

Use AppScend to get that app through App Review, in the order get_docs topic "to-approved" gives. 1) get_app area "approval", then "store": what would get it rejected. 2) Fix the blockers first, then the warnings: if you're in the app's code, use get_finding's brief, make the change on a branch and scan_app; otherwise fix_finding has the Mac's agent do it on a branch. Show me what changed before merge_fix. 3) Store setup: store_setup mode "edit" for what App Store Connect lacks (review_details, age_rating, app_info), and screenshots for the sizes Apple requires. 4) test_run action "start", then get_app area "run"; fix what it finds. 5) analyze scope "review_notes", then store_setup mode "edit" with the notes. 6) When nothing blocks it, submit_for_review (it asks first: show me willDo and the preview, and confirm with its confirm_token only after my yes, or send it to me with approve: "website"). 7) If Apple rejects it: app_review action "report_rejection" with Apple's message, then analyze scope "chat", tool "review", message "Answer Apple's message"; show me the fixes, the reply and when it resubmits, and use_analysis_action how "confirm" only what I agree to. Ask me before anything that reaches Apple or can't be undone.
