# lotti-docs

Generated media for Lotti documentation and release communication. Application
source, manual prose, screenshot case definitions, and CI orchestration live in
the sibling `lotti` repository.

## Automated manual screenshots

```text
manual/screenshots/
├── development/
│   ├── manifest.json
│   └── <case-id>/
│       ├── mobile-light.webp
│       ├── mobile-dark.webp
│       ├── desktop-light.webp
│       └── desktop-dark.webp
└── <app-marketing-version>/
```

Run `make manual_screenshots` from the `lotti` checkout to regenerate the
development catalog. Raw PNG staging is ignored under `manual/.staging/`.
Final files and manifests are generated; do not rename or hand-edit them.

Release directories are immutable. `development` may be refreshed by CI, while
a numbered directory is created from the matching Lotti release tag. The
server can synchronize `manual/screenshots/` directly from `main` without a
Flutter toolchain.
