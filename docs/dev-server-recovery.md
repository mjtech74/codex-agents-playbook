# Dev Server Recovery

Browser automation is only useful when the local server is healthy.

## Before Browser Checks

Confirm:

- expected port is listening
- target URL returns HTTP 200 or the expected status
- server logs do not show compile/runtime failures

## If Navigation Times Out

Do not keep retrying browser navigation blindly.

Instead:

1. Check the server process.
2. Check HTTP response outside the browser.
3. Inspect server logs.
4. Restart one server process cleanly.
5. Clear framework dev cache only when stale chunks or manifest errors indicate it.
6. Open a fresh browser context after the server responds.

## What To Log

- port and process status
- HTTP response or timeout
- browser error message
- recovery step taken
- remaining uncertainty

## Common Pitfall

A timed-out shell session can leave a server process alive with detached logs. The port may still listen while requests hang. Treat that as a server state problem before debugging application code.
