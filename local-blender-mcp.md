# Local Blender MCP Development

This document explains how to run the Blender MCP server locally for development.

## Setup

The `run-local-mcp` script allows you to run the local development version of the Blender MCP server instead of the published version.

### Script Location
- **File**: `run-local-mcp`
- **Purpose**: Local development wrapper that runs the server using `uv`

### Requirements
- `uv` package manager (installed via Cargo/Rust)
- Python environment with project dependencies

## Usage

The script automatically:
1. Changes to the project directory
2. Runs `uv run main.py` with any provided arguments
3. Uses the full path to `uv` at `~/.cargo/bin/uv`

```bash
./run-local-mcp
```

## Troubleshooting

### "uv: not found" Error
If you see this error, it means `uv` is not in your PATH. The script has been configured to use the full path `~/.cargo/bin/uv`.

**Alternative Solutions:**
1. Add Cargo bin to your PATH:
   ```bash
   echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.zshrc
   source ~/.zshrc
   ```

2. Install uv if not present:
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

## MCP Integration

When configuring this server in Claude Desktop or other MCP clients, use the full path to the `run-local-mcp` script as the command.