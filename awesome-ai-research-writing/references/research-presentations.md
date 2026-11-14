# Research Presentations

Use to create or revise a research PPT for a journal club, group meeting, thesis defense, or conference talk. An explicit outline-only request ends with an outline. A request for a PPT calls for an actual deck when authoring/export tools are available.

## 1. Establish the talk contract

Reuse the supplied paper/version, existing deck, template, audience, language, duration, aspect ratio, and output format. Ask only for consequential missing inputs. If a reasonable assumption permits progress, state it briefly and proceed. Do not invent institutional branding, required sections, or a fixed number of slides per minute.

Choose the story for the occasion:

| Occasion | Main job | Evidence emphasis |
| --- | --- | --- |
| Journal club / 文献汇报 | Explain and critically assess another work | Problem, mechanism, decisive experiment, limitations, discussion questions |
| Group meeting / 组会 | Support a research decision | Progress, baseline, new result, failure analysis, next experiment and needed feedback |
| Defense / 答辩 | Establish the candidate's contribution | Research questions, connected contributions, validation, boundaries, likely committee questions |
| Conference talk | Make one contribution memorable | Problem, key idea, strongest evidence, implications and limits |

Adapt to the research itself: a discovery paper may center on evidence and alternatives; a methods paper on mechanism and evaluation; a resource paper on construction and utility; a review on synthesis and disagreements. Clinical or other specialized work needs its own study-design context, not a generic model-benchmark narrative.

## 2. Build an evidence-grounded story

Read the relevant paper sections and inspect important figures/tables. For PDFs, use page images where extraction loses symbols, chart encodings, or table alignment. Keep a small working mapping of each key claim to its section/page/figure/table and exact quantitative conditions. This can live in speaker notes or the slide plan; do not create a separate tracking system.

- Preserve technical names, definitions, notation, units, denominators, and uncertainty across slides. Use a compact terminology list when translation risks inconsistency.
- Distinguish author claims, replicated observations, and the presenter's interpretation. Label proposed experiments and conceptual illustrations explicitly.
- If only an abstract is supplied, make a preliminary abstract-level outline and identify the method/results material needed for a defensible full talk. Do not fabricate experimental slides.
- Verify external context or recent comparisons with primary sources. Do not turn unmatched benchmark settings into a controlled comparison.

Choose a central question and a takeaway supported by the evidence. Organize slides as an argument, not one slide per manuscript section. For each planned slide, specify a short title, one main message or question, supporting evidence/visual, source anchor, and approximate speaking time. Add notes where the spoken explanation carries details omitted from the slide.

Allocate time by difficulty and importance. Include opening, transitions, and closing in the total; reserve Q&A only if it is part of the stated duration. Cut peripheral material or move it to backup slides when the talk runs over. Do not solve timing by shrinking text.

## 3. Design around scientific content

Use the supplied template and existing visual language where applicable. Otherwise choose a restrained, coherent system of typography, spacing, color, and alignment suited to the audience and display. Make the key contribution or finding visually prominent and supporting detail quieter.

- Use concise informative titles; a claim title must be supported. A question title is appropriate when the evidence is unresolved.
- Prefer one main visual argument per slide. Use side-by-side comparisons only when axes, conditions, and labels remain readable and comparable.
- Reuse a source figure when it communicates clearly. Crop without removing context needed for interpretation; mark an inset or zoom and retain relevant legends, scales, units, and attribution.
- Redraw dense paper figures for presentation readability while preserving values and semantics. Label “adapted from” when appropriate and keep the original source in notes. Do not infer underlying data from a schematic; digitized values require disclosure.
- Use editable text, shapes, arrows, tables, and charts where feasible. Keep an imported paper image as an image when appropriate; do not describe it as individually editable objects.
- Present equations progressively: define variables, show the mechanism needed for the argument, and keep notation consistent. Avoid screenshots of unreadably dense derivations.
- Use contrast and redundant encoding (labels, shapes, line styles) so meaning does not depend on color alone. Choose text size through actual slide-size inspection rather than treating a fixed point size as universally sufficient.

Use [scientific data figures](scientific-data-figures.md) for new quantitative plots and [framework figures](framework-figures.md) for method diagrams. Keep chart uncertainty and training/inference distinctions intact when adapting them to slides.

## 4. Author the requested artifact

Inspect the current environment's presentation capability and follow the relevant installed skill/tool documentation. Prefer established tools that fit the requested format and project; this package assumes no particular library, slide service, or API key.

For a PowerPoint request, create `.pptx` when possible. Use reusable layouts/themes and editable objects instead of flattening every page into one image. Add speaker notes for explanations, timing cues, evidence anchors, qualifications, and probable questions as useful. Notes are not a substitute for visible attribution when it is required on the slide.

If the environment can create source but cannot export PPTX, deliver that source with the precise export limitation. Do not silently substitute a PDF, image collection, or outline and call it a completed PowerPoint. If only text can be produced, provide a useful slide-by-slide plan and notes, and state that the deck file remains uncreated.

<a id="edit-existing-decks"></a>
## 5. Edit existing decks

Inspect the existing deck before modifying it: theme/master layouts, dimensions, fonts, object structure, slide order, notes, and target pages. Preserve unaffected slides and the source file unless overwriting was requested. Keep the revision in a clearly named output file or the established project versioning path.

For targeted edits, change the specified slides and dependent references or numbering only as necessary. Do not redesign the entire deck to fit a preferred theme. Check that imported assets, notes, citations, and layout inheritance survive export. Unsupported animations, equations, or custom fonts should be called out where they affect fidelity.

## 6. Inspect the result

Verify the actual saved file through the normal toolchain. Structural checks include slide count/order, dimensions, text presence, notes where expected, missing assets, and obvious placeholder content. File existence alone does not establish a usable deck.

Render all slides with the available presentation or office renderer and inspect both a contact sheet for consistency and full-slide views for detail. Review:

- overflow, clipping, overlaps, missing glyphs, font fallback, equation rendering, and alignment;
- readability of chart axes, annotations, references, and source figures at presentation size;
- consistent terminology, values, source anchors, slide numbering, and template use;
- story continuity, evidence strength, total estimated speaking time, and backup-slide placement;
- accidental changes outside the requested pages in an existing deck.

Fix defects in the editable source and re-export affected slides. Structural inspection of PPTX XML cannot replace rendered visual inspection. If rendering is unavailable, report that visual checks remain unperformed; deliver the usable file/source without claiming a rendered pass.

## Delivery

For a deck request, return the actual editable deck, any requested PDF/preview, and the source/assets needed to continue editing when they are separate. Include a short note naming the audience/duration assumptions and any concrete remaining limitation. Put substantive source attribution and speaker notes inside the artifact where possible, not solely in chat.

For an outline request, return the slide plan with messages, evidence/source anchors, and time allocation. For a prompt-template request, provide input slots for sources, occasion, audience, duration, template, language, and deliverables. Do not run the file-production workflow when the user asked only for planning text.
