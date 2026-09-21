# TagForge

*Offline asset-label printing*

TagForge is a self-contained, offline tool for producing tray, container, and pallet labels. It requires no installation, no license, no login, and no network connection, and has been in production use for several weeks with no reported issues. This brief covers what the tool does, its measured impact, and what a wider rollout would involve.

## What TagForge does

- **Range expansion** — paste the first allocated tag and the number of items created; the full sequential range is generated automatically, with zero-padding preserved.
- **One-click list copy** — the same range is copied ready to paste into the tracking system, replacing manual, digit-by-digit entry.
- **Batch printing** — the whole batch prints in a single action, each label sized exactly to the label stock, so no manual resizing is needed.
- **Built for the floor** — Code 128 and QR, tray and pallet label sizes, and printed notes or initials in place of handwriting on the label.

## Measured effect

Measured in a single department:

- 7 operators, typically 30+ labels per operator per day.
- Previous process: up to ~10 minutes per batch, generated one label at a time.
- TagForge: under one minute for the same batch, including the tracking-system paste.
- Roughly one hour per day recovered in this department alone — on the order of 250 hours per year, assuming one batch per operator per working day.

*These figures are from a single department; other departments and sites have not been measured. Manual transcription of tag numbers is structurally eliminated rather than reduced — no error rate was recorded before or after, so no error-reduction claim is made here.*

## Verification and security

TagForge runs entirely offline inside a single HTML file: asset numbers never leave the machine, and there is no installation, account, or network call of any kind. The barcode engines self-test every time the file is opened and refuse to run if a check fails. Generated codes were round-trip decoded against real tag formats during development, and printed labels were verified scanning correctly into the existing tracking system before use. Codes are rendered at native printer resolution rather than as scaled images, which produces a cleaner scan than the previous method.

## Deployment

The tool is one file on a shared drive; the marginal cost of an additional user, department, or site is zero. For a multi-site rollout, hosting it as an internal web page is recommended — it avoids e-mail attachment filtering and per-machine downloads, and guarantees every site is running the same version. It has been tested with the Zebra GK420d at 203 dpi using the standard ZDesigner driver, and is configurable for other Zebra models and label sizes.

## Proposed next step

Make TagForge available to other teams and facilities that produce asset labels manually, and confirm with IT the preferred method of hosting and distribution.

---

*Prepared by Christopher Wilson · TagForge v1.0 · July 2026*
