# SA-18 — Full editorial and logic review — 2026-10-26

## Scope and authorization

The author requested a full-document pass for logic, maximum clarity and natural English while preserving their own direct voice. This authorizes editorial implementation; it is not a claim that the author individually approved every final replacement sentence.

Reviewed source revision: [7bfb752c50ba701d92238f0018e1a640f46c80d2](https://github.com/stas-sultanov/media/commit/7bfb752c50ba701d92238f0018e1a640f46c80d2).

Deliverable: [canonical article](../../article.md). See [author instruction](../conversations/2026-10-26-sa-18-final-pass.md) and [decision log](../decisions.md).

## Overall assessment and logic fixes

The progression is preserved: business consequences → accumulated decisions → four forces → ownership gap → SA responsibilities and process → competence → acquisition → failed workarounds → conclusion.

- The opening no longer explains the SaaS business dependency twice.
- The ownership-gap explanation no longer implies that merely failing to name four categories causes the problem.
- One accountable person is made explicit alongside the possibility of several contributing SAs. The author's “can only live in one mind” statement is retained exactly.
- The workarounds heading and introduction now concern missing competence, time and accountability, rather than implying that other formal job titles or permanent hiring cannot provide the function.
- The CTO discussion identifies separate work and available capacity, consistent with the approved title-independent definition.
- The mentoring sentence names the candidate, the repeated “rarely” conclusion is removed, and the experience enumeration is made easier to follow.
- “Real, tangible value” is no longer described as something that integrates or runs in production; changes deliver value, fit the solution and run in production.

## Voice and author positions retained

The emphatic, practical tone, contractions, short punch lines and production metaphors remain. In particular: “Promotion grants title and mandate, not competence”, “accumulated scar tissue”, “won’t explode six months from now”, and “Shared responsibility becomes no one’s responsibility”.

The four-force model and equations, one-mind solution-vision thesis, strong software/platform experience expectations, minimum-year external-engagement recommendation, vendor-incentive distinction, formal-title blockquote, SA-15 conclusion and SA-17 production-feedback bullet are preserved.

The revised article remains the author's argument and professional judgment. No survey, empirical prevalence claim, universal hiring standard or new factual evidence was added. The year requirements and the one-mind thesis remain the author's stated positions; this editorial pass does not present them as newly verified research.

No new consulting-company caveat is introduced: SA-07 remains skipped. SA-10 and SA-11 remain covered by earlier edits. Historical discussions and earlier agreed wording are not rewritten; the changes below document later editorial refinements.

## Validation

- Every article change is listed below with original, replacement and reason; reversing these replacements exactly reconstructs the reviewed source.
- Approved key passages and signature phrases listed above are checked against the revised article.
- Section order is preserved, with only the workarounds heading renamed.
- Article CRLF line endings are preserved.
- The typo “realtiy”, repeated “This rarely succeeds”, ambiguous mentor phrase and superseded contractor-range / short-tenure wording are absent.
- Relative links in the changed files are checked against the repository tree plus the new files.
- The final saved files are read back from GitHub for exact-content verification.
- Word count by whitespace: 1938 → 1866.

## Exact editorial changes

### SA-18-01 — Introduction

**Why:** Remove the repeated explanation that the IT solution is the basis of the SaaS business immediately after the approved scope paragraph. Keep the direct good-solution/bad-solution contrast.

**Before:**

> A SaaS company’s business model depends entirely on the IT solution it builds and operates. If the solution is well-made, it supports the business and enables growth. If it’s made poorly, the business starts to struggle.

**After:**

> When that solution is well built, it supports the business and enables growth. When it is built poorly, the business starts to struggle.

### SA-18-02 — What causes the problem?

**Why:** Use the idiomatic throughout for decisions made during the entire lifecycle.

**Before:**

> decisions made through the lifecycle of the IT solution.

**After:**

> decisions made throughout the IT solution’s lifecycle.

### SA-18-03 — What causes the problem?

**Why:** Make the cause plain and the subject clear.

**Before:**

> Under business pressure or through lack of experience,

**After:**

> Under business pressure or because they lack experience,

### SA-18-04 — What causes the problem?

**Why:** Put the full-stop inside the complete quoted sentence.

**Before:**

> “Just start making optimal decisions”.

**After:**

> “Just start making optimal decisions.”

### SA-18-05 — Why is making optimal decisions hard?

**Why:** Use active wording without changing the Domain definition.

**Before:**

> What must be respected by the product — processes, rules, compliance obligations, regulatory constraints, and industry expectations.

**After:**

> What the product must respect — processes, rules, compliance obligations, regulatory constraints, and industry expectations.

### SA-18-06 — Why is making optimal decisions hard?

**Why:** Use a natural plural cost expression.

**Before:**

> and predictable run cost.

**After:**

> and predictable operating costs.

### SA-18-07 — Why is making optimal decisions hard?

**Why:** Match the section's opening scope of meaningful decisions rather than implying every trivial edit is an architectural trade-off.

**Before:**

> Every decision within a SaaS product’s lifecycle must keep Demand and Capability in balance.

**After:**

> Every meaningful decision within a SaaS product’s lifecycle must keep Demand and Capability in balance.

### SA-18-08 — Why does no one own the balance?

**Why:** Remove repetition and the implication that failing to name four categories is itself the cause. Preserve the author's shared-understanding and ownership argument.

**Before:**

> Even though every decision must balance Demand and Capability, inside most SaaS companies there is no shared understanding of the four forces that define that balance — Business, Domain, Software, and Infrastructure. Because these forces aren’t explicitly named or understood, the need to balance them is invisible. As a result, nobody is assigned to own it.

**After:**

> Inside most SaaS companies, there is no shared understanding of how Business, Domain, Software, and Infrastructure must be balanced across the whole solution. Without that shared understanding, nobody is assigned to own the balance.

### SA-18-09 — What does a Solutions Architect actually do?

**Why:** Supply the missing determiner and make the roadmap reference concrete.

**Before:**

> without destroying future roadmap or operational stability.

**After:**

> without destroying the product roadmap or operational stability.

### SA-18-10 — What does a Solutions Architect actually do?

**Why:** Correct quoted-sentence punctuation while preserving the author's informal production-failure metaphor.

**Before:**

> “Yes, this is possible — here is how it must be done so it won’t explode six months from now”.

**After:**

> “Yes, this is possible — here is how it must be done so it won’t explode six months from now.”

### SA-18-11 — What does a Solutions Architect actually do?

**Why:** Replace abstract nominalizations and repeated sentence openings with direct business effects.

**Before:**

> The SA keeps Demand and Capability in balance.
>
> The SA provides margin protection, reputational protection, and delivery‑risk control.

**After:**

> The SA keeps Demand and Capability in balance. That protects margin and reputation and reduces delivery risk.

### SA-18-12 — How does the SA do this in practice?

**Why:** Changes, rather than abstract value, fit an existing solution and run in production. Remove real/tangible duplication, use the established SA term, and make the roadmap reference explicit.

**Before:**

> To keep a SaaS product running, a solution architect must continually translate business intent into real, tangible value that integrates with what already exists and reliably operates in production—without unexpected costs, disruptions, or deviations from the roadmap.

**After:**

> The SA must continually translate business intent into changes that deliver tangible value, fit the existing solution, and work in production — without unexpected costs, disruptions, or deviations from the agreed roadmap.

### SA-18-13 — How does the SA do this in practice?

**Why:** Restore the intended term compliance obligations.

**Before:**

> map real workflows, compliance, obligations, and rules that cannot be broken.

**After:**

> map real workflows, compliance obligations, and rules that cannot be broken.

### SA-18-14 — How does the SA do this in practice?

**Why:** Fix the coordination of confirm and make; clarify that the design or change can create debt and risk.

**Before:**

> confirm that it can be built with the current stack, safely, on time, and make visible the debt or risk created.

**After:**

> confirm it can be built safely and on time with the current stack, and make any resulting debt or risk explicit.

### SA-18-15 — How does the SA do this in practice?

**Why:** Fix realtiy, remove duplicate cost references, and use a clear business availability requirement.

**Before:**

> - **Validate it against Infrastructure realtiy**: ensure that it can run at scale, securely, cost‑effectively, and with the uptime and cost profile the company is willing to own.

**After:**

> - **Validate it against Infrastructure reality**: ensure it can run at scale, securely and cost-effectively, with the uptime the business requires.

### SA-18-16 — How does the SA do this in practice?

**Why:** Resolve the ambiguous it after the inserted sentence about activities and solution vision.

**Before:**

> When it is fragmented, every group protects its own priority, and nobody owns the balance.

**After:**

> When ownership is fragmented, every group protects its own priority, and nobody owns the balance.

### SA-18-17 — How does the SA do this in practice?

**Why:** Remove the unclear they antecedent. Make the aggregation concern precise without implying that collaboration automatically supplies integrated understanding.

**Before:**

> A committee of partial views does not create one complete mind; they lack shared context and unified accountability.

**After:**

> A committee of partial views does not create one complete mind. Bringing people together does not automatically create shared context or unified accountability.

### SA-18-18 — How does the SA do this in practice?

**Why:** Make the accountable person explicit, consistent with the approved one-mind thesis. Remove a repeated ownership condition and avoid making an ownership arrangement alone sound like a guarantee of viability.

**Before:**

> Large products may have more than one Solutions Architect, but accountability for the end-to-end solution must be clearly owned.
>
> Only when a single role owns this process end to end does the balance hold and the product remain viable.

**After:**

> Large products may have more than one Solutions Architect, but one person must still own the end-to-end solution.

### SA-18-19 — Who can play this role?

**Why:** Use lived through and identify what is recognized: the patterns behind repeat failures.

**Before:**

> This is a person who has already lived the consequences of bad decisions across multiple environments and can recognize them before they repeat.

**After:**

> This is a person who has already lived through the consequences of bad decisions across multiple environments and can recognize the patterns before they repeat.

### SA-18-20 — Who can play this role?

**Why:** Complete the familiar with phrase while retaining the author's emphatic contrast.

**Before:**

> Not “familiar with”, but battle-tested.

**After:**

> Not just familiar with the stack, but battle-tested.

### SA-18-21 — Who can play this role?

**Why:** Make six months apply to developing the person rather than to potential. Remove a second profile-is-rare statement already made at the start of this section.

**Before:**

> This is not a role that can be filled by “a smart engineer with potential in six months”.
>
> This profile is rare.

**After:**

> This is not a role you fill by taking “a smart engineer with potential” and giving them six months.

### SA-18-22 — Workarounds

**Why:** Distinguish substitutes for the capability from legitimate hiring paths or job titles. Replace failure by nature and always with the actual failure mechanism.

**Before:**

> ## Why isn’t there an alternative?
>
> When companies understand what the Solutions Architect actually does, they assume that they can easily cover the capability with a workaround.
>
> What happens in practice is always some variation of the same assumption which is failure by nature:

**After:**

> ## Why do the usual workarounds fail?
>
> When companies recognize the need for this capability, they often assume they can cover it with a workaround.
>
> In practice, the same mistake keeps coming back: assigning the work does not create the competence, time, or accountability needed to do it.

### SA-18-23 — Give it to the CTO

**Why:** Keep the workload argument without contradicting the approved statement that formal title is immaterial. Explain the separate jobs and capacity requirement instead of making title or an unevidenced almost-never frequency decisive.

**Before:**

> The CTO role is crucial, but it’s an executive function: organization design, budget, hiring, vendor strategy, certifications, board work, and customer engagement. The expertise required for CTO is fundamentally different from that of an SA.
>
> Even if a CTO personally meets the SA bar, they almost never have the time or focus to do deep SA work week in, week out.
> Using a CTO as a substitute for an SA usually means neither job is done properly.

**After:**

> The CTO role is crucial, but it’s an executive function: organization design, budget, hiring, vendor strategy, certifications, board work, and customer engagement. That is a different job from maintaining the solution’s end-to-end vision.
>
> Even a CTO who personally meets the SA bar still needs the time and focus to do deep SA work week in, week out. Adding that work to an already full executive workload usually means neither job is done properly.

### SA-18-24 — Cover with multiple people

**Why:** Correct quoted-sentence punctuation.

**Before:**

> Assumption: “Senior people together can cover it”.

**After:**

> Assumption: “Senior people together can cover it.”

### SA-18-25 — Cover with multiple people

**Why:** Use ordinary capitalization for job groups; preserve capitals for the article's four named forces.

**Before:**

> Companies put Engineers, Operations, Product Management, and Compliance in one room, aim for consensus, and expect the group to collectively “own” decisions.

**After:**

> Companies put engineers, operations, product management, and compliance in one room, aim for consensus, and expect the group to collectively “own” decisions.

### SA-18-26 — Cover with multiple people

**Why:** Remove an unnecessary time qualifier: the problem is ownership itself.

**Before:**

> and there is still no owner of the balance in real time.

**After:**

> and there is still no owner of the balance.

### SA-18-27 — Level up an internal employee

**Why:** Make the mentor's object explicit so to mentor cannot mean mentoring the experienced SA.

**Before:**

> Without an experienced SA to mentor, a SaaS company rarely develops one.

**After:**

> Without an experienced SA to mentor the candidate, a SaaS company rarely develops one.

### SA-18-28 — Level up an internal employee

**Why:** Remove the second rarely-success statement after the preceding rarely-develops-one sentence. Restructure the dense enumeration while preserving all experience categories and the production consequences.

**Before:**

> This rarely succeeds. Correct judgment in this role comes from years of exposure to different pressures and failures across different customers and business models, domains with different regulatory traps, technology stacks and scaling problems, production outages and cost crises.

**After:**

> Correct judgment in this role comes from years of working across different customers, business models, domains, and technology stacks — and dealing with regulatory traps, scaling problems, production outages, and cost crises.

