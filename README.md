[update-readmes]   Mode: rewrite — migrating to template structure...
# caro

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/caro)

<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/caro.git
cd caro
```

## Usage


### Basic Syntax
```bash
caro [OPTIONS] <PROMPT>
```

### Examples
```bash
# Basic command generation
caro "list all files in the current directory"

# With specific shell
caro --shell zsh "find large files"

# JSON output for scripting
caro --output json "show disk usage"

# Adjust safety level
caro --safety permissive "clean temporary files"

# Auto-confirm dangerous commands
caro --confirm "remove old log files"

# Verbose mode with timing info
caro --verbose "search for Python files"
```

### CLI Options

| Option | Description | Status |
|--------|-------------|--------|
| `-s, --shell <SHELL>` | Target shell (bash, zsh, fish, sh, powershell, cmd) | ✅ Implemented |
| `-b, --backend <BACKEND>` | Inference backend (embedded, ollama, exo, vllm) | ✅ Implemented |
| `-m, --model-name <NAME>` | Model name for the backend (e.g., codellama:7b) | ✅ Implemented |
| `--safety <LEVEL>` | Safety level (strict, moderate, permissive) | ✅ Implemented |
| `-o, --output <FORMAT>` | Output format (json, yaml, plain) | ✅ Implemented |
| `-y, --confirm` | Auto-confirm dangerous commands | ✅ Implemented |
| `-v, --verbose` | Enable verbose output with timing | ✅ Implemented |
| `-c, --config <FILE>` | Custom configuration file | ✅ Implemented |
| `--show-config` | Display current configuration | ✅ Implemented |
| `-x, --execute` | Execute the generated command after validation | ✅ Implemented |
| `-i, --interactive` | Interactive mode with step-by-step confirmation | ✅ Implemented |
| `--dry-run` | Show execution plan without running | ✅ Implemented |
| `--force-llm` | Force LLM inference, bypass static pattern matcher | ✅ Implemented |

### Examples (Target Functionality)

```bash
# Simple command generation
caro "compress all images in current directory"

# With specific backend
caro --backend ollama "find large log files"

# Force LLM inference (bypass cached patterns)
caro --backend embedded --force-llm "list files"

# Verbose mode for debugging
caro --verbose "show disk usage"
```

### Shell Integration (Optional)

For the best experience, add caro's shell integration to your shell configuration. This enables the **Edit** feature, which lets you modify generated commands directly in your shell before executing them.

**zsh** - Add to `~/.zshrc`:
```bash
eval "$(caro init zsh)"
```

**bash** - Add to `~/.bashrc`:
```bash
eval "$(caro init bash)"
```

**fish** - Add to `~/.config/fish/config.fish`:
```fish
caro init fish | source
```

After adding the integration, restart your shell or run `source ~/.zshrc` (or equivalent).

#### Using the Edit Feature

When caro generates a command, you'll see three options:

```
Generated command:
  find ~/Downloads -name "*.pdf" -size +10M

Execute this command? (Y)es / (n)o / (e)dit: e
```

Selecting **(e)dit** places the command directly into your shell prompt for editing before execution - just like if you had typed it yourself.

> **Note:** Without shell integration, selecting Edit will copy the command to your clipboard instead.

### Configuration Management

Caro provides a `config` subcommand for managing persistent settings:

```bash
# Show all configuration
caro config show

# Set inference backend
caro config set backend ollama

# Set model name for the backend
caro config set model-name codellama:7b

# Set default shell
caro config set shell zsh

# Set safety level
caro config set safety strict

# Get a specific setting
caro config get backend

# Reset to defaults
caro config reset
```

**Available config keys:**
| Key | Values | Description |
|-----|--------|-------------|
| `backend` | `embedded`, `ollama`, `exo`, `vllm` | Inference backend |
| `model-name` | Any valid model name | Model for the backend (e.g., `codellama:7b`) |
| `shell` | `bash`, `zsh`, `fish`, `sh`, `powershell`, `cmd` | Default target shell |
| `safety` | `strict`, `moderate`, `permissive` | Safety validation level |

**Config file location:** `~/.config/caro/config.toml` (Linux/macOS)

**Priority order:** CLI flags (`--backend`, `--model-name`) > Environment variables > Config file > Auto-detect

### System Assessment

Caro can assess your system's hardware capabilities and recommend optimal model configurations:

```bash
# Basic assessment
caro assess

# Export to JSON
caro assess --export json --output assessment.json

# Export to Markdown
caro assess --export markdown --output assessment.md
```

The assessment command detects:
- CPU architecture, cores, and model
- Total and available memory (RAM)
- GPU vendor, model, and VRAM (if available)
- Recommended models and backends based on your hardware

**Supported Platforms**: macOS, Linux, Windows

**Backends**: MLX (Apple Silicon), CUDA (NVIDIA), CPU-only

For more details, run `caro assess --help`.

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/caro`](https://github.com/Interested-Deving-1896/caro) and mirrored through:

```
Interested-Deving-1896/caro  ──►  OpenOS-Project-OSP/caro  ──►  OpenOS-Project-Ecosystem-OOC/caro
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
_Contributors pending._
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream fork._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## License

<!-- AI:start:license -->
[AGPL-3.0](https://github.com/Interested-Deving-1896/caro/blob/main/LICENSE) © 2026 [Interested-Deving-1896](https://github.com/Interested-Deving-1896)
<!-- AI:end:license -->
