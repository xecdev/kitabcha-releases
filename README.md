# Kitabcha releases

This public repository contains the Android distribution workflow and prepared distribution files. Kitabcha application source remains in a private repository.

The manual publication workflow uses a standard Ubuntu runner, verifies the prepared archive and signed APK, and publishes through the existing restricted deployment receiver. It checks the public APK checksum and English, Dari, and Pashto download links afterward. It does not build or checkout the private application source.

Deployment credentials are encrypted GitHub Secrets. No Firebase service-account keys, signing keys, account data, or app source belong in this repository.

Download the current Android app from https://kitabcha.app/.
