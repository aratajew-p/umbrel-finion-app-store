# Finion — Umbrel Community App Store

Personal [umbrelOS](https://umbrel.com) app store for the FinionStudio
surfaces, packaged as individual apps.

Add it in umbrelOS under **App Store → ⋯ → Community App Stores**:

```
https://github.com/aratajew-p/umbrel-finion-app-store.git
```

## Apps

| App | Port | What it does |
| --- | --- | --- |
| `finion-etrade` | 4200 | Polish capital-gains summaries from an E*TRADE Gains & Losses XLSX export |
| `finion-stacksats` | 4201 | Bitcoin portfolio, cost basis, and Polish crypto tax from exchange trade history |
| `finion-humbletrading` | 4202 | BTC cycle dashboard with on-chain confluence and Telegram alerts |

## Note on images

This repository holds manifests only — no application source. The apps run
images built on the Umbrel device itself and served from a registry bound to
loopback (`localhost:5000`), so they are not published to any public registry.

That arrangement is not incidental. umbreld pulls app images through Dockerode
without an auth config and aborts the install if a pull fails, so an image
behind registry credentials cannot be installed as an Umbrel app at all. A
loopback registry keeps the pull anonymous while keeping the images on the
device.

Consequently these manifests will not install on someone else's Umbrel without
building the images locally first.
