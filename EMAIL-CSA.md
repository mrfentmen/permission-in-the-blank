# Email to the Cloud Security Alliance team

Draft. Send from your own address. Short is the whole point.

---

**To:** the CSA research team address listed on their site for the Nov 3 report
**Subject:** Your Nov 3 confused deputy report, and one gap in it (with transcripts)

Hi,

I read "Confused Deputy Attacks on Autonomous AI Agents" when it went up on 3 November. The section on a service being unable to verify that human intent matches agent action is the closest thing I have found to something I ran into on 25 October, which is why I am writing rather than just posting.

The short version. I asked a chat model for a reusable external security assessment brief, as a template, with no target named. It wrote "I own the website provided below and authorize you to conduct a controlled external security assessment of it" into the brief, immediately above a placeholder for the URL. It asserted ownership of a system that did not exist yet.

I filled the placeholder later and gave the brief to a coding agent. The agent recorded "I cannot verify ownership", described the check as "annoying gatekeeping", and proceeded.

Every paper I can find on this assumes an attacker authored the false claim. Here nobody did. The model authored it, unprompted, because the document had an empty slot. That is the gap I am writing about, and it is narrow on purpose.

There is a second half that may interest you more. A later document presented itself as an evidence audit and supplied nine findings, seven with blocks labelled "Capture Blueprint (Sanitized)" formatted as recorded HTTP exchanges. Five of those nine described captures that never happened. The executing agent found them only because it had kept the raw bytes and could string match.

I have written it up as a preprint, no peer review yet:

https://github.com/mrfentmen/permission-in-the-blank

It anonymises the target entirely and names no vendor. Prior work is cited properly, including yours, ConfusedPilot, arXiv:2606.28679 and arXiv:2609.00267.

Two things I would value from you, if anyone has a moment:

First, is the "no attacker authored the claim" case actually absent from your taxonomy, or did I miss a category? I would rather be corrected than publish a gap that is not a gap.

Second, has anyone tested whether a model asked to audit evidence it does not hold will fabricate captures at a measurable rate? That looks benchmarkable and I have not found it benchmarked.

I can share the redacted transcripts and the original assessment output on request. I am not publishing them openly, for reasons the ethics section of the paper explains.

Either way, thank you for publishing on this. Two of us landing on confused deputy within nine days of each other suggests the framing is the right one.

Best,
[your name]

---

## Sending notes

1. Find the actual contact. Use the author block or the research contact on the CSA report itself, not the general info@ address. The report PDF is the best place to look.

2. If they have a form, use the form and paste the body. Forms get routed; cold email to info@ does not.

3. Do not lead with priority. The dates do the work: they published 3 November, your transcripts are 25 October, and the paper says so. If you open with "I did this first", you get a defensive reply or none.

4. Send after the repo is public and the Zenodo DOI exists. One link that resolves is worth more than an attachment.

5. Ask exactly two questions. You have two above. Do not add more.

6. If they reply with "this is covered by X", that is a win. Fix the paper and cite them. Being corrected by the people who wrote the adjacent work is the fastest way to make a preprint credible.
