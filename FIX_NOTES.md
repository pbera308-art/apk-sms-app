# Fix: Banglar Shiksha login "Server error" in WebView (works in Chrome)

Changes in MainActivity.kt:
1. Removed the `X-Requested-With: com.bspsms.android` header (WebSettingsCompat.setRequestedWithHeaderOriginAllowList).
2. User-Agent is now Chrome-style (no `wv`, no `Version/4.0`), built from the device's real WebView Chrome version.
3. NO_CACHE_HEADERS (Cache-Control/Pragma/Expires) are no longer sent on page loads.
Applied to all 3 portal WebViews (main, popup, background marksheet).
