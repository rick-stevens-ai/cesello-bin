# cesello-bin

Prebuilt binaries for [**cesello**](https://github.com/rick-stevens-ai/cesello) —
a clean-room Rust WebSocket tunnel (TCP forward / reverse / SOCKS5). No WireGuard,
no Go runtime. Linux builds are fully static (musl), drop-in on any host.

Binaries are published under **[Releases](../../releases)**.

## Platforms

| asset | platform | notes |
|-------|----------|-------|
| `cesello-linux-x86_64-musl`  | Linux x86_64  | fully static (musl) |
| `cesello-linux-aarch64-musl` | Linux aarch64 | fully static (musl) |
| `cesello-macos-x86_64`       | macOS Intel   | |
| `cesello-macos-aarch64`      | macOS Apple Silicon | |

## Download & run (Linux x86_64 example)

```sh
curl -fsSL -o cesello \
  https://github.com/rick-stevens-ai/cesello-bin/releases/latest/download/cesello-linux-x86_64-musl
chmod +x cesello
./cesello --version
```

## Verify integrity

```sh
curl -fsSL -O https://github.com/rick-stevens-ai/cesello-bin/releases/latest/download/SHA256SUMS.txt
shasum -a 256 -c SHA256SUMS.txt      # (sha256sum -c on Linux)
```

## Quick use

```sh
# server (rendezvous host)
cesello server --host 0.0.0.0 --port 8080 --reverse --socks5 --key <KEY>

# client: forward local 9002 -> server -> target
cesello client --key <KEY> ws://SERVER:8080 9002:127.0.0.1:9001

# client: reverse — expose a local service back on server:19080
cesello client --key <KEY> ws://SERVER:8080 R:19080:127.0.0.1:18080
```

Source & build instructions: https://github.com/rick-stevens-ai/cesello
