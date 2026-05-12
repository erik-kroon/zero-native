# Browser Example

A no-build vanilla HTML/CSS/JS example that uses the main WebView for browser chrome and a native overlay WebView for page content.

Run it from this directory:

```sh
zig build run
```

Or from the repository root:

```sh
zig build run-browser
```

The frontend lives in `frontend/` and is served directly as `zero://app/index.html`.

The page content runs in an isolated native overlay WebView. Overlay pages do not receive `window.zero`; all navigation and sizing is controlled by the browser chrome through the overlay handle returned by `window.zero.webviews.create()`.

This example allows all navigation origins so it can browse arbitrary pages. Treat that as demo-only policy, not a production template. Linux Chromium/CEF currently does not support overlay WebViews; use the system WebView backend on Linux for this example.
