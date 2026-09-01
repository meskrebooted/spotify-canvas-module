# spotify-canvas-module

Clone of `apple-mus-module` adapted for Spotify Canvas.
https://raw.githubusercontent.com/meskrebooted/spotify-canvas-module/refs/heads/copilot/implement-spotify-canvas-support/index.json

## Files
- `/home/runner/work/spotify-canvas-module/spotify-canvas-module/spotify_canvas_v1.8spine`
- `/home/runner/work/spotify-canvas-module/spotify-canvas-module/spotify_canvas_v1.json`
- `/home/runner/work/spotify-canvas-module/spotify-canvas-module/index.json`

## Configuration
Set values via environment variables or `globalThis.__SPOTIFY_CANVAS_CONFIG__`:
- `SPOTIFY_CANVAS_ACCESS_TOKEN` (optional bearer token)
- `SPOTIFY_CLIENT_ID` + `SPOTIFY_CLIENT_SECRET` (optional client credentials flow)
- `SPOTIFY_CANVAS_ENABLE_PRIVATE_FALLBACK` (`true`/`false`, default `false`)
- `SPOTIFY_CANVAS_PRIVATE_ENDPOINTS` (comma-separated URL templates with `{trackId}` and `{market}`)

## Behavior
1. Reads Spotify track data from the official Web API.
2. Uses official canvas-like fields if present.
3. Optionally tries configured private endpoints if enabled.
4. Falls back to `preview_url` when Canvas is unavailable.

## Limitations
- Spotify Canvas is not exposed in Spotify public Web API for most integrations.
- Private endpoint fallback is disabled by default and may stop working at any time.
- Without Canvas data, the module returns `preview_url` (audio preview), not a video canvas.
