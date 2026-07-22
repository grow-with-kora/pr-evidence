# pr-evidence

Visual evidence for pull requests on the (private) `grow-with-kora/kora-platform`
repository: screenshots and screen recordings produced by its Playwright
end-to-end suite.

## Why this repository is public

`kora-platform` is private. GitHub's image proxy (camo) cannot authenticate
against a private repository, so an embedded image pointing back at it renders
as a broken image in pull-request markdown — always. GitHub's own attachment
upload works, but has no API: it needs an authenticated browser session, which
a CI job does not have.

So the CI job publishes here instead, and embeds the files by raw URL. This
repository exists purely to be a host camo is willing to fetch from.

## What lands here

The `PR E2E` workflow pushes one directory per run:

```
pr-<number>/<run-id>-<attempt>/
  screens/   PNG screenshots taken by the specs
  clips/     the same recording as a .gif (inline preview) and .mp4 (scrubbing)
  manifest.json
```

Everything is generated output from a seeded local test stack — throwaway
fixture accounts, generated workspaces, no source code and no real user data.

Nothing here is authoritative and nothing depends on it. Old directories can be
deleted at any time; the only cost is that links in closed pull requests go
stale.
