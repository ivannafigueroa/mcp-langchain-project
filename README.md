# MCP Terminal Server

A simple MCP server that exposes a tool for running terminal commands.

## Installation

1. Install the MCP Python SDK:

```bash
pip install mcp
```

## Usage

1. Start the server:

```bash
python server.py
```

2. Connect to the server in an MCP-compatible client, such as Claude Desktop:

```bash
mcp install server.py
```

Or use the MCP Inspector to test it:

```bash
mcp dev server.py
```

## Tool Overview

This server exposes one tool:

### terminal_command

Runs a terminal command and returns its output.

**Parameters:**
- `command`: The command to run in the terminal

**Returns:**
- A dictionary containing:
  - `stdout`: The standard output from the command
  - `stderr`: The standard error output from the command
  - `return_code`: The command's return code (0 typically means success)

**Example Usage in Claude:**

```
Can you list the files in the current directory using the terminal tool?
```

## Security Considerations

This tool executes commands directly on your system. Use with caution as it can run any command with the same permissions as the user running the server.

## Limitations

- Commands timeout after 30 seconds
- For security reasons, consider implementing additional validation and restrictions on the commands that can be executed
