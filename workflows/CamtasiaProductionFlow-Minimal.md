# Camtasia Production Flow (Minimal)

## Purpose
A concise, deterministic workflow for producing course videos using the canonical 5‑folder pipeline.

## Folder Structure
    RAW/
    ADOBE/
    AUDIATE/
    EDIT/
    OUT/

## Workflow Summary
1. Record
2. Audio Enhancement (ADOBE)
3. Audiate Cleanup (AUDIATE)
4. Camtasia Editing (EDIT)
5. Export (OUT)

## Naming Rules
- lesson_##.mp4  
- lesson_##.wav  
- lesson_##_enhanced.wav  
- lesson_##_audiate.wav  
- lesson_##.srt  

## Canonical Editor
Camtasia for Windows is the authoritative editing environment.

## Detailed Steps

### 1. Record (RAW/)
Record the lesson using your preferred capture method.  
Save the raw recording into the `RAW/` folder using the deterministic naming convention.

### 2. Audio Enhancement (ADOBE/)
Enhance the audio using Adobe tools (e.g., Enhance Speech).  
Export the cleaned WAV into the `ADOBE/` folder with the `_enhanced` suffix.

### 3. Audiate Cleanup (AUDIATE/)
Import the enhanced WAV into Audiate.  
Perform transcript cleanup, silence removal, and timing corrections.  
Export the final WAV + SRT into the `AUDIATE/` folder.

### 4. Camtasia Editing (EDIT/)
Create a new Camtasia project in the `EDIT/` folder.  
Import the Audiate WAV + SRT.  
Assemble the timeline, add callouts, transitions, and visual polish.

### 5. Export (OUT/)
Export the final MP4 into the `OUT/` folder.  
Use deterministic naming so the file can be batch‑processed later.
- **Human steps minimized**  
  Any step requiring human comparison, judgment, or memory must be simplified or eliminated.

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

### Adobe Tools
- Own audio enhancement only.
- Output is a temporary intermediate, not a truth source.

## Why These Boundaries Exist

### 1. Tools do not share a common data model
Audiate, Camtasia, and Adobe tools were not designed to synchronize state.  
Each tool stores timing, captions, and edits in incompatible formats.  
If you edit captions in Camtasia, Audiate has no way to ingest those changes.

### 2. One‑way pipelines prevent data corruption
When a tool cannot round‑trip data, it must be treated as a one‑direction flow.  
This prevents the “silent drift” that happens when two tools disagree about timing.

### 3. Humans are bad at detecting small divergences
Tiny timing mismatches, caption offsets, or waveform shifts are nearly invisible.  
Relying on human comparison leads to the same failure mode as the Ford merge lines:  
high repetition → low vigilance → missed anomalies → corrupted output.

### 4. Determinism requires a single source of truth
If two tools can edit the same type of data, the system becomes non‑deterministic.  
By assigning ownership (Audiate = captions, Camtasia = timeline),  
the workflow becomes predictable and reproducible.

### 5. Folder purity eliminates ambiguity
When every artifact lives in the correct stage folder,  
you always know which file is authoritative and which is intermediate.  
This prevents accidental reuse of stale or incorrect assets.
## Common Failure Modes

### 1. Editing captions in Camtasia
**What happens:**  
Camtasia stores caption timing differently than Audiate.  
If you edit captions here, the SRT and WAV from Audiate no longer match.

**Why it breaks the workflow:**  
You now have two competing “truth sources,” and neither tool can reconcile them.

---

### 2. Re‑importing SRT into Audiate
**What happens:**  
Audiate cannot ingest timing changes from Camtasia.  
It treats imported SRT files as plain text, losing timing metadata.

**Why it breaks the workflow:**  
You destroy the authoritative timing model and create drift.

---

### 3. Mixing files between folders
**What happens:**  
A stale WAV or SRT gets reused because it “looks right.”

**Why it breaks the workflow:**  
Humans are terrible at spotting tiny differences in filenames.  
Folder purity eliminates this entire class of errors.

---

### 4. Renaming files manually
**What happens:**  
A file gets renamed inconsistently or out of sequence.

**Why it breaks the workflow:**  
Automation, batch processing, and future scripts depend on deterministic naming.

---

### 5. Editing audio in Camtasia instead of Audiate
**What happens:**  
Waveform edits in Camtasia do not propagate back to Audiate.

**Why it breaks the workflow:**  
You create timing drift between audio, captions, and transcript.
## Success Criteria

