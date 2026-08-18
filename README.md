# homebrew-tap

Homebrew formulae for [pomo](https://github.com/muhalifalgibran/pixel-pomodoro).

```sh
brew install muhalifalgibran/tap/pomo
```

Installing through Homebrew avoids the macOS Gatekeeper prompt a downloaded
release gets: `brew` does not mark what it fetches as quarantined, so there is
no `xattr` step and no "Apple could not verify" dialog.

To update:

```sh
brew upgrade pomo
```

`pomo --update` still works, but the two will fight over the same binary —
pick one. Homebrew is the better choice if you installed this way.

## How the formula stays current

`Formula/pomo.rb` is generated, not hand-edited. The workflow in
`.github/workflows/update-formula.yml` checks pixel-pomodoro's latest release
every hour, rewrites the formula against the checksums published with it, and
commits when the version has moved. Run it by hand from the Actions tab to pick
up a release immediately.

It reads the release with the repository's own `GITHUB_TOKEN` and only ever
writes to this repo, so there is no personal access token to keep in a secret.
