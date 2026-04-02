# Use Case: Moving Camtasia Projects Between Windows Machines (with Dropbox)

This scenario demonstrates how to move your Camtasia project and all assets between two different Windows machines (or simulate this with a single machine) using Dropbox. The workflow is based on the deterministic, folder-based approach from the single-machine use case.

## Prerequisites

1. Dropbox is installed and set up on both Windows machines (or on your single machine for simulation).
2. Camtasia (latest version) is installed and activated on both machines.
3. Audiate is installed and activated (if used in your workflow).
4. (Optional) neep.com Noise Reducer and Adobe Podcast are available if you use them for audio preparation.
5. You have sufficient disk space in your Dropbox folder and on both machines.

---

> **Note:** This workflow assumes you are following the strict folder structure and naming conventions described in the single-machine use case. All assets must be inside one of the five subfolders (RAW, EDIT, EXPORT, FINAL, DOCS) under your lesson folder (e.g., `lesson_01`).

## Baby Steps: Moving Projects with Dropbox

### 0. Prepare Your Folder Structure in Dropbox
1. In your Dropbox folder, create `lesson_01/`.
2. Inside `lesson_01/`, create these five subfolders:
   1. `RAW`
   2. `EDIT`
   3. `EXPORT`
   4. `FINAL`
   5. `DOCS`

### 1. Record and Save Assets (on Machine A)
1. Follow steps 1–4 from the single-machine use case, but save all files in your Dropbox `lesson_01` folder and subfolders.
2. When you reach the dehydration step, export your Camtasia Zipped Project as `lesson_01_ProjectZipped.zip` in the `EDIT` folder.

### 2. Sync and Transfer
1. Wait for Dropbox to fully sync all files and folders to the cloud.
2. On Machine B, ensure Dropbox has finished syncing and all files are available locally.

### 3. Rehydrate and Continue Editing (on Machine B)
1. Open the `lesson_01_ProjectZipped.zip` file from the `EDIT` folder in Camtasia on Machine B.
2. Extract and restore your project as needed.
3. Continue editing, exporting, or archiving as desired.

---

> **Tip:** You can use this same workflow with OneDrive, Google Drive, or even a USB drive (sneaker-net) by following the same folder and file discipline.

> **Strict Folder Rule:** All assets must remain inside the five subfolders under `lesson_01`. Do not create extra folders or leave stray files outside these folders.

---

**Rationale:** Using Dropbox (or any sync/transfer method) with a deterministic folder structure ensures your project is portable, reproducible, and easy to restore on any Windows machine.
