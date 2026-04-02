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
**Symptoms:**
1. Exported video has mismatched audio and visuals, or captions drift out of alignment.

**Likely Causes:**
1. Timing edits made in Camtasia after audio was finalized in Audiate
2. Ripple-deletes, clip cuts, or timeline changes in Camtasia
3. Importing the wrong WAV or SRT file

**Fix:**
1. Revert to the last synced version from Audiate and re-import into Camtasia
2. Ensure all timing and transcript edits are done in Audiate only
3. Lock the audio track after alignment in Camtasia

---

## 2. Broken or Missing Media Links
**Symptoms:**
1. Camtasia project shows missing media, or files won’t load.

**Likely Causes:**
1. Media files moved or renamed outside Camtasia
2. Files stored outside the project folder

**Fix:**
1. Restore files to their original location and relink in Camtasia
2. Always keep all media inside the project folder

---

## 3. Caption Timing Errors
**Symptoms:**
1. Captions appear at the wrong time or are out of sync with audio.

**Likely Causes:**
1. Captions edited in Camtasia instead of Audiate
2. SRT file not updated after audio changes

**Fix:**
1. Edit and export captions in Audiate only
2. Re-import the updated SRT into Camtasia

---

## 4. Export Fails or Crashes
**Symptoms:**
1. Export process hangs, fails, or produces a corrupt file.

**Likely Causes:**
1. Corrupted media or project file
2. Insufficient disk space or memory
3. Unsupported file formats

**Fix:**
1. Remove or replace problematic media
2. Save and restart Camtasia
3. Ensure enough free disk space

---

## 5. Project File Corruption
**Symptoms:**
1. Camtasia project won’t open or crashes on load.

**Likely Causes:**
1. File corruption due to crashes or disk errors
2. Version mismatch between Camtasia installations

**Fix:**
1. Restore from a recent backup or versioned file
2. Open on another machine or Camtasia version if possible

---

## 6. Naming or Folder Issues
**Symptoms:**
1. Automation scripts fail, files are missing, or batch processing breaks.

**Likely Causes:**
1. Files not following naming conventions
2. Files in the wrong folder

**Fix:**
1. Rename files to match the documented conventions
2. Move files to the correct folder

---

## 7. Versioning Confusion
**Symptoms:**
1. Multiple versions of the same file, uncertainty about which is current.

**Likely Causes:**
1. Inconsistent version suffixes (e.g., _v2, _final, _edit)
2. Old files not deleted or archived

**Fix:**
1. Use a clear, documented versioning scheme
2. Keep only the latest authoritative file in each folder

---

## 8. Automation Script Failures
**Symptoms:**
1. Scripts for batch processing, renaming, or exporting don’t work as expected.

**Likely Causes:**
1. Deviations from naming or folder structure
2. Unsupported file formats or characters

**Fix:**
1. Audit files for compliance with conventions
2. Update scripts or file formats as needed

---

## 9. General Tips
1. Save and back up your work frequently
2. Document any exceptions or customizations in your README
3. When in doubt, revert to the last known good state
4. Ask for help early—small issues are easier to fix than big ones

---

_Last updated: April 2, 2026_
