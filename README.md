# OasisTools

🛠️ **Central hub for all Oasis tools - program installer and update manager**

## Overview

OasisTools is a program distribution hub that allows you to:
- Browse and install programs from one central location
- Automatically check for and install updates
- Manage all your installed Oasis programs

## For Users

Download the OasisTools Hub installer from the [Releases](https://github.com/oasisdfg/oasistools/releases) page.

## For Development

### Repository Structure

```
oasistools/
├── manifest.json    # Master list of all available programs
├── icons/           # Program icons (PNG, 64x64 recommended)
└── README.md
```

### manifest.json Format

Each program entry requires:

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier (lowercase, hyphens) |
| `name` | string | Display name |
| `description` | string | Short description |
| `icon` | string | Path to icon file |
| `repo` | string | GitHub repo in `owner/repo` format |
| `category` | string | Program category |
| `featured` | boolean | Show in featured section |

### How It Works

1. The hub fetches `manifest.json` from this repo
2. For each program, it queries GitHub Releases API for the latest version
3. Downloads are pulled directly from GitHub Release assets

## Adding a New Program

1. Create a GitHub Release in your program's repo with a `.zip` asset
2. Add an entry to `manifest.json` in this repo
3. Add an icon to the `icons/` folder