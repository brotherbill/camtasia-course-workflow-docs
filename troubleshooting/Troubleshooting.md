# Troubleshooting Guide

This guide provides solutions to common issues encountered in the Camtasia + Audiate production workflow. Each entry includes symptoms, likely causes, and deterministic fixes to get you back on track quickly.

---

## Table of Contents
1. Audio/Video Out of Sync
2. Broken or Missing Media Links
3. Caption Timing Errors
4. Export Fails or Crashes
5. Project File Corruption
6. Naming or Folder Issues
7. Versioning Confusion
8. Automation Script Failures
9. General Tips

---

## 1. Audio/Video Out of Sync
**Symptoms:** Exported video has mismatched audio and visuals, or captions drift out of alignment.

**Likely Causes:**
- Timing edits made in Camtasia after audio was finalized in Audiate
- Ripple-deletes, clip cuts, or timeline changes in Camtasia
- Importing the wrong WAV or SRT file

**Fix:**
- Revert to the last synced version from Audiate and re-import into Camtasia
- Ensure all timing and transcript edits are done in Audiate only
- Lock the audio track after alignment in Camtasia

---

## 2. Broken or Missing Media Links
**Symptoms:** Camtasia project shows missing media, or files won’t load.

**Likely Causes:**
- Media files moved or renamed outside Camtasia
- Files stored outside the project folder

**Fix:**
- Restore files to their original location and relink in Camtasia
- Always keep all media inside the project folder

---

## 3. Caption Timing Errors
**Symptoms:** Captions appear at the wrong time or are out of sync with audio.

**Likely Causes:**
- Captions edited in Camtasia instead of Audiate
- SRT file not updated after audio changes

**Fix:**
- Edit and export captions in Audiate only
- Re-import the updated SRT into Camtasia

---

## 4. Export Fails or Crashes
**Symptoms:** Export process hangs, fails, or produces a corrupt file.

**Likely Causes:**
- Corrupted media or project file
- Insufficient disk space or memory
- Unsupported file formats

**Fix:**
- Remove or replace problematic media
- Save and restart Camtasia
- Ensure enough free disk space

---

## 5. Project File Corruption
**Symptoms:** Camtasia project won’t open or crashes on load.

**Likely Causes:**
- File corruption due to crashes or disk errors
- Version mismatch between Camtasia installations

**Fix:**
- Restore from a recent backup or versioned file
- Open on another machine or Camtasia version if possible

---

## 6. Naming or Folder Issues
**Symptoms:** Automation scripts fail, files are missing, or batch processing breaks.

**Likely Causes:**
- Files not following naming conventions
- Files in the wrong folder

**Fix:**
- Rename files to match the documented conventions
- Move files to the correct folder

---

## 7. Versioning Confusion
**Symptoms:** Multiple versions of the same file, uncertainty about which is current.

**Likely Causes:**
- Inconsistent version suffixes (e.g., _v2, _final, _edit)
- Old files not deleted or archived

**Fix:**
- Use a clear, documented versioning scheme
- Keep only the latest authoritative file in each folder

---

## 8. Automation Script Failures
**Symptoms:** Scripts for batch processing, renaming, or exporting don’t work as expected.

**Likely Causes:**
- Deviations from naming or folder structure
- Unsupported file formats or characters

**Fix:**
- Audit files for compliance with conventions
- Update scripts or file formats as needed

---

## 9. General Tips
- Save and back up your work frequently
- Document any exceptions or customizations in your README
- When in doubt, revert to the last known good state
- Ask for help early—small issues are easier to fix than big ones

---

_Last updated: April 2, 2026_
