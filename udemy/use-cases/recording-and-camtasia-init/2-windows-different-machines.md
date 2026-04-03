# Use Case: Recording and Editing Camtasia Projects Across Different Windows Machines

This scenario covers the workflow for recording your lesson on one Windows machine (Machine A) and editing it on another Windows machine (Machine B), using Dropbox, OneDrive, Google Drive, or a USB drive for transfer. The workflow is fully explicit and rationale-rich.

---

> **Note:** You can use any cloud-based file system (Dropbox, OneDrive, Google Drive, etc.) or a USB thumb drive for transferring files. The workflow remains the same as long as you maintain the folder structure and naming conventions described below.

## Prerequisites

1. Dropbox, OneDrive, Google Drive, or a USB drive is available on both Windows machines (either installed or accessed via a web browser).
2. Camtasia (latest version) is installed and activated on both machines. (A free trial is available; this course works with the trial version.)
   > **Important:** If Machine A (recording) has a newer version of Camtasia Recorder than Machine B (editing), you may encounter undefined behavior, file incompatibility, or project corruption. Both machines must have the latest version of Camtasia to ensure reliable, predictable results. Always update Camtasia on both machines before starting a cross-machine workflow.
   >
   > If Machine A has an old version of Camtasia and Machine B has a newer version of Camtasia, this will usually work unless the old version is really, really old. Newer versions of Camtasia are generally backward-compatible with projects created in older versions, but not the other way around.
   >
   > **Best Practice:** To avoid all edge cases and compatibility issues, always ensure Machine B (the editing machine) has the latest Camtasia updates installed before opening any project files.
3. Audiate is installed and activated on the machine doing the editing. The trial version is fully featured and lasts 14 days; you can request an additional week by contacting Camtasia Tech Support. This course works with the trial version.
4. (Optional) neep.com Noise Reducer is highly recommended for preparing audio. This cross-platform local tool reduces background noises such as fans, refrigerators, dogs barking, air conditioning, and noisy neighbors, improving your recording quality before editing. **Note:** neep is payware ($12/month as of April 2026, with the first month free). I do not receive any affiliate rewards for this recommendation. If you try it and subscribe to it, tell them Brother Bill sent you.  After 1,000 notifications, maybe the CEO of neep.com will thank me!
5. (Optional) Adobe Podcast or another audio enhancement tool is available for preparing audio. **Note:** Adobe Podcast is payware (about $10/month as of April 2026, with the first month free).
6. You have sufficient disk space in your cloud folder (or USB drive) and on both machines.

---

> **Note:** Camtasia and its audio workflow (including Audiate and recommended tools) are tuned for voice recording, narration, and spoken content—not for music or singing. If you need to record music, consider using a Digital Audio Workstation (DAW) or specialized music recording software.



---



---

## Baby Steps: Recording, Dehydrating, Transferring, and Rehydrating

