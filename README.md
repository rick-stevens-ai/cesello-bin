# cesello-bin

Prebuilt binary artifacts for deployment testing.

Assets are published under [**Releases**](../../releases).

## Download & run (Linux x86_64)

```sh
curl -fsSL -o cesello \
  https://github.com/rick-stevens-ai/cesello-bin/releases/latest/download/cesello-linux-x86_64-musl
chmod +x cesello
./cesello --version
```

Other targets in the release:
`cesello-linux-aarch64-musl`, `cesello-macos-x86_64`, `cesello-macos-aarch64`.

## Verify integrity

```sh
curl -fsSL -O https://github.com/rick-stevens-ai/cesello-bin/releases/latest/download/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt      # shasum -a 256 -c on macOS
```
