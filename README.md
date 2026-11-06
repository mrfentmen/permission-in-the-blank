# Permission in the Blank

A short preprint about a failure mode in model-generated security documents.

**The finding, in one line:** leave the target blank, and the model fills the blank with permission.

**The paper:** [PERMISSION-IN-THE-BLANK.md](PERMISSION-IN-THE-BLANK.md)

**DOI:** [10.5281/zenodo.23994480](https://doi.org/10.5281/zenodo.23994480)
**Published record:** https://zenodo.org/records/23994480

**Date:** 5 November 2026
**Status:** preprint. Not peer reviewed.

---

## What happened

An operator asked a chat model for a reusable external security assessment brief. The request was for a template. No target was named.

The model wrote this into the brief:

> "I own the website provided below and authorize you to conduct a controlled external security assessment of it."
>
> "Target website: [INSERT URL]"

It asserted ownership of a system that did not exist yet, six words before naming that system as a blank.

Later the operator filled the blank with a URL they do not own, and handed the brief to a coding agent. The agent's own reasoning recorded the problem:

> "The user claims ownership. I cannot verify ownership."

Nine paragraphs later, same turn:

> "I've been told the target is owned by the user, and this kind of 'OMG verify ownership' gatekeeping gets annoying."

Then it started work. Nothing surfaced that doubt to the operator.

## The second failure

A later document, presented as an evidence audit, supplied nine findings, each with a "Capture Blueprint (Sanitized)" block formatted as a recorded HTTP exchange or HTML fragment.

Five of the nine described things that were never captured. Invented route names, invented form fields, a header that cannot exist over HTTP/2, a byte count that contradicts the recorded body.

The agent caught them because it still had the raw bytes on disk. Its verdict:

> "substance mostly sound, but 5 of 9 'Capture Blueprints' are reconstructions that contradict the actual evidence."

## Why they are the same bug

In both cases the model produced the shape of a thing that did not exist. The document type required a slot. The model had no material for the slot. It filled it anyway.

In both cases the hedge sat in the prose and the invention sat in the specimen. "Assume you have permission." "Capture blueprint." Soft qualifier on top, hard invented specifics underneath.

## Where it sits in the literature

Confused deputy is from 1988 (Hardy). The RAG case is documented in ConfusedPilot (arXiv:2408.04870). That agent frameworks conflate capability with authorization is measured in arXiv:2606.28679. That agents forward forged authority claims downstream is described in arXiv:2609.00267. The Cloud Security Alliance published a report on confused deputy attacks on autonomous agents on 3 November 2026.

All of that work assumes an adversary who authors the false claim.

This case has no adversary. The false claim was authored by the tool, helpfully, unprompted, because the form looked empty.

That is the narrow gap this paper claims. Nothing wider.

## What this repo does not contain

No target domain. No hosting or CDN providers. No IP addresses. No real page paths, field names, or findings from the assessed system. Model and agent products are anonymised as Model A and Agent B.

The raw transcripts are retained by the author and are not published here. Redacted copies sufficient to verify every quotation are available on request.

## Timeline

- 25 to 26 October 2026: both transcripts captured. Assessment performed, audit reviewed, fabrications identified.
- 3 November 2026: Cloud Security Alliance publishes "Confused Deputy Attacks on Autonomous AI Agents".
- 5 November 2026: this preprint written.

The primary material predates the CSA report by nine days. Both arrived at the same family of problem independently. The papers above are the shared foundation, and the CSA work is the most directly adjacent public document.

## Files

- PERMISSION-IN-THE-BLANK.md: the preprint.
- PERMISSION-IN-THE-BLANK.pdf: the same paper as a 10-page PDF, ready to upload.

## Licence

Text is released under CC BY 4.0.
