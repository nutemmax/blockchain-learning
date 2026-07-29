# Repository Instructions

This repository is a learning knowledge graph for blockchain, digital assets, fintech, and the financial system. It should become a coherent course, not a collection of project or vendor-research notes.

## Audience and Teaching Style

Write for both:

- technically strong readers who need finance explained from first principles; and
- finance professionals who need technical systems explained from first principles.

Build intuition before jargon, define assumptions, and explain each topic recursively: concept, purpose, prerequisites, internal mechanism, components and dependencies, trade-offs, risks, real implementations, and links to related topics. Prefer depth over a broad but shallow survey.

## Repository and Knowledge-Graph Structure

`README.md` is the canonical curriculum and migration plan. Keep notes exactly two
directory levels below `notes/`:

```text
notes/<macro-topic>/<micro-topic>/<canonical-note>.md
```

The macro topics are:

0. course guide and orientation;
1. financial foundations;
2. blockchain foundations;
3. digital assets and market structure;
4. decentralized finance;
5. digital money and tokenization;
6. interoperability, privacy, and enterprise DLT; and
7. compliance, analytics, regulation, and security.

Organize companies and protocols beside the concepts and markets they implement,
not in a generic companies folder. For example, Aave belongs under onchain
lending, Chainalysis under blockchain analytics, Zama under privacy, and Coinbase
under centralized crypto markets. Make every major concept have one canonical
home and connect related notes with purposeful Markdown links.

## Refactoring Existing Notes

Preserve accurate technical, financial, architectural, and comparative material. Rewrite only what needs rewriting.

Remove or generalize anything that reveals the original project, client, employer, use case, procurement exercise, or research objective. Remove institution-specific recommendations, adoption assessments, requirements, scoring, and conclusions such as whether a particular financial institution should use a vendor or protocol.

Vendor, company, blockchain, and protocol material may remain when it is neutral and educational. Describe how systems work, compare their designs, and explain strengths, limitations, risks, and relevant history without writing from the viewpoint of a prospective client. Do not infer or expose the projects that motivated the original research.

Move an existing note without rewriting it when it already meets the learning
standard. Otherwise, preserve its accurate content and rewrite only the sections
that need a neutral voice, better teaching structure, correction, consolidation,
or removal of project context. Create missing notes from scratch. Follow the
status and destination recorded in `README.md`, updating the plan when it changes.

## Format

Use the format that best teaches each idea:

- paragraphs for intuition, mechanism, causality, and nuance;
- bullets for properties, steps, assumptions, and risks;
- tables for comparisons and decision frameworks;
- Mermaid diagrams for architecture, flows, lifecycles, and dependencies;
- concrete examples, equations, schemas, and concise callouts where useful.

Notes should contain substantial explanatory prose, not just bullets and tables.
Start from foundations, then descend into subtopics and sub-subtopics as far as
needed for a rigorous, self-contained explanation. A canonical note should be as
comprehensive as practical within its declared scope, while distinguishing facts,
interpretations, and time-sensitive claims.

## Token Discipline

Depth does not mean repetition. Prefer a few long canonical notes. Before adding a
file, check `README.md` and existing notes for the concept's canonical home.
Explain shared foundations once, recap them briefly elsewhere, and link back.
Merge overlapping material, avoid filler, and split a note only when it has
genuinely distinct teaching paths or a company warrants a separate deep dive.

## Accuracy and Sources

Use technically and financially precise language. Verify claims that may change over time and date them when relevant. End every note with a `## References` section containing sources that support its claims. Prefer primary and authoritative sources; for a company, vendor, product, blockchain, or protocol, include its official documentation or website and add independent sources when they improve accuracy or balance.
