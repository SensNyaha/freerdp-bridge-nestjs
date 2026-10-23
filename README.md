# @freerdp-bridge/nestjs

This repository contains the 0.2.5 library source under package/ and its independent Node.js 24 test harness.

Install the published library and an explicit native runtime for the server OS. Shared JS modules install transitively.

```sh
npm install @nestjs/common@12.2.0 @nestjs/core@12.2.0 @nestjs/platform-express@12.2.0 reflect-metadata@0.2.2 rxjs@7.8.2 @freerdp-bridge/nestjs@0.2.5 @freerdp-bridge/runtime-linux-x64-gnu@0.2.5
```

Windows x64 selects runtime-win32-x64 of the same version. Public availability is a separate release gate; do not infer it from this source version.

[Full project guide](docs/NESTJS_USAGE.md), [interface](docs/NESTJS_PLUGIN.md), [identity/Cookie boundaries](docs/HOST_AUTHENTICATION.md).

## Development

After the exact core dependencies are public, run npm ci, npm run build, npm run check:types and npm test. The private root manifest supplies host/test tools and OS-selected optional native packages; the published package metadata remains in package/package.json.

The test harness distinguishes fake media from actual native TLS/lifecycle. Real desktop and device acceptance is recorded separately in the release evidence. Each RDP session still owns one native worker; FreeRDP does not run inside Node.

## Release

See DELIVERY.md. The workflow publishes the exact accepted archive from GitHub Releases using OIDC, after Windows/Linux checks and compiled-file comparison. No native tarball or npm credential is stored in Git.

## License

MIT for this adapter; native runtimes carry their own licenses/notices and corresponding source companions.
