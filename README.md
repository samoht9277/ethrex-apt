# Ethrex APT Repository

Official **Debian / Ubuntu APT repository** for [Ethrex](https://github.com/lambdaclass/ethrex), the high-performance Ethereum execution client built by [LambdaClass](https://lambdaclass.com).

---

## Supported Packages

| Package        | Architecture | Description                          |
|----------------|--------------|--------------------------------------|
| `ethrex`       | amd64, arm64 | Standard CPU build                   |
| `ethrex-gpu`   | amd64, arm64 | GPU-accelerated build (CUDA support) |

All binaries are signed and versioned exactly as on the [Ethrex GitHub Releases](https://github.com/lambdaclass/ethrex/releases) page.

---

## Supported Platforms

- Debian 11 (Bullseye) and newer  
- Ubuntu 20.04 (Jammy) and newer  
- Any derivative that uses `apt` (Pop!_OS, Mint, etc.)

---

## Installation

### 1. Import the repo signing key

```bash
curl -fsSL https://apt.ethrex.xyz/KEY.asc \
  | sudo gpg --dearmor -o /usr/share/keyrings/ethrex-archive-keyring.gpg
```

### 2. Add the Ethrex repo into APT
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ethrex-archive-keyring.gpg] https://apt.ethrex.xyz stable main" | sudo tee /etc/apt/sources.list.d/ethrex.list
```

### 3. Update and install
```bash
sudo apt update
sudo apt install ethrex
```

For GPU versions, run
```bash
sudo apt update
sudo apt install ethrex-gpu
```

## GPG Info
Key Owner	Ethrex Infra <ethrex+infra@lambdaclass.com>

Fingerprint	see key on https://apt.ethrex.xyz/KEY.asc