### 1. Prepare Your Folder Structure on Machine A (Recording)
1. In File Explorer on Machine A, create the following folder for your lesson: 
   - `C:\Users\<YourName>\Videos\lesson_01\`

> **Transfer Note:** Only the dehydrated Camtasia Project zip file (e.g., `lesson_01_CAMTASIA_PROJECT.zip`) needs to be copied to Dropbox (or your chosen transfer method) for use on Machine B. You do not need to mirror the entire folder structure in Dropbox—just transfer the zip file.

### 2. Launch Camtasia Editor Recorder (on Machine A)
1. Open Camtasia Editor Recorder. (Note: Despite the name, this app does not edit—it only records. The name is a marketing choice, not a description of its function.)
2. Set your capture area, microphone, and camera as needed.
   - If you are using neep.com Noise Reducer, ensure your microphone input in Camtasia Recorder is set to "neep" (not Shure MV7+ or another physical microphone).

**Rationale:** Camtasia Recorder is optimized for screen and voice capture, making it easy to start your lesson. Setting the correct input ensures your audio is processed by neep before recording.

### 3. Do a "Show and Tell" Recording (on Machine A)
1. Click the big red “Rec” button to begin recording.
2. Narrate and demonstrate your lesson content.
3. When finished, click “Stop.”

**Rationale:** Recording in one take keeps the workflow simple and avoids editing headaches later. With Camtasia, it is especially easy to remove repeated phrases or mistakes—just delete the unwanted ("dirty") take and keep the clean one. This makes editing your video almost as easy as editing a text document.

### 4. Open Camtasia and Dehydrate the Project (on Machine A)
1. Click "Open in Editor" to bring up Camtasia Editor.
2. Do not start editing yet. Instead, immediately dehydrate (archive) your raw recording and project files:
   1. In Camtasia, go to File > Export > Zipped Project
   - Save the zip file as `lesson_01_CAMTASIA_PROJECT.zip` in the `Videos\lesson_01` folder:
     `Videos\lesson_01\lesson_01_CAMTASIA_PROJECT.zip`
   - This creates a dehydrated, portable snapshot of your editing state, making it easy to back up or transfer your project.

**Rationale:** Archiving your raw assets and project files before editing ensures you always have a clean, restorable starting point. This is critical for reproducibility and disaster recovery.

### 5. Transfer the Project to Machine B
1. Copy the file `Videos\lesson_01\lesson_01_CAMTASIA_PROJECT.zip` from Machine A to Dropbox (or your chosen transfer method). This is the only file you need to archive and transfer.
   > **Why this works:** Because you are recording on one Windows machine with Camtasia and editing on another Windows machine, you can take this shortcut—just build and transfer `lesson_01_CAMTASIA_PROJECT.zip`. The editing machine only needs this single file to fully restore and continue your project. All required assets are included in the Camtasia Zipped Project file.
2. Wait for Dropbox (or your chosen transfer method) to fully sync the zip file to the cloud or USB drive.
3. On Machine B, ensure Dropbox (or your transfer method) has finished syncing and the zip file is available locally.

**Rationale:** Waiting for full sync ensures that all assets are available and up-to-date on Machine B before you begin editing. Skipping this step can lead to missing files or broken project links.

### 6. Rehydrate and Continue Editing (on Machine B)
1. On Machine B, open the `lesson_01_CAMTASIA_PROJECT.zip` file from the `Videos\lesson_01` folder in Camtasia.
2. Extract and restore your project as needed.
3. Continue editing, exporting, or archiving as desired.

**Rationale:** Rehydrating your project on Machine B allows you to pick up exactly where you left off, with all assets and project files intact and organized.

---

## Concrete Folder Layout for This Use Case

1. **Lesson Folder:**
   - `Dropbox\lesson_01\` (or the equivalent path in your chosen transfer method)
   - This is your main working folder for the lesson. All subfolders for RAW, EDIT, EXPORT, FINAL, and DOCS will be created here.
2. **RAW Folder:**
   - `Dropbox\lesson_01\RAW\`
   - Store your original/raw recordings and project dehydrated (zipped) project files here.
3. **EDIT Folder:**
   - `Dropbox\lesson_01\EDIT\`
   - Save your Camtasia project files (`.tscproj`) and Zipped Projects here.
4. **EXPORT Folder:**
   - `Dropbox\lesson_01\EXPORT\`
   - Use for intermediate exports or files to be further processed.
5. **FINAL Folder:**
   - `Dropbox\lesson_01\FINAL\`
   - Place your finished, deliverable videos and student-facing documents here.
6. **DOCS Folder:**
   - `Dropbox\lesson_01\DOCS\`
   - Keep all internal documentation, workflow notes, and reference materials here.

---

> **Important:** You do not need to understand every step in this workflow. What matters is having the discipline to follow each step in the **exact order shown**. This process is like using a power saw: you must respect the tool and follow all safety protocols, even if you don’t know all the details. Trust the workflow—precision and order are critical for success and safety.

> **Strict Folder Rule:** Every asset for `lesson_01` must be stored inside one of the five subfolders: `RAW`, `EDIT`, `EXPORT`, `FINAL`, or `DOCS`. Do not create any other folders or leave stray files outside these five. This discipline ensures your project stays deterministic, organized, and reproducible.
