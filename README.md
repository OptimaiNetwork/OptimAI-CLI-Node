# OptimAI Node CLI

This repository contains the OptimAI Node CLI. Use it to sign in, run your node, check status, and view rewards.

> **Full Documentation:** For detailed information about the OptimAI Node, please visit our [Official Documentation](https://docs.optimai.network/docs/optimai-node/core-node).

## Prerequisites

- OptimAI account
- Docker Desktop (required to run the node)
  - Download: https://www.docker.com/products/docker-desktop/

## Install

### macOS

Run the following commands in your terminal to download and install:

```bash
# Download and rename to optimai-cli
curl -L https://optimai.network/download/cli-node/mac -o optimai-cli

# Make executable and install to PATH
chmod +x optimai-cli
sudo mv optimai-cli /usr/local/bin/optimai-cli
```

### Linux (Ubuntu)

```bash
# Download and rename to optimai-cli
curl -L https://optimai.network/download/cli-node/linux -o optimai-cli

# Make executable and install to PATH
chmod +x optimai-cli
sudo mv optimai-cli /usr/local/bin/optimai-cli
```

### Windows (PowerShell or Command Prompt)

```cmd
curl.exe -L https://optimai.network/download/cli-node/win -o optimai-cli.exe
```

After downloading, you can run it from the current folder:
```cmd
.\optimai-cli.exe --help
```
*Tip: Move `optimai-cli.exe` to a folder in your System PATH to use it from anywhere as `optimai-cli`.*

## Tutorial

### 1) Sign in

Open a terminal and run:

```bash
optimai-cli auth login
```

Enter your email and password when prompted.

### 2) Start the node

Make sure Docker Desktop is running, then start the node:

```bash
optimai-cli node start
```

**Running in the background (Linux/macOS):**
To keep the node running after closing your terminal, we recommend using a tool like `screen`:
1. Start a new session: `screen -S optimai`
2. Run the node: `optimai-cli node start`
3. Detach: Press `Ctrl+A` then `D`
4. Resume later: `screen -r optimai`

Otherwise, keep your terminal open while the node is running.

### 3) Check status

Open a new terminal and run:

```bash
optimai-cli node status
```

### 4) View rewards

```bash
optimai-cli rewards balance
```

### 5) Update the CLI

```bash
optimai-cli update
```

### 6) Stop the node

Press `Ctrl+C` in the terminal where the node is running.

## Command Reference

Account:

```bash
optimai-cli auth login
optimai-cli auth status
optimai-cli auth me
optimai-cli auth logout
```

Node:

```bash
optimai-cli node start
optimai-cli node status
```

Rewards:

```bash
optimai-cli rewards balance
```

Updates:

```bash
optimai-cli update
```



## Tips

- Keep Docker Desktop running before you start the node.

## Troubleshooting

- **Docker not running**: If `optimai-cli node status` shows Docker as `not_running`, start Docker Desktop and retry.
- **Node already running**: If you see "Another node instance is already running", a node process is active in the background.
  - Run `optimai-cli node status` to check the Process ID (PID).
  - If you need to stop it manually, use your system's task manager or run `kill <PID>` (macOS/Linux).
