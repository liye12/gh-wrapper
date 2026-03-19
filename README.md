# gh-wrapper

A lightweight `gh` CLI wrapper that proxies GitHub CLI commands to the GitHub REST API via `curl`.

## Why

On some environments (restricted Linux containers), installing the official `gh` CLI binary is not possible. This wrapper provides a drop-in replacement for common commands via the GitHub REST API.

## Supported Commands

| Command | Description |
|---------|-------------|
| `gh auth status` | Show current authenticated user |
| `gh api <path>` | Call any GitHub REST API endpoint |
| `gh pr checks <num> --repo <owner/repo>` | Show PR check runs |
| `gh run list --repo <owner/repo> --limit N` | List recent workflow runs |
| `gh run view <id> --repo <owner/repo>` | Show workflow run details |

## Setup

### 1. Obtain a GitHub Personal Access Token (PAT)

Generate a PAT at **GitHub → Settings → Developer Settings → Personal Access Tokens → Generate new token (classic)**.

Required scopes: `repo`, `workflow`, `read:user`

### 2. Set Your Token

Export your token as an environment variable before running:

```bash
export GITHUB_TOKEN="ghp_your_token_here"
# or
export TOKEN="ghp_your_token_here"
```

### 3. Run

```bash
chmod +x gh-wrapper
./gh-wrapper auth status
./gh-wrapper api /user
./gh-wrapper run list --repo owner/repo --limit 10
```

## License

MIT
