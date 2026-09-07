# Security

Vita releases are Universal macOS apps signed ad hoc. No Apple Developer ID certificate is used, and Apple notarization is not performed.

Sparkle updates are signed with EdDSA. Vita requires a signed update feed and verifies update archives before extraction. Every release also includes `SHA256SUMS.txt`.

Vita is not App Sandbox enabled. Hardened Runtime remains enabled. The `com.apple.security.cs.disable-library-validation` entitlement is required because the separately signed SPL Vitalizer Audio Unit fails to instantiate without it; a dedicated build test confirmed that it loads when the entitlement is present.

Verify a download from the directory containing the release files:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

Network endpoints used by Vita:

- `https://min152193.github.io/Vita-Releases/appcast.xml` for Sparkle updates
- `https://github.com/min152193/Vita-Releases/releases/` for release downloads
- `https://api.sidelabs.net/mac/vita/report` for bug reports submitted by the user
