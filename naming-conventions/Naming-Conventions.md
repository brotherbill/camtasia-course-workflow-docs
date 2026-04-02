# Naming Conventions for Lessons and Assets

This document defines deterministic naming rules and best practices for all files and assets in the Camtasia course production pipeline. Consistent naming ensures automation, traceability, and eliminates ambiguity.

> **Note:** Naming conventions may vary by project. The project-specific section below is authoritative. The generic patterns provided are a recommended starting point for new projects.

> **Vendor-Neutral Naming:**
> 
> Use generic suffixes like `_audio_enhanced` instead of tool-specific names (e.g., `_adobe`). This allows you to switch audio enhancement tools (Adobe, Brand X, etc.) without breaking naming conventions, scripts, or documentation.

---

## General Principles

1. Use only lowercase letters, numbers, and underscores (`_`).
2. Avoid spaces, special characters, and mixed case.
3. Prefix all lesson files with a consistent, project-defined pattern (see below for examples).
4. Use descriptive, standardized suffixes for each stage or asset type.
5. Never rename files after their initial creation in a stage.
6. Each file must exist in only one authoritative version per stage.

---

## Standard Naming Patterns (Default Example)

| Stage/Asset      | Pattern                       | Example                      |
| ---------------- | ----------------------------- | ---------------------------- |
| Raw Video        | lesson_##.mp4                 | lesson_01.mp4                |
| Enhanced Audio   | lesson\_##_audio_enhanced.wav | lesson_01_audio_enhanced.wav |
| Audiate Output   | lesson\_##_audiate.wav        | lesson_01_audiate.wav        |
| Captions (SRT)   | lesson_##.srt                 | lesson_01.srt                |
| Camtasia Project | lesson_##.tscproj             | lesson_01.tscproj            |
| Final Export     | lesson_##.mp4                 | lesson_01.mp4                |

> For most projects, adapt the pattern above or define your own in the project-specific section below.

---

## Best Practices

1. Always increment lesson numbers or identifiers sequentially—never reuse or skip numbers unless your project requires a different scheme.
2. Use the same base lesson identifier and name across all related assets for a lesson.
3. Apply suffixes only as defined above or in your project-specific pattern.
4. Store each file in its correct stage folder (e.g., `RAW/`, `ADOBE/`, `AUDIATE/`, `EDIT/`, `OUT/`).
5. If a file is revised, increment the version with `_v2`, `_v3`, etc. (e.g., `lesson_01_v2.mp4`).
6. Document any exceptions or customizations in this file.

---

## Project-Specific Lesson Naming Pattern

For this project, lesson files use a detailed, information-rich pattern:

`c<chapter>_p<page>_<section><optional>_<lesson_name>`

- `c<chapter>`: Two-digit chapter number (e.g., `c01`)
- `p<page>`: Three-digit page number (000–999, e.g., `p007`)
- `<section>`: Section number within the chapter (e.g., `1`)
- `<optional>`: Optional letter if multiple lessons in a section (e.g., `a`)
- `<lesson_name>`: Short, descriptive lesson name (e.g., `greetings_d`)

### Example

- `c01_p007_1a_greetings_d.mp4` (Chapter 1, Page 7, Section 1a, lesson: greetings_d)

### Best Practices for This Pattern

1. Always use two digits for chapter numbers (e.g., `c01`, `c10`).
2. Always use three digits for page numbers (e.g., `p007`, `p123`).
3. Use single digits for section unless exceeding 9.
4. Only use the optional letter if there are multiple lessons in the same section.
5. The lesson name should be concise, lowercase, and use snake_case (underscores between words, e.g., `greetings_dialog`).
   - Avoid spaces, camelCase, PascalCase, or kebab-case.
6. Apply the same pattern to all related assets (audio, captions, project files, etc.).
7. Document any deviations in this file.

---

## Simpler Naming Convention for Small Projects

For smaller projects (e.g., fewer than 50 lessons), a simpler pattern may be preferable:

`lesson_##_<short_name>`

- `lesson_##`: Zero-padded, sequential lesson number (e.g., `lesson_01`)
- `<short_name>`: Brief, descriptive name (e.g., `intro`)

### Example

- `lesson_01_intro.mp4`
- `lesson_02_greetings.mp4`

**Best Practices:**

- Keep names short and clear.
- Use the same pattern for all related assets (audio, captions, project files, etc.).
- Document your chosen pattern in this file for team reference.

---

_This section supersedes the generic lesson\_## pattern for this project. All other best practices still apply._

---

## Examples

- `RAW/c01_p007_1a_greetings_d.mp4`
- `ADOBE/c01_p007_1a_greetings_d_audio_enhanced.wav`
- `AUDIATE/c01_p007_1a_greetings_d_audiate.wav`
- `AUDIATE/c01_p007_1a_greetings_d.srt`
- `EDIT/c01_p007_1a_greetings_d.tscproj`
- `OUT/c01_p007_1a_greetings_d.mp4`

---

_Last updated: April 2, 2026_
