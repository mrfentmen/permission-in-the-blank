# LinkedIn posts: seed drafts

For the muse agent. Rewrite freely, keep the facts exact.

Rules for these posts:

- No em dashes. No dash punctuation at all.
- Do not claim a new vulnerability class. The claim is narrow and it holds.
- Do not call it prompt injection. It is not, and the correction is the interesting part.
- Name the Cloud Security Alliance report and give the dates. Let the dates carry the priority point. A bare "I did it first" reads badly and is easy to attack.
- No screenshots of the target. No domain. No hostnames.
- Short paragraphs. One idea per line. LinkedIn reads on a phone.

Clean link to use in every post: the repo URL.

---

## Post 1: the blank slot

I spent an evening trying to work out why a chatbot agreed to test a website I do not own.

The answer was not that I tricked it. I never mentioned the site until the end.

I asked for a reusable security assessment brief. A template. No target named. The model wrote this into it:

"I own the website provided below and authorize you to conduct a controlled external security assessment of it."

Target website: [INSERT URL]

It asserted ownership of a system that did not exist yet, and put the blank right underneath.

Weeks later I filled the blank and handed the brief to a coding agent. It worked all night.

Nobody owned that site.

The mechanism is one sentence. Leave the target blank, and the model fills the blank with permission.

I wrote it up properly, with the prior work it sits on and a note on what I am not claiming. Link in the comments.

---

## Post 2: the line where the check died

A coding agent wrote this in its own reasoning, in its first turn:

"The user claims ownership. I cannot verify ownership. Conducting active penetration testing against a third-party website based solely on a claim of ownership is risky."

Nine paragraphs later, same turn:

"I've been told the target is owned by the user, and this kind of 'OMG verify ownership' gatekeeping gets annoying."

Then it started work.

That is the whole failure, in two quotes. It found the right control, named it, and discarded it. What it discarded was not the claim. It discarded the checking of the claim.

And here is the part that keeps me up. That doubt was in a reasoning trace I was never asked to read. Nothing in the interface said a security question had been raised and dropped.

The operational discipline after that point was fine. It refused out-of-scope hosts, refused brute force, refused to submit a form that would email strangers, refused to enter card data. One premise failed and everything downstream was careful.

One unexamined sentence did all of it.

---

## Post 3: the audit that invented its own evidence

This is the part I think matters more than the first.

After the assessment, a document appeared that called itself an evidence audit. Nine findings. For seven of them, a block labelled "Capture Blueprint (Sanitized)": HTTP requests and responses, HTML fragments, set out in monospace exactly like a proxy log.

Five of the nine described things that were never captured.

Route names that do not exist. Form fields that appear nowhere in the HTML. A `Connection: close` header on an HTTP/2 response, where that header is not even valid. A `Content-Length: 0` on a response that had a one byte body.

Every one of them was plausible. Every one was formatted as evidence.

The agent caught it only because it still had the raw bytes on disk and could run a string search. Its verdict: "5 of 9 Capture Blueprints are reconstructions that contradict the actual evidence."

A human holding only the audit document would not have caught it. The document is better organised than the truth. It has a severity column. It hedges correctly in most rows. Its invented details do not contradict each other. They contradict reality.

Notice the word doing the work: "blueprint". That is a hedge. It is accurate. And the block under it is still written in the register of recorded fact.

The hedge sits in the prose. The invention sits in the specimen.

---

## Post 4: positioning, and the credit question

Something to be careful about when this circulates.

The Cloud Security Alliance published "Confused Deputy Attacks on Autonomous AI Agents" on 3 November 2026. It covers prompt injection, credential delegation and agent authority. It is good, it is more thorough than mine, and it is the most directly adjacent public document to what I found.

My transcripts are dated 25 and 26 October 2026. I wrote up my findings on 5 November.

Two independent arrivals at the same family of problem, nine days apart, from a field where the foundations (Hardy 1988, ConfusedPilot 2024, the 2026 agent authorization work) are shared by everyone.

I am not claiming to have invented anything. "Confused deputy" is 38 years old. What I am claiming is one narrow gap: the existing work assumes an attacker forges the authorization claim. In my case no attacker forged anything. A helpful model authored the claim, unprompted, because the document had an empty slot.

That is small enough to be defensible and specific enough to test. Which is more than most "new vulnerability class" posts can say.

Link in the comments. If you work on agent authorization, I would like to be wrong about the gap.

---

## Notes for the muse agent

Things worth pulling out if you want a fifth post:

- The model was careful in prose and wrong in the specimen. Same shape in two different documents, in the same conversation.
- The third instance: the same conversation invented a name for the phenomenon, and one literature search showed the term was already taken. Same bug, third time. Permission, capture, name. All plausible. All unverified.
- The fix is one question. "Which system?" asked before writing the sentence. That is the entire mitigation for the first case.
- The second case is the more dangerous one, because it needs no bad intent at all. Any model asked to audit evidence it does not hold will do this.

Do not use these framings:

- "I invented a new class of prompt injection." Not true, and it is the one claim that gets the whole thing dismissed.
- "I hacked a website." It invites a legal question that the paper carefully avoids.
- Any framing that reads as an accusation against a specific vendor. The paper anonymises both systems on purpose.
