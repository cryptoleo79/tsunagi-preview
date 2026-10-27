# Preview releases

GitHub Releases contain distinct artifacts with different qualification scopes. At the
**2026-10-27** check, GitHub marked the October portable follower release **Latest**. Recheck the
[release list](https://github.com/cryptoleo79/tsunagi-preview/releases) for later versions.

| Release | Executable | Recorded scope |
|---|---|---|
| [2026-10-05 portable follower](https://github.com/cryptoleo79/tsunagi-preview/releases/tag/v2026.10.05-preview-portable-x86_64) | `tsunagi-preview-v2026.10.05-linux-x86_64` | Preview ChainSync, BlockFetch, transaction decoding/application, local persistence, and cold reopen from generated state, as stated in that release. **Not qualified there for block production.** |
| [2026-06-18 producer snapshot](https://github.com/cryptoleo79/tsunagi-preview/releases/tag/v2026.06.18-preview) | `tsunagi-node-v2026.06.18-preview-linux-x86_64` | Historical Preview block-production and supervision observations from June 2026. Not a statement about current operation. |

## October follower: use its release-specific files

The October release contains the executable, `SHA256SUMS`, `PROVENANCE-MANIFEST.md`, and an
attached `INSTALL.md`. The executable's published SHA-256 is
`4919985711adbf8f59b07839752e605ac3d98d1df35a42f5f93ab2ff3985e08e`. Download the
binary and checksum from that **same** release, run `sha256sum --check SHA256SUMS`, then follow
its attached installation instructions. It is dynamically linked and requires glibc 2.34 or
newer, `liblmdb.so.0`, and `libsodium.so.23`. The release explicitly excludes qualification for
block production, stake-pool operation, Mainnet, production-grade use, and Node V1 completion.

## June producer: historical release

The June release tag and status snapshot are dated **2026-06-18**; GitHub published the release
at **2026-06-19 01:19:50 UTC**. It contains its **different** producer executable, `SHA256SUMS`,
`cockpit`, and `forge.env.sample`. The producer binary's published SHA-256 is
`b93a60fe731cc381633fc1b8170b66da9e03032a0ca71569ecf2bdb8e2047dd9`. The June
[`DOWNLOAD.md`](DOWNLOAD.md) and [`INSTALL.md`](INSTALL.md) examples are scoped to this release
only. The 41-block claim is a dated [`PUBLIC_STATUS.md`](PUBLIC_STATUS.md) record from
2026-06-18, not a claim about the October follower or present chain activity.

For evidence chronology and open gaps, see [`CHANGELOG.md`](CHANGELOG.md),
[`REALITY-GAPS.md`](REALITY-GAPS.md), and [`SURVIVAL.md`](SURVIVAL.md). Verify each release's own
asset names, checksum, and instructions before use; the two executable names and purposes differ.