A workflow run is considered successful when all of the following are true:

1. **Only one WAV exists per stage**  
   - `RAW/lesson_##.wav`  
   - `ADOBE/lesson_##_enhanced.wav`  
   - `AUDIATE/lesson_##_audiate.wav`

2. **Captions match the final audio exactly**  
   The SRT exported from Audiate aligns perfectly with the WAV imported into Camtasia.

3. **No edits were made in the wrong tool**  
   - No caption edits in Camtasia  
   - No timing edits outside Audiate  
   - No audio edits outside Adobe or Audiate

4. **Folder purity is intact**  
   Each folder contains only the artifacts appropriate to its stage.

5. **Naming is deterministic**  
   All files follow the lesson_## pattern with correct suffixes.

6. **The OUT/ file is reproducible**  
   Re‑running the workflow with the same inputs produces the same MP4 output.

## Minimal Workflow Diagram

### Key Properties
- **One‑way flow** — no backtracking, no round‑tripping  
- **Each stage produces exactly one artifact**  
- **Each stage consumes exactly one artifact**  
- **No tool edits data owned by another tool**  
- **Folder purity ensures no ambiguity about which file is authoritative**

## Versioning and Change Control

### 1. Workflow files are version‑controlled
All workflow documents (Minimal, Full, Hybrid, State Machine) must be updated through Git commits.  
No ad‑hoc edits outside version control.

### 2. Changes require justification
Every modification to the workflow must include:
- what changed  
- why it changed  
- which failure mode or inefficiency it resolves  

### 3. Backward compatibility is intentional, not accidental
If a change breaks compatibility with older lessons or older tooling,  
the commit message must explicitly state this.

### 4. No silent edits
Never modify workflow logic without updating:
- the Minimal version  
- the Full version  
- the Hybrid version  
- the State Machine version  

All four must remain synchronized.

### 5. Commit messages must be deterministic
Use clear, structured commit messages such as:

### 6. The Minimal version is the canonical baseline
All other workflow documents expand from the Minimal version.  
Changes always propagate outward, never inward.

## Operational Checklist

### Before You Begin
- Confirm folder structure exists (`RAW/`, `ADOBE/`, `AUDIATE/`, `EDIT/`, `OUT/`)
- Confirm deterministic naming for the lesson number
- Close all unrelated Camtasia or Audiate projects

### 1. Record
- Capture lesson audio/video
- Save raw file into `RAW/`

### 2. Enhance Audio
- Open raw WAV in Adobe Enhance
- Export enhanced WAV to `ADOBE/` with `_enhanced` suffix

### 3. Audiate Cleanup
- Import enhanced WAV into Audiate
- Clean transcript, remove filler, fix timing
- Export WAV + SRT to `AUDIATE/`

### 4. Camtasia Assembly
- Create new project in `EDIT/`
- Import Audiate WAV + SRT
- Assemble timeline, add visuals, transitions, callouts

### 5. Export Final
- Export MP4 to `OUT/`
- Verify naming matches deterministic pattern

### 6. Validate Success Criteria
- One WAV per stage  
- Captions match audio  
- No edits in wrong tool  
- Folder purity intact  
- Naming deterministic  
- OUT/ file reproducible

## Glossary of Terms

### Authoritative File
The single file in a workflow stage that represents the “truth.”  
All downstream steps must use this file, and no other file may override it.

### Intermediate File
A temporary artifact produced during processing.  
Intermediate files are never reused once the next stage is complete.

### Folder Purity
A rule stating that each folder contains only the artifacts appropriate to its stage.  
No mixing, no duplicates, no stale files.

### Deterministic Naming
A naming convention where every file follows a predictable pattern:  
`lesson_##`, with suffixes indicating stage (`_enhanced`, `_audiate`, etc.).

### One‑Way Pipeline
A workflow where data flows in a single direction with no backtracking or round‑tripping.  
This prevents drift, corruption, and ambiguity.

### Timing Drift
A mismatch between audio, captions, and transcript caused by editing in the wrong tool  
or mixing files from different stages.

### Truth Source
The tool or file that owns a specific type of data.  
Example: Audiate is the truth source for captions and timing.

### Drift
Any divergence between tools, files, or stages that should be synchronized.  
Drift is always a sign of a broken workflow.

### Stage
A discrete step in the workflow represented by a folder (`RAW/`, `ADOBE/`, `AUDIATE/`, `EDIT/`, `OUT/`).  
Each stage has exactly one input and one output.

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