# refqa-privacy

Hosts the privacy policy for the **Rifqa (رِفقة)** app at
<https://husseinmohamed99.github.io/refqa-privacy/>, via GitHub Pages.

## Why this is a separate repo

The policy is deliberately *not* served from the app repo:

- A privacy policy must be updatable **independently of app releases**. Fixing a
  wrong sentence should not require merging a branch and shipping a build.
- App-store listings link to this URL permanently. Keeping it off the app repo's
  release cycle means the link cannot break because of a branch rename or a
  reorganised `docs/` folder.
- Serving the app repo's `docs/` folder would also publish its internal
  engineering notes, which have nothing to do with users.

## Source of truth

The canonical copy lives in the app repo at `docs/privacy-policy.md`, where it
sits next to the code it describes and is reviewed alongside it. `index.md` here
is a copy of that file.

**When the policy changes, update the app repo first, then copy it here:**

```sh
cp /path/to/refqa/docs/privacy-policy.md index.md
git commit -am "Update privacy policy" && git push
```

Pages redeploys automatically within a minute or so.
