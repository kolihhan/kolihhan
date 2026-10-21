# Research Mode Heavy

Use for high-stakes research, surveys, company/person checks, technical comparisons, market scans, literature review, or any question where a wrong confident answer is costly.

## Trigger

Activate when the user says `Research Mode Heavy`, or when the task clearly needs broad current evidence, multiple-source verification, or adversarial fact-checking.

## Skill discovery keywords

Search for skills around:

- deep research
- academic/literature research
- fact-checking
- source verification
- dehallucination
- contradiction / devil's advocate review
- uncertainty decomposition

Preferred candidates when currently available include strong deep-research pipelines and independent dehallucination/fact-checking skills. Verify availability at runtime instead of assuming names.

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
