# Camtasia Production Flow (Hybrid – Expanded Minimal)

## Purpose

A deterministic workflow that expands the Minimal version with slightly more operational detail while preserving clarity, simplicity, and strict tool boundaries. The Hybrid version is designed for daily use and delegation without introducing unnecessary complexity.

## Folder Structure

```
RAW/
ADOBE/
AUDIATE/
EDIT/
OUT/
```

Each folder represents a discrete stage in the workflow.  
Folder purity ensures that every artifact is always in the correct place, eliminating ambiguity and preventing accidental reuse of stale files.

## Workflow Summary

The workflow moves through five deterministic stages:

1. Record           → RAW
2. Enhance Audio    → ADOBE
3. Audiate Cleanup  → AUDIATE
4. Camtasia Editing → EDIT
5. Export Final     → OUT

Each stage consumes one authoritative file and produces one authoritative file.

### Do NOT:

- Do NOT skip stages or reorder them.
- Do NOT mix files between stages.
- Do NOT create multiple outputs for a single stage.
- Do NOT return to a previous stage once the next stage has begun.

## Stage 1 — RAW (Recording)

This stage captures the initial screen recording and microphone audio.  
The goal is to produce a clean, unedited source file that moves directly into audio enhancement.

### Inputs

- Live screen recording
- Live microphone audio

### Output

- RAW/<lesson>.mp4

### Rules

- Record in one continuous take whenever possible.
- Keep the microphone gain consistent across lessons.
- Stop and restart the recording if a major error occurs.

### Do NOT:

- Do NOT edit inside the RAW stage.
- Do NOT rename the file after recording.
- Do NOT store multiple RAW versions of the same lesson.
- Do NOT place any non‑recording files in the RAW folder.

## Stage 2 — ADOBE (Audio Enhancement)

This stage enhances the microphone audio using Adobe’s speech tools.  
The goal is to produce a cleaner, more consistent audio track before entering Audiate.

### Input

- RAW/<lesson>.mp4

### Output

- ADOBE/<lesson>.wav

### Rules

- Use the same Adobe enhancement preset for all lessons.
- Export only the enhanced audio (WAV), not a video.
- Keep filenames identical to the RAW lesson name.

### Do NOT:

- Do NOT modify the RAW video.
- Do NOT export M4A or any lossy format.
- Do NOT change the lesson name during export.
- Do NOT store multiple Adobe outputs for the same lesson.

## Stage 3 — AUDIATE (Transcript Cleanup & Timing)

This stage cleans up the enhanced audio using Audiate’s transcript‑based editing.  
The goal is to remove filler words, tighten pacing, and produce a timing‑accurate WAV for Camtasia.

### Input

- ADOBE/<lesson>.wav

### Output

- AUDIATE/<lesson>.wav

### Rules

- Use the same Audiate cleanup preset for all lessons.
- Remove filler words only when they do not change meaning.
- Remove any audio spikes or transient noise artifacts that slipped through recording or enhancement.
- Preserve natural pacing unless it harms clarity.
- Export a WAV file with the exact same lesson name.

### Do NOT:

- Do NOT edit the video in this stage.
- Do NOT export M4A or any lossy format.
- Do NOT change timing manually.
- Do NOT create multiple Audiate versions of the same lesson.

## Stage 4 — EDIT (Camtasia, governed by CAOL)

Camtasia functions as a *smart container* in this workflow.  
It assembles media, preserves timing, maintains track relationships, and exports the final lesson.  
It must NOT modify audio timing, pacing, content, or structure.  
All timing and content edits are performed upstream in Audiate.

Camtasia’s role is strictly limited to the CAOL (Camtasia Allowed Operations List).  
Any operation outside CAOL is forbidden to prevent timing drift, audio corruption,
and nondeterministic behavior.

### Inputs

- RAW/<lesson>.mp4
- AUDIATE/<lesson>.wav

### Output

- EDIT/<lesson>.tscproj

### Allowed Operations (CAOL)

