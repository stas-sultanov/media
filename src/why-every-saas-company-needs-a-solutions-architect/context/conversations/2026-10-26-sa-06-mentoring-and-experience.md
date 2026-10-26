# SA-06 — Mentoring constraints and varied experience — 2026-10-26

Record of the article-related SA-06 discussion supplied in this session. Quoted author statements and English proposals are verbatim; connecting explanations are summaries. Repeated readings and operational acknowledgments are omitted. This is not a full transcript of every message or tool action.

## Initial direction and proposal — summary

After SA-05, the assistant introduced SA-06: explain the mentoring and varied-experience constraints on developing a Solutions Architect inside a SaaS company. The author requested a forceful formulation:

> О. Я жёстко

The assistant proposed:

> Without an experienced SA to mentor, a SaaS company rarely develops one; promotion alone doesn’t create the competence.

The author requested hearing the whole subsection with the proposed insertion.

## Author objection to repetition — verbatim

> Значит, что мне там не нравится, там два раза повторяем, короче, типа, что эту компетенцию нельзя, типа, внутри вырастить

The assistant proposed removing the clause “promotion alone doesn’t create the competence”, because SA-05 already states that promotion grants title and mandate, not competence. The shortened mentor sentence was:

> Without an experienced SA to mentor, a SaaS company rarely develops one.

The author requested another full reading:

> Прочитай теперь полностью весь кусок

## Author objection to repeated “multiple” — verbatim

> Вот мне не нравится вот это, что мы там используем много раз multi, поэтому типа то, multi, поэтому, типа то

The assistant proposed replacing the repeated “multiple” list with this continuous enumeration:

> across different customers and business models, domains with different regulatory traps, technology stacks and scaling problems, production outages and cost crises.

The wording combines customers and business models, then retains the domain, technology, scaling, outage and cost-crisis examples without repeating “multiple” at the start of each item.

## Author acceptance — verbatim

> Хреново звучит Да, оставляем так

The assistant stated that it would apply the change as SA-06 in a separate commit with the rationale. The author explicitly confirmed:

> Да, давай

## Approved implementation — summary

In “3. Level up an internal employee”:

1. Add the shortened mentor sentence immediately after the existing SA-05 promotion sentence.
2. Replace the existing repetitive bullet list with the accepted continuous enumeration. Join the existing introductory sentence to that enumeration by changing the colon/list transition to a space before “across”.
3. Preserve the remaining subsection, including “This rarely succeeds” and the final paragraph about a single SaaS company's ability to provide breadth.

The resulting subsection is:

### 3. Level up an internal employee

Assumption: mentor a strong internal engineer or delivery lead into an SA over time.

Promotion grants title and mandate, not competence.

Without an experienced SA to mentor, a SaaS company rarely develops one.

This rarely succeeds. Correct judgment in this role comes from years of exposure to different pressures and failures across different customers and business models, domains with different regulatory traps, technology stacks and scaling problems, production outages and cost crises.

A single SaaS company usually cannot generate that breadth fast enough. It isn’t about intelligence; it’s accumulated scar tissue under different conditions.

Only SA-06 is resolved by this change. The article edit, discussion, rationale and backlog status are recorded together in one separate SA-06 commit.

See [author decision](../decisions.md#sa-06--mentoring-constraints-and-varied-experience--2026-10-26) and [backlog entry](../improvements.md#sa-06--explain-mentoring-and-exposure-constraints).
