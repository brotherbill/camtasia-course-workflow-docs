# Use Case: Recording on Windows (One Machine)

This scenario covers the most common workflow: recording your lesson and preparing to edit on the same Windows machine using Camtasia.

## Prerequisites

1. Camtasia (latest version) is installed and activated on your Windows machine. (A free trial is available; this course works with the trial version.)
2. Audiate is installed and activated. (A free trial is available; this course works with the trial version.)
3. (Optional) neep.com Noise Reducer is highly recommended for preparing audio. This cross-platform local tool reduces background noises such as fans, refrigerators, dogs barking, air conditioning, and noisy neighbors, improving your recording quality before editing. **Note:** neep is payware ($12/month as of April 2026, with the first month free). I do not receive any affiliate rewards for this recommendation. If you try it and subscribe to it, tell them Brother Bill sent you.  After 1,000 notifications, maybe the CEO of neep.com will thank me! 
4. (Optional) Adobe Podcast or another audio enhancement tool is available for preparing audio. **Note:** Adobe Podcast is payware (about $10/month as of April 2026, with the first month free).
5. You have sufficient disk space in your Videos/ and Documents/ folders.

---

> **Note:** Camtasia and its audio workflow (including Audiate and recommended tools) are tuned for voice recording, narration, and spoken content—not for music or singing. If you need to record music, consider using a Digital Audio Workstation (DAW) or specialized music recording software.

> **Platform Note:** On Windows, Camtasia uses the term "Zipped Project" for its special archive format (e.g., lesson_01_CAMTASIA_PROJECT.zip). On Mac, the equivalent is often just called "Project" or uses a different archive format. Be aware of these naming and compatibility differences if you work across platforms.

## Baby Steps: Recording, Dehydrating, and Rehydrating

### 0. Prepare Your Folder Structure
1. In File Explorer, create the following folder for your lesson:
   - `C:\Users\<YourName>\Videos\lesson_01\`
2. Inside `lesson_01`, create these five subfolders:
   1. `RAW`
   2. `EDIT`
   3. `EXPORT`
   4. `FINAL`
   5. `DOCS`

**Rationale:** Setting up your folder structure before you begin ensures all assets are organized from the start and makes every step that follows deterministic and easy to follow.

### 1. Launch Camtasia Editor Recorder
1. Open Camtasia Editor Recorder. (Note: Despite the name, this app does not edit—it only records. The name is a marketing choice, not a description of its function.)
2. Set your capture area, microphone, and camera as needed.
   - If you are using neep.com Noise Reducer, ensure your microphone input in Camtasia Recorder is set to "neep" (not Shure MV7+ or another physical microphone).
3. Position your microphone for recording.

**Rationale:** Camtasia Recorder is optimized for screen and voice capture, making it easy to start your lesson. Setting the correct input ensures your audio is processed by neep before recording.

### 2. Do a "Show and Tell" Recording
1. Click the big red “Rec” button to begin recording.
2. Narrate and demonstrate your lesson content.
3. When finished, click “Stop.”

**Rationale:** Recording in one take keeps the workflow simple and avoids editing headaches later. With Camtasia and Audiate, it is especially easy to remove repeated phrases or mistakes—just delete the unwanted ("dirty") take and keep the clean one. This makes editing your video almost as easy as editing a text document.

### 3. Save the Raw Recording
1. When prompted, save your recording as `lesson_01.trec` directly in your project’s `Videos\lesson_01\RAW\` folder. (The `RAW\` folder is the canonical location for all raw assets.)
2. Click Save
3. This will open Camtasia Rev app.

**Rationale:** Saving each lesson’s raw recording directly in the `Videos\lesson_01\RAW\ folder keeps your project organized, prevents clutter, and makes it easy to manage multiple recordings and assets. Building this habit early ensures your workflow stays clean and scalable as your project grows.

### 4. Open Camtasia and Dehydrate the Project
1. Click "Open in Editor"
   1. This brings up Camtasia Editor.

2. File > Save
    - Save your project as `lesson_01.tscproj` in the `EDIT` folder:
       `C:\Users\<YourName>\Videos\lesson_01\EDIT\lesson_01.tscproj`
   - This keeps your editable Camtasia project file organized and separate from your raw assets.

3. Do not start editing yet. Instead, immediately dehydrate (archive) your raw recording and project files:
   1. In Camtasia, go to File > Export > Zipped Project
    - Save the zip file as `lesson_01_CAMTASIA_PROJECT.zip` in the `EDIT` folder:
       `C:\Users\<YourName>\Videos\lesson_01\EDIT\lesson_01_CAMTASIA_PROJECT.zip`
   - This creates a dehydrated, portable snapshot of your editing state, making it easy to back up or transfer your project.