Camtasia may ONLY perform the following tasks:

1. Import audio files and MP4 files (including OBS Studio recordings).
2. Rehydrate incoming Camtasia assets, including:
   - .trec and .cmrec recordings from Camtasia Recorder (Mac or Windows),
   - Zipped Project exports created by Camtasia,
   - Manually dehydrated lesson folders following the 5‑folder structure.
3. Send the audio track to Audiate **once** to create the initial .audiate session file.  
   All further audio or transcript edits must be done by reopening the .audiate file directly.
4. Pass the audio track to Audiate for transcript-based editing.
5. Perform CRUD operations on timeline tracks (add, remove, reorder).
6. Silence audio on a track (without altering timing).
7. Remove Dynamic Captions.
8. Export the final lesson as MP4 or MP4 with Smart Player.

### Rules

- Place the Audiate WAV on the timeline and disable the audio from the RAW video.
- Ensure the WAV and video start at the exact same timestamp (0:00.000).
- Lock the audio track immediately after alignment.
- Perform **no timing edits** in Camtasia. All pacing, cuts, and content edits must be done in Audiate.
- Add only non-destructive visual elements (zoom, callouts, cursor effects) that do not alter timing.
- Keep all media files inside the project folder to avoid broken links.
- Save frequently using the same project filename.

### Do NOT:

- Do NOT cut, trim, ripple-delete, or modify timing in any way.
- Do NOT adjust pacing or remove sections (these belong in Audiate).
- Do NOT modify audio except for silencing a track.
- Do NOT export audio from Camtasia (Audiate is the single timing authority).
- Do NOT move or rename media files after importing them.
- Do NOT create multiple project files for the same lesson.

## Stage 5 — OUT (Export Final)

This stage produces the final deliverable for distribution or upload. The goal is to export a single, authoritative MP4 file or set of MP4 + Smart Player files that matches the lesson name and is ready for delivery.

### Input

- EDIT/<lesson>.tscproj

### Output

- OUT/<lesson>.mp4

### Rules

1. Export using the standard Camtasia MP4 preset (or MP4 + Smart Player).
2. Ensure the exported file matches the lesson name exactly.
3. Verify audio/video sync and overall quality before delivery.
4. Store only the final, approved version in the OUT folder.

### Do NOT:

- Do NOT export multiple versions for the same lesson.
- Do NOT rename the file after export.
- Do NOT store drafts or test exports in the OUT folder.
- Do NOT modify the OUT file after export; repeat the workflow if changes are needed.

---

## Revision Workflow (Post-Release Fixes)

If an error (e.g., a typo in captions) is discovered after export, follow these steps:

1. **Restore Authoritative Project Files**
   - Retrieve the original `EDIT/<lesson>.tscproj` and all associated media from your archive or OUT folder.
   - If the project was archived, unzip or restore it to the EDIT folder.

2. **Open in Camtasia and Audiate**
   - Launch Camtasia and open the `.tscproj` file.
   - Ensure all media links are intact (RAW video, AUDIATE WAV, etc.).
   - If transcript or audio edits are needed, launch Audiate and open the corresponding `.audiate` file from the AUDIATE folder.

3. **Make the Correction**
   - The human video editor may make any edits permitted in the original workflow for this stage. Edit captions or other non-destructive elements as needed.
   - Any edit allowed in the original workflow for this stage is also allowed during revision—including changes to audio timing, structure, or content.

4. **Re-export the Final Resource**
   - Export the corrected lesson to `OUT/<lesson>.mp4` (or MP4 + Smart Player), overwriting the previous version.
   - Verify the correction and overall quality.

   - If required, increment the version number in the filename (e.g., `<lesson>_v2.mp4`) and update documentation.

6. **Document the Change**
   - Log the revision, reason, and date in your change tracking system or a simple text file.

### Do NOT:
- Do NOT edit the RAW or ADOBE artifacts.
- AUDIATE files are expected to change over time as typos are fixed.
- Do NOT skip quality checks after export.
