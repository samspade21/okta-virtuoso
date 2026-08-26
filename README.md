# Okta Virtuoso

A Chrome extension that adds a bunch of productivity features to the Okta admin console — exporting objects to CSV, enhanced search, SSO/SAML inspection, an API explorer, and more.

## Credit

This project is a branch of [**Okta Rockstar**](https://github.com/gabrielsroka/gabrielsroka.github.io/tree/master/rockstar) by [**Gabriel Sroka**](https://github.com/gabrielsroka) ([gabrielsroka.github.io/rockstar](https://gabrielsroka.github.io/rockstar/)). All credit for the original extension and its design goes to him — this repo starts from his code (see `LICENSE`, carried over unmodified as required by its MIT terms).

### How this fork differs

Where upstream Okta Rockstar sticks to Okta's public, documented `/api/v1/*` API, Virtuoso also calls Okta's internal/undocumented admin-console APIs (`/api/internal/*`) where a feature has no public API equivalent — for example, triggering a group-push "Push now" action. Every feature that uses one is explicitly labeled in the UI. These endpoints can break at any time.

## Install as an unpacked extension

1. Clone this repo.
2. Open Chrome and go to `chrome://extensions`.
3. Enable **Developer mode**.
4. Click **Load unpacked** and select the cloned folder.

## Development

This repo uses [pre-commit](https://pre-commit.com/) for linting and secret scanning. To set it up:

```sh
pip install pre-commit    # or: brew install pre-commit
pre-commit install
```

After changing `rockstar.js`, reload the extension on `chrome://extensions`, then reload the Okta tab you're testing against.
