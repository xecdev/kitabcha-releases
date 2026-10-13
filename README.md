# Kitabcha releases

This public repository contains release workflows and Android distributables. Kitabcha's application source stays in the private `kitabcha-app` repository.

The manual `release-app.yml` workflow builds an immutable private-source commit on standard Ubuntu runners. A dedicated read-only deploy key permits an ephemeral checkout; the workflow does not commit that source here, cache the checkout, or upload private source or build logs. Only the signed APK is uploaded as a build artifact, with seven-day retention.

The separate `publish-android.yml` workflow can publish a previously prepared, verified Android package without building private source. Both workflows use the existing restricted deployment receiver and pinned SSH host key. They verify release identity, signatures, checksums and public download metadata. The web job transfers its package directly to the server over SSH without uploading it as a public artifact.

Signing and deployment keys remain encrypted GitHub Secrets. Never commit Firebase service-account keys, signing keys, account data or app source here.

Standard runners in public repositories are free: https://docs.github.com/en/actions/concepts/billing-and-usage. No paid runner or service is configured by these workflows.

Download the current Android app from https://kitabcha.app/.
