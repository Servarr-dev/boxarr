Here’s a clean, quick README you can drop in:

---

# Boxarr

**Boxarr** is the library lifecycle layer for the *arr stack.

It turns the usual scattered tools (qBittorrent → Sonarr/Radarr → media servers) into a coherent daily system: claim completed downloads, stage them, rename, distribute to live libraries, inventory what you actually have, align naming, repair broken files, strip/enrich metadata, and optionally share refined metadata with other Boxarr nodes over I2P.

### Core idea

Boxarr should understand your library and workflow instead of forcing you to understand every path, tool, and service.

### Quick start

```bash
cd /path/to/Boxarr
python boxarr.py --connect
python boxarr.py --daily
python boxarr.py --media --scan
python boxarr.py --gui          # optional local dashboard
```

Default mode is **execute**. Add `--dryrun` when you only want a plan.

### Main verbs

| Command | Purpose |
|---------|---------|
| `--daily` | Full morning pipeline (steps 1–10 + purge) |
| `--media --scan` | Inventory libraries → per-show workbooks + JSON |
| `--seek` | Isolate *arr searches to current core / year / backlog |
| `--align` | Light naming + profile fixes |
| `--repair --check` | Diagnose missing / unreachable / broken files |
| `--strip-metadata` | Clear internal tags (or per-service variants) |
| `--dupes` | Recommend which copy to keep (never deletes) |
| `--mesh` | I2P peer network for refined metadata |
| `--purge` | Housekeeping (old actions + logs) |

### Key concepts

- **Staging** → pure bracket folders like `[Stagging]` are temporary ops areas
- **Core tags** → `YYYY-CC` (01 Winter … 04 Fall) drive what gets searched
- **Mesh** → nodes share refined metadata only (no media files, no paths). Identities are randomized; each client decides its own seed duty based on estimated swarm size

### Status

Early development. Standalone Python CLI + optional local GUI. Designed to eventually ship as a single executable.

---

Want a slightly longer or more marketing-oriented version?
