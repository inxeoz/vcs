# vcs
version control system alternative to git written in rust


# .vcs Directory Structure

## Overview
The `.vcs` directory contains all the internal files and directories needed to manage the version control system. Below is the detailed structure and purpose of each component.

---

## 1. Store: `store/`
Holds the actual content of the repository in the form of objects (blobs, trees, and commits) and compressed data.


---

## 2. Staging Area: `staging_area/`
Tracks files that are staged for the next commit.


---

## 3. Metadata: `metadata/`
Stores branch pointers, commit references, and tags.


---

## 4. History: `history/`
Logs for actions like commits and merges.


---

## 5. Temporary Files: `temp/`
Tracks in-progress operations like merges and stashes.


---

## 6. Remotes: `remotes/`
Tracks remote repositories and synchronization data.


---

## 7. Scripts: `scripts/`
Holds executable scripts for various lifecycle hooks.


---

## 8. Conflicts: `conflicts/`
Tracks and helps resolve merge conflicts.


---

## 9. Undo: `undo/`
Tracks undo/redo operations for staging and commits.


---

## 10. Statistics: `stats/`
Tracks repository usage and contributor activity.


---

## 11. Documentation: `docs/`
Stores repository-specific documentation and metadata.


---

## 12. Configuration File: `config.json`
Stores repository-specific or user-specific settings.


**Sample Content**:
```json
{
    "user": {
        "name": "John Doe",
        "email": "john.doe@example.com"
    },
    "core": {
        "hash_algorithm": "sha256",
        "compression": "gzip"
    },
    "repository": {
        "default_branch": "main"
    }
}
