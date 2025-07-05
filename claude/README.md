# Claude Profile Manager

A cross-platform Python script for managing multiple Claude Code authentication profiles on macOS and Linux.

## Features

- Save multiple authentication profiles
- Switch between different Claude accounts using short/long flags
- Cycle through profiles quickly
- List all saved profiles
- Show current active profile
- Cross-platform support (macOS Keychain and Linux file-based storage)

## Installation

1. Make the script executable:
   ```bash
   chmod +x claude-profile
   ```

2. Add the repository path to your PATH in your shell profile (e.g., `~/.zshrc` or `~/.bashrc`):
   ```bash
   export PATH="$PATH:/path/to/ai-tools-pub/claude"
   ```

3. Reload your shell or source the profile:
   ```bash
   source ~/.zshrc  # or ~/.bashrc
   ```

## Usage

### Command Line Options

```bash
# Save current authentication as a profile
claude-profile --save <profile_name>

# Switch to a specific profile (short form)
claude-profile -s <profile_name>

# Switch to a specific profile (long form)
claude-profile --switch <profile_name>

# Cycle to the next available profile (short form)
claude-profile -c

# Cycle to the next available profile (long form)
claude-profile --cycle

# List all saved profiles (short form)
claude-profile -l

# List all saved profiles (long form)
claude-profile --list

# Show current active profile
claude-profile --current

# Show help
claude-profile --help
```

### Examples

```bash
# Save your work account
claude-profile --save work

# Save your personal account  
claude-profile --save personal

# Switch to work account (short form)
claude-profile -s work

# Switch to personal account (long form)
claude-profile --switch personal

# Quick cycle between accounts
claude-profile -c

# List all profiles
claude-profile -l

# Check current profile
claude-profile --current
```

## Storage

- Profile files are stored in `~/.claude-accounts/`
- Active authentication storage depends on platform:
  - **macOS**: Uses macOS Keychain (service: "Claude Code-credentials")
  - **Linux**: Uses `~/.claude/.credentials.json` (Claude Code's auth file)

## Platform Support

- **macOS**: Uses macOS Keychain for secure token storage
- **Linux**: Uses file-based storage with proper permissions (600)

## Requirements

- Python 3.6+
- macOS or Linux
- Claude Code CLI installed and configured