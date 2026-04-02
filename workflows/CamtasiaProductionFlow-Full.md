# Camtasia Production Flow (Full)

## Purpose
A comprehensive, deterministic workflow for Camtasia-based course production, expanding on the Minimal version with detailed rationale, operational notes, and edge-case handling.

## Folder Structure
    RAW/
    ADOBE/
    AUDIATE/
    EDIT/
    OUT/

## Workflow Summary
1. Record (RAW)
2. Audio Enhancement (ADOBE)
3. Audiate Cleanup (AUDIATE)
4. Camtasia Editing (EDIT)
5. Export (OUT)

## Naming Rules
- lesson_##.mp4
- lesson_##.wav
- lesson_##_audio_enhanced.wav
- lesson\_##_audiate.wav
- lesson_##.srt

## Canonical Editor
Camtasia for Windows is the authoritative editing environment.

---

## Detailed Steps

### 1. Record (RAW/)
- Use a consistent capture method (e.g., OBS, Camtasia Recorder).
- Save the raw recording into the `RAW/` folder using the deterministic naming convention.
- Confirm audio and video quality before proceeding.
- If a major error occurs, restart the recording—do not splice or edit in this stage.

### 2. Audio Enhancement (ADOBE/)
- Enhance the audio using Adobe tools (e.g., Enhance Speech).
- Export the cleaned WAV into the `ADOBE/` folder with the `_audio_enhanced` suffix.
- Use the same enhancement preset for all lessons to ensure consistency.
- Do not modify the original RAW file.

### 3. Audiate Cleanup (AUDIATE/)
- Import the audio enhanced WAV into Audiate.
- Perform transcript cleanup, silence removal, and timing corrections.
- Remove filler words only if they do not change meaning.
- Export the final WAV + SRT into the `AUDIATE/` folder.
- All caption edits must occur in Audiate.
- Never import SRT back into Audiate.

### 4. Camtasia Editing (EDIT/)
- Create a new Camtasia project in the `EDIT/` folder.
- Import the Audiate WAV + SRT.
- Assemble the timeline, add callouts, transitions, visual effects, and overlays (e.g., cursor highlighting, animated/non-animated shapes, arrows, titles) that do not alter timing or add/remove clips.
- Never modify captions inside Camtasia.
- Never expect changes to sync back to Audiate.
- Keep all media files inside the project folder to avoid broken links.

### 5. Export (OUT/)
- Export the final MP4 into the `OUT/` folder.
- Use deterministic naming so the file can be batch‑processed later.
- Verify audio/video sync and overall quality before delivery.

---

## Tool Boundaries

### Audiate
- Owns transcript, timing, and caption truth.
- All caption edits must occur here.
- Exports authoritative WAV + SRT.
- Never import SRT back into Audiate.

### Camtasia
- Owns timeline assembly and visual editing.
- Imports WAV + SRT from Audiate.
- Never modify captions inside Camtasia.
- Never expect changes to sync back to Audiate.

### Camtasia Allowed Operations List (CAOL)
Camtasia may ONLY perform the following tasks:
1. Import audio files and MP4 files (including OBS Studio recordings).
2. Rehydrate incoming Camtasia assets, including:
    - .trec and .cmrec recordings from Camtasia Recorder (Mac or Windows),
    - Zipped Project exports created by Camtasia,
    - Manually dehydrated lesson folders following the 5‑folder structure.
3. Send the audio track to Audiate **once** to create the initial .audiate session file. All further audio or transcript edits must be done by reopening the .audiate file directly.
4. Pass the audio track to Audiate for transcript-based editing.
5. Perform CRUD operations on timeline tracks (add, remove, reorder).
6. Add visual effects and overlays (e.g., cursor highlighting, animated/non-animated shapes, arrows, titles, callouts) that do not alter timing or add/remove clips.
7. Add transitions (e.g., fades, wipes) only if they do not change the duration or timing of any clip (no ripple edits or trimming).
8. Remove Dynamic Captions.
9. Export the final lesson as MP4 or MP4 with Smart Player.

**Rules:**
- Place the Audiate WAV on the timeline and disable the audio from the RAW video.
- Ensure the WAV and video start at the exact same timestamp (0:00.000).
- Lock the audio track immediately after alignment.
- Perform **no timing edits** in Camtasia. All pacing, cuts, and content edits must be done in Audiate.
- Add only non-destructive visual elements (zoom, callouts, cursor effects, overlays, transitions as above) that do not alter timing or clip structure.
- Keep all media files inside the project folder to avoid broken links.
- Save frequently using the same project filename.

**Do NOT:**
- Do NOT cut, trim, ripple-delete, or modify timing in any way.
- Do NOT adjust pacing or remove sections (these belong in Audiate).
- Do NOT modify audio except for silencing a track.
- Do NOT export audio from Camtasia (Audiate is the single timing authority).
- Do NOT move or rename media files after importing them.
- Do NOT create multiple project files for the same lesson.
- Own audio enhancement only.
- Output is a temporary intermediate, not a truth source.

---

## Rationale and Edge-Case Handling

- If a file is missing or corrupted at any stage, return to the previous stage and regenerate the artifact.
- If a typo or error is found after export, follow the Revision Workflow (see below).
- Folder purity: Each folder contains only the artifacts appropriate to its stage. No mixing, no duplicates, no stale files.
- Deterministic naming: All files follow the lesson_## pattern with correct suffixes.
- One-way pipeline: No backtracking or round-tripping between tools.

---

## Revision Workflow (Post-Release Fixes)

If a correction is needed after export (e.g., a typo in captions):

1. Restore the authoritative Camtasia project (`EDIT/lesson_##.tscproj`) and all associated media.
2. Open the project in Camtasia. If transcript or audio edits are needed, open the corresponding Audiate file from `AUDIATE/` in Audiate.
3. Make any edits allowed by the original workflow for each tool and stage. Captions and timing edits should be made in Audiate; timeline and visuals in Camtasia.
4. Export the corrected lesson to `OUT/lesson_##.mp4` (or MP4 + Smart Player), overwriting the previous version if appropriate.
5. Optionally increment the version number in the filename (e.g., `lesson_##_v2.mp4`) and update documentation if required.
6. Log the revision and reason for traceability.

### Do NOT:
- Do NOT edit the RAW or ADOBE artifacts.
- AUDIATE files are expected to change over time as typos are fixed.
- Do NOT skip quality checks after export.
