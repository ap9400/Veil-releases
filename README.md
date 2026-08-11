# Veil — Releases

Public download and update feed for [Veil](https://veil.invalid), a soft lock for
macOS.

**This repository carries no source code.** It exists so that installed copies of
Veil can fetch updates without credentials — release assets on a private
repository require authentication, which would mean shipping a token inside the
app. Source lives in a separate private repository.

## Install

Download the latest `Veil-x.y.z.dmg` from
[Releases](../../releases/latest), drag it to Applications, then clear the
quarantine flag macOS sets on anything downloaded:

```bash
xattr -dr com.apple.quarantine /Applications/Veil.app
```

Veil is signed but not notarized, so macOS blocks it until that flag is cleared.

## Updates

Veil checks `appcast.xml` in this repository and updates itself. Every build is
signed with an EdDSA key whose public half is compiled into the app, so a
tampered download is rejected even though the feed itself is public and
unauthenticated.
