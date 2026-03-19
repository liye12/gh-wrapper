# gh-wrapper

A lightweight gh CLI wrapper that proxies GitHub CLI commands to the GitHub REST API via curl.

## Why

On some environments (restricted Linux containers), installing the official gh CLI binary is not possible. This wrapper provides a drop-in replacement for common commands by calling the GitHub REST API directly with curl.

## Supported Commands

| Command | Description |
|---------|-------------|
| gh auth status | Show current authenticated user |
| gh api \<path\> | Call any GitHub REST API endpoint |
| gh pr checks \<num\> --repo \<owner/repo\> | Show PR check runs |
| gh run list --repo \<owner/repo\> --limit N | List recent workflow runs |
| gh run view \<id\> --repo \<owner/repo\> | Show workflow run details |

## Setup

1. Generate a GitHub PAT with repo, workflow, and read:user scopes
2. Edit the TOKEN variable at the top of gh-wrapper
3. chmod +x gh-wrapper && ./gh-wrapper auth status

## Quick Reference

./gh-wrapper auth status
./gh-wrapper api /user
./gh-wrapper run list --repo owner/repo --limit 10

MIT
