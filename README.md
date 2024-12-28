# .vcs Directory Structure

## Overview
The `.vcs` directory contains all the internal files and directories needed to manage the version control system. Below is the detailed structure and purpose of each component, along with additional subcomponents and details.

---

## 1. Store: `store/`
Holds the actual content of the repository in the form of objects (blobs, trees, and commits) and compressed data.

### Subdirectories:
- `blobs/`: Contains individual file data objects.
- `trees/`: Contains directory structure data, referencing blobs and other trees.
- `commits/`: Stores commit metadata and references to parent commits and associated trees.
- `pack/`: Stores compressed and packed objects for efficient storage.

---

## 2. Staging Area: `staging_area/`
Tracks files that are staged for the next commit.

### Files:
- `staged_files.json`: A JSON file listing all files and their statuses (added, modified, deleted) in the staging area.

---

## 3. Metadata: `metadata/`
Stores branch pointers, commit references, and tags.

### Subdirectories:
- `branches/`: Tracks branch names and their associated commit hashes.
- `tags/`: Tracks lightweight and annotated tags.
- `HEAD`: A file pointing to the current branch or commit.

---

## 4. History: `history/`
Logs for actions like commits and merges.

### Files:
- `commits.log`: A chronological log of all commit messages and metadata.
- `merges.log`: A log of all merge operations and resolutions.

---

## 5. Temporary Files: `temp/`
Tracks in-progress operations like merges and stashes.

### Subdirectories:
- `merge_state.json`: Tracks the state of an ongoing merge.
- `stash/`: Stores temporary changes that have been stashed.

---

## 6. Remotes: `remotes/`
Tracks remote repositories and synchronization data.

### Subdirectories:
- `origin/`: Stores data for the default remote repository.
- `upstream/`: Stores data for secondary remote repositories.

---

## 7. Scripts: `scripts/`
Holds executable scripts for various lifecycle hooks.

### Files:
- `pre_commit`: Executed before a commit is finalized.
- `post_merge`: Executed after a merge operation.

---

## 8. Conflicts: `conflicts/`
Tracks and helps resolve merge conflicts.

### Files:
- `file_a.conflict`: Tracks details of conflicts in `file_a`.

---

## 9. Undo: `undo/`
Tracks undo/redo operations for staging and commits.

### Files:
- `stage_undo.log`: Logs staging area changes for undo operations.

---

## 10. Statistics: `stats/`
Tracks repository usage and contributor activity.

### Files:
- `contributors.json`: Stores contributor activity and metadata.
- `file_stats.json`: Tracks statistics for individual files, such as changes and contributors.

---

## 11. Documentation: `docs/`
Stores repository-specific documentation and metadata.

### Files:
- `readme.md`: Repository README file.
- `vcs_internals.md`: Documentation on `.vcs` internals and structure.

---

## 12. Configuration File: `config.json`
Stores repository-specific or user-specific settings.

### Sample Content:
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
```

---

## Full Directory Structure
```
.vcs/
├── store/
│   ├── blobs/
│   ├── trees/
│   ├── commits/
│   ├── pack/
├── staging_area/
│   └── staged_files.json
├── metadata/
│   ├── branches/
│   ├── tags/
│   ├── HEAD
├── history/
│   ├── commits.log
│   ├── merges.log
├── temp/
│   ├── merge_state.json
│   ├── stash/
├── remotes/
│   ├── origin/
│   ├── upstream/
├── scripts/
│   ├── pre_commit
│   ├── post_merge
├── conflicts/
│   ├── file_a.conflict
├── undo/
│   ├── stage_undo.log
├── stats/
│   ├── contributors.json
│   ├── file_stats.json
├── docs/
│   ├── readme.md
│   ├── vcs_internals.md
├── config.json
```

