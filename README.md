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
# Download and rename to node-cli
curl -L https://optimai.network/download/cli-node/mac -o node-cli

# Make executable and install to PATH
chmod +x node-cli
sudo mv node-cli /usr/local/bin/node-cli
```

### Linux (Ubuntu)

```bash
# Download and rename to node-cli
curl -L https://optimai.network/download/cli-node/linux -o node-cli

# Make executable and install to PATH
chmod +x node-cli
sudo mv node-cli /usr/local/bin/node-cli
```

### Windows (PowerShell or Command Prompt)

```cmd
curl.exe -L https://optimai.network/download/cli-node/win -o node-cli.exe
```

After downloading, you can run it from the current folder:
```cmd
.\node-cli.exe --help
```
*Tip: Move `node-cli.exe` to a folder in your System PATH to use it from anywhere as `node-cli`.*

## Tutorial

### 1) Sign in

Open a terminal and run:

```bash
node-cli auth login
```

Enter your email and password when prompted.

### 2) Start the node

Make sure Docker Desktop is running, then start the node:

```bash
node-cli node start
```

**Running in the background (Linux/macOS):**
To keep the node running after closing your terminal, we recommend using a tool like `screen`:
1. Start a new session: `screen -S optimai`
2. Run the node: `node-cli node start`
3. Detach: Press `Ctrl+A` then `D`
4. Resume later: `screen -r optimai`

Otherwise, keep your terminal open while the node is running.

### 3) Check status

Open a new terminal and run:

```bash
node-cli node status
```

### 4) View rewards

```bash
node-cli rewards balance
```

### 5) Update the CLI

```bash
node-cli update
```

### 6) Stop the node

Press `Ctrl+C` in the terminal where the node is running.

## Command Reference

Account:

```bash
node-cli auth login
node-cli auth status
node-cli auth me
node-cli auth logout
```

Node:

```bash
node-cli node start
node-cli node status
```

Rewards:

```bash
node-cli rewards balance
```

Updates:

```bash
node-cli update
```



## Tips

- Keep Docker Desktop running before you start the node.

## Troubleshooting

- **Docker not running**: If `node-cli node status` shows Docker as `not_running`, start Docker Desktop and retry.
- **Node already running**: If you see "Another node instance is already running", a node process is active in the background.
  - Run `node-cli node status` to check the Process ID (PID).
  - If you need to stop it manually, use your system's task manager or run `kill <PID>` (macOS/Linux).