### 5. Archive lesson_01 to Dropbox

1. In File Explorer, navigate to:  \Videos\lesson_01\

2. Select all files with Control + A

3. Right-click on any of the selected folders, then select: "Compress to..." > ZIP File

4. Rename that file to: `lesson_01_ALL.zip`

5. Upload that file from Machine A to Dropbox (or your chosen transfer method). This is the only file you need to archive and transfer.
   1. I saved it in DropBox root folder `Camtasia and Audiate course`

6. Wait for Dropbox (or your chosen transfer method) to fully sync the zip file to the cloud or USB drive.

7. 

**Rationale:** Archiving your raw assets and project files before editing ensures you always have a clean, restorable starting point. This is critical for reproducibility and disaster recovery.

---

> **Important Distinction:**
> - A regular zip file (e.g., `lesson_01_FULL.zip`) contains all files and folders in your `lesson_01` directory—this is a generic archive for backup or transfer.
> - The Camtasia Project zip file (`lesson_01_CAMTASIA_PROJECT.zip`) is created via Camtasia's File > Export > Zipped Project. It contains only the Camtasia project and its linked assets, in a format Camtasia can restore directly. Do not confuse these two: only the Camtasia Project zip can be opened natively by Camtasia for editing.

---

> **Dehydration & Rehydration Terminology (DDD):**
> - **lesson_01_ALL.zip**: This is a full dehydration of your entire lesson_01 folder—all files and subfolders are zipped. Rehydration means unzipping to restore everything exactly as it was. Use this for complete backups, transfers, or archiving the entire project state.
> - **lesson_01_CAMTASIA_PROJECT.zip**: This is a Camtasia-specific dehydration, created via File > Export > Zipped Project. Rehydration means opening this file in Camtasia to restore the project and its linked assets. This does not restore Audiate projects or non-Camtasia files—rehydrating Audiate assets may require a separate export/import or backup process.

> **Note:** If you use Audiate, ensure you also export or back up your Audiate project files separately, as they are not included in the Camtasia Project zip. Store these in the RAW or EDIT folder as appropriate, and consider including them in lesson_01_ALL.zip for full reproducibility.

---

> **Audiate Note:** At this stage in the workflow, Audiate has not yet been introduced into the Camtasia project. Therefore, there is no dehydration or rehydration of Audiate assets required at this point. Dehydrating and rehydrating Audiate assets will be covered later in this course when Audiate is integrated into the workflow.

## Concrete Folder Layout for This Use Case

1. **Lesson Folder:**
   - `C:\Users\<YourName>\Videos\lesson_01\`
   - This is your main working folder for the lesson. All subfolders for RAW, EDIT, EXPORT, FINAL, and DOCS will be created here.
2. **RAW Folder:**
   - `C:\Users\<YourName>\Videos\lesson_01\RAW\`
   - Store your original/raw recordings and project dehydrated (zipped) project files here.
3. **EDIT Folder:**
   - `C:\Users\<YourName>\Videos\lesson_01\EDIT\`
   - Save your Camtasia project files (`.tscproj`) and Zipped Projects here.
4. **EXPORT Folder:**
   - `C:\Users\<YourName>\Videos\lesson_01\EXPORT\`
   - Use for intermediate exports or files to be further processed.
5. **FINAL Folder:**
   - `C:\Users\<YourName>\Videos\lesson_01\FINAL\`
   - Place your finished, deliverable videos and student-facing documents here.
6. **DOCS Folder:**
   - `C:\Users\<YourName>\Videos\lesson_01\DOCS\`
   - Keep all internal documentation, workflow notes, and reference materials here.

We will follow these concrete folder paths step-by-step in this use case, so you can see exactly where every file goes and how to keep your workflow organized.

---

> **Important:** You do not need to understand every step in this workflow. What matters is having the discipline to follow each step in the **exact order shown**. This process is like using a power saw: you must respect the tool and follow all safety protocols, even if you don’t know all the details. Trust the workflow—precision and order are critical for success and safety.

> **Strict Folder Rule:** Every asset for `lesson_01` must be stored inside one of the five subfolders: `RAW`, `EDIT`, `EXPORT`, `FINAL`, or `DOCS`. Do not create any other folders or leave stray files outside these five. This discipline ensures your project stays deterministic, organized, and reproducible.
