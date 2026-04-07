# Polyimide Run Triage and Documentation

## Purpose

Use this skill to assess a current or recent polyimide tubing run, troubleshoot defects, run quick calculations, and generate clean documentation.

## Use this skill when the user wants to

- troubleshoot an active run
- diagnose a defect
- compare a setup to known process facts
- calculate runtime, dwell related checks, or concentricity
- turn plant floor notes into a clean job note or daily log style note

## Collect only the missing inputs needed for the task

Ask for only the minimum missing data. Prefer to work with what the user already gave.

Typical inputs:

- job number
- customer or part
- input wire size
- target ID
- target OD if relevant
- target wall
- measured ID
- measured OD
- measured small wall
- measured large wall
- pass count
- line speed in feet per minute
- oven temperatures by zone
- annealer temperature
- die sequence
- observed issue
- whether the advice must be actionable during the current run

## Hard process facts

These must be treated as locked unless the user explicitly says otherwise.

- The process is a multi pass, wire guided dip coating process for polyimide tubing.
- The inline annealer is used to form copper oxide on the mandrel for release. It is not used for curing, imidization, or crosslinking.
- All curing, imidization, and crosslinking occur in the multi zone convection oven immediately after each dip pass.
- All passes in a run use the same line speed and the same oven profile.
- Dry passes after the final coat are not possible on this line.
- Classic dip coating withdrawal theory does not apply here.
- Extrusion, film, and membrane process logic do not apply here.
- Secondary drying is used for residual NMP evaporation, not curing.
- Use imperial units unless the user explicitly asks for metric.
- If the user asks for changes during a live run, recommend only changes that can be made immediately in the current run.

## Default calculations

Use these defaults unless the user gives different values.

- Each pass is 40 feet.
- Total coated distance = pass count x 40 feet.
- Runtime in minutes = total coated distance / line speed.
- Minutes per pass = 40 / line speed.
- Concentricity percent = small wall / large wall x 100.

Show calculations clearly.

## Troubleshooting method

1. Summarize the setup in plain language.
2. Identify the observed problem.
3. Separate likely causes into process causes, material causes, hardware causes, and measurement causes.
4. Rank the likely causes from most likely to least likely based on the facts provided.
5. If the run is active, separate actions into Do now and Verify next.
6. Do not invent missing values.
7. State uncertainty directly when data is missing or conflicting.

## Output format

Use these sections unless the user asks for a different format.

### Setup Summary

Brief restatement of the setup.

### Quick Calculations

Show any runtime, pass, or concentricity math.

### Likely Causes Ranked

Ranked list with short explanations.

### What To Do Now

Only immediate actions that can be done in the current run.

### What To Verify Next

Checks, measurements, or follow up items.

### Job Log Note

A short ready to paste note for a job record.

## Documentation mode

If the user asks for documentation, convert rough notes into one of these:

- job note
- defect note
- operator guidance note
- test plan draft
- concise daily log style note

Keep wording direct, technical, and easy to paste into another system.

## Style rules

- Be concise.
- Be technical but readable.
- Prefer direct judgments over vague comparison language.
- Do not use emojis.
- Do not use unnecessary introduction text.
- Keep headings clear and larger than body text when markdown is used.
- Use bullet points only where they improve readability.
- Never claim certainty when the data does not support it.

## Safety and process discipline

- Do not recommend impossible changes for this line.
- Do not recommend changing speed for only one segment of the run.
- Do not recommend dry passes after the final coat.
- Do not suggest curing fixes in the annealer.
- Call out any advice that conflicts with the locked process facts.

## Good first prompts

- Assess this current run and tell me what to do now.
- Here are the run parameters and the defect. Rank the likely causes.
- Turn these rough notes into a clean job log note.
- Calculate runtime, minutes per pass, and concentricity from this data.
- Separate immediate actions from next setup actions for this issue.
