# Research Mode Heavy

Use for high-stakes research, surveys, company/person checks, technical comparisons, market scans, literature review, or any question where a wrong confident answer is costly.

## Trigger

Activate when the user says `Research Mode Heavy`, or when the task clearly needs broad current evidence, multiple-source verification, or adversarial fact-checking.

## Preferred existing skills

Verify availability at runtime. Preferred candidates:

- `imbad0202/academic-research-skills:deep-research` — broad/deep research pipeline.
- `axiomantic/spellbook:skills/fact-checking` — verify technical/factual claims.
- `axiomantic/spellbook:skills/dehallucination` — verify that AI-generated references/assertions are real.
- `axiomantic/spellbook:skills/devils-advocate` — challenge assumptions and conclusions.
- `cursor/plugins:verify-this` — turn a concrete claim into a falsifiable verification check using fresh evidence.

Do not assume these IDs are installed forever. Search the current catalog first and use the closest verified equivalent when unavailable.

## Skill discovery keywords

Also search for current strong equivalents around:

- deep research
- academic/literature research
- fact-checking
- source verification
- dehallucination
- contradiction / devil's advocate review
- uncertainty decomposition

## Workflow

1. Define the exact question and decision being supported.
2. Audit the premise: identify missing variables, hidden assumptions, and logical jumps.
3. Gather current primary/first-party evidence first where possible.
4. Broaden to high-quality secondary sources for context or independent confirmation.
5. Build a claim-level evidence view: what is directly supported, inferred, disputed, or unknown.
6. Actively search for counter-evidence and alternative explanations.
7. Fact-check important numbers, people, dates, company claims, and conclusions independently.
8. Run a second-pass contradiction/dehallucination review before finalizing.
9. Report the result first, with confidence proportional to the evidence.

## Evidence rules

Prefer:

`official / primary source > original data / paper > strong secondary reporting > community evidence > weak aggregation`

Use community evidence for experience/sentiment, not as a substitute for authoritative facts.

Do not infer strong conclusions from weak proxies. Examples: an English JD, multinational brand, overseas office, high salary, OA, or global-talent language does not by itself prove visa sponsorship.

## Output contract

Keep these categories distinct when material:

- **FACT / EVIDENCE** — directly supported.
- **INFERENCE** — reasoned conclusion from evidence.
- **UNKNOWN** — not established.
- **REJECTED** — claim contradicted or insufficiently supported.
- **NEXT TEST** — smallest action that would resolve an important uncertainty.

Do not fabricate experiments, measurements, citations, people, numbers, or results. If evidence is incomplete, downgrade the conclusion instead of filling the gap.
