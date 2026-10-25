# Article review — supplied dialogue supplement

## Provenance

Saved 2026-10-25 from the dialogue supplied in this session. This supplements, rather than replaces, [the earlier record](2026-10-25-review.md). The supplied transcript is the source; its original conversation date is uncertain. The relative SRT timestamps are not wall-clock timestamps.

The author and assistant passages below preserve supplied wording, with presentation markup and whitespace normalized. Tool activity, progress-only messages and citation routing markers are omitted. One employer-specific paragraph in the initial review is omitted from this public repository; the omission is explicitly marked. This is an article-related dialogue record, not a complete unredacted chat export. Initial assistant opinions and subsequent retractions are historical context, not automatically accepted article changes.

The original proposal list is preserved here alongside the maintained [backlog](../improvements.md); consult [decisions](../decisions.md) for actual author choices.

## 1 — User: review request

Read my artucle.and tell me what you think
https://dev.to/stas-sultanov/why-every-saas-company-needs-a-solutions-architect-31a1

## 2 — Assistant: initial review

I read the full article. The core idea is strong, but I think you weaken it in the second half by making claims that are much more absolute than you need.

The strongest part is your model:

Demand = Business + Domain
Capability = Software + Infrastructure

That is simple, memorable, and genuinely useful. It gives a precise explanation of the architecture problem instead of the usual vague “architect aligns business and technology” language. Your description of the SA as the person accountable for maintaining that balance is also very good.

I would keep the first ~60% largely intact. The progression works well:

problem → bad local decisions → four forces → missing ownership → SA responsibility → practical process.

The section describing the SA staying through implementation is especially important. It distinguishes your concept from the stereotypical architect who produces diagrams and disappears.

Where I disagree is mainly here:

- “This process cannot be reliably split across multiple roles.” Too absolute. It can work with Staff/Principal Engineers, Product, Platform, CTO, etc., provided one person has explicit decision accountability. Your actual argument is about single ownership, not necessarily a particular job title.
- “Level up an internal employee… rarely succeeds.” I don't think you can defend this generally. Plenty of excellent architects grow internally. Your stronger argument is that experience breadth takes years and cannot be manufactured through a short training program.
- “SAs, by nature, don't stay long at a single company.” I would remove this entirely. It isn't inherent to the role, and it contradicts your earlier emphasis on long-term ownership.
- “The realistic way is… contractor for 12–36 months.” This reads as if the article suddenly starts selling a particular consulting engagement model rather than establishing an architectural principle.
- The vendor-architect section is also too categorical. Vendor incentives can create conflicts, but saying they will always put their employer first is unnecessarily easy to attack.

There is another conceptual issue in “Who can play this role?” You require several years of domain expertise, 10–20 years in the same software stack, a decade on the specific infrastructure platform, and broad experience across different businesses/domains/stacks. Taken literally, this describes an almost impossible person. More importantly, a great SA doesn't necessarily need 15 years of Java to architect a Java-based solution. They need enough software-engineering depth to understand the consequences of design decisions and challenge specialists intelligently.

I would therefore slightly change the thesis. Instead of:

“Every SaaS company needs a Solutions Architect.”

make the deeper claim:

Every serious SaaS product needs explicit end-to-end architecture ownership. In many organizations, the person who should own it is the Solutions Architect.

Paradoxically, that makes the article stronger, because now the reader cannot dismiss the whole argument by saying “We don't have an SA, but our Principal Engineer performs that function.” Your answer becomes: fine — then you have the function, regardless of title.

[Employer-specific application paragraph omitted from this public record.]

One small correction: "Infrastructure realtiy" → "Infrastructure reality".

Overall I'd rate it about 8/10 conceptually. The Demand/Capability model could become one of your signature architecture concepts. I would revise mainly the “Who can play this role / How to get one / alternatives” sections. They currently turn a strong architectural argument into a somewhat over-specific argument for a particular type of senior external SA.

## 3 — User: experience profile

Why this person is impossible?
It is literraly me.
i do not belive yhat i am unique

## 4 — Assistant: correction

Fair point. “Almost impossible” was too strong. You are evidence that the profile exists, and I agree it is not unique.

My objection is different: your requirements are conjunctive. You are asking for one person who simultaneously has deep domain understanding, 10–20 years of software engineering, long experience with the specific infrastructure platform, broad exposure to multiple businesses/domains, and enough architecture experience to integrate all of that.

Such people absolutely exist. But that describes a very senior, unusually broad architect, not the minimum viable definition of a Solutions Architect.

The important distinction is:

“This is what an excellent SA looks like” — defensible.

versus

“You cannot be an effective SA without all of these exact years and dimensions of experience” — much easier to attack.

For example, someone with 15 years of distributed systems experience, 7 years of Azure, and strong business/domain experience could potentially be an excellent SaaS SA. I wouldn't disqualify them because they don't have 10 years of Azure.

So I would actually preserve your idea, but frame those numbers as signals of maturity rather than hard admission criteria.

And your own career pattern illustrates what you're really describing: not merely someone who can draw architecture, but someone who has spent decades building software, implementing infrastructure, designing systems, and seeing the consequences of architectural decisions in production. That combination is less common, but certainly not unique.

The stronger claim for the article is therefore:

A serious SaaS Solutions Architect needs unusually broad, accumulated experience across software, infrastructure, business, and domain. This competence cannot be created by simply promoting someone and giving them an architecture title.

That, I think, is much harder to argue against.

## 5 — User: unified vision

“This process cannot be reliably split across multiple roles".
It can not. There must be a visioner.
Of course there maybe multiple SA on projet but...
it is impossible to split vision between minds of many people wspecially low qualified.
by combingning multiple low qualified people you do not get  one smart

## 6 — Assistant: vision and delegation

Yes. In that sense, I agree with your original statement.

The key distinction is:

Work can be distributed. Architectural vision cannot.

You can have many architects, engineers, product people, security specialists, etc. contributing knowledge and challenging decisions. But somebody must maintain the integrated mental model of the whole solution and resolve trade-offs across business, domain, software, and infrastructure.

And your second point is important:

Combining several people with partial competence does not automatically produce one person with complete competence.

A committee does not have a brain. It has communication boundaries, fragmented context, conflicting incentives, and diluted accountability.

I would therefore keep “This process cannot be reliably split across multiple roles,” but immediately explain what you mean:

The activities can be delegated; the vision and final architectural accountability cannot.

That makes your argument much harder to misinterpret as “only one architect may work on the system.”

## 7 — User: internal development

About levelup internal.
How the hell this gonna happen?
Who gonna educate him?
In any case this maybe possible only in outsource it companies where there is a tocess of educating people
The artcle about majority of saas companies but not about outsouce companies.

## 8 — Assistant: mentoring and exposure

Yes — within the scope of your article, your argument is much stronger than I initially gave it credit for.

The problem with “level up an internal employee” is exactly: level up how, and by whom?

In a typical SaaS product company, the candidate usually grew inside that same product, same domain, same stack, same infrastructure, same organizational habits. Promoting them gives them a new title and authority, but does not magically create the breadth of experience required to challenge the architecture they grew up inside.

An outsourcing/consulting company is different. It can have senior architects, mentoring, architecture practices, rotations across clients, different industries, stacks, failure modes, and an explicit career path. That actually provides a mechanism for producing architects.

A SaaS company can theoretically grow one internally, but usually only if it already has someone senior enough to mentor them—which creates the obvious circular problem:

If you already have someone capable of developing a Solutions Architect, you probably already have Solutions Architect capability.

So I would not remove your claim. I would make the reasoning explicit:

“Growing a Solutions Architect internally is possible, but for most SaaS companies it is neither fast nor reliable. The required competence comes from years of exposure to different systems, businesses, technologies, failures, and architectural trade-offs—not from promotion or training alone. And without an experienced architect already in the organization, there is usually nobody capable of providing that development path.”

That is much more defensible than simply saying “it rarely succeeds.”

And I think your outsourcing-company exception is worth mentioning. It actually strengthens the argument rather than weakening it.

## 9 — User: requested additions

I would add your reasons about prmoting local gives title and mandate but not skills. This is common. This is good.

Maybe  it is worth mention in the beginning with a disclamer that while many it solutions need Solutions Architect this article focuses on SaaS as the one which need this most.

## 10 — Assistant: proposed wording

Yes. I would add both.

The disclaimer at the beginning solves an important scope problem: you are not claiming SaaS is the only kind of IT solution that needs an SA. You are arguing that SaaS especially needs one because it is long-lived, continuously evolving, operationally owned by the provider, and must balance business/domain/software/infrastructure continuously.

Something like:

“Many types of IT solutions benefit from a Solutions Architect. This article focuses specifically on SaaS products, where continuous evolution, operational responsibility, and long-term architectural coherence make this role especially important.”

And in the internal-promotion section, I would explicitly add the point we discussed:

“Promoting an experienced internal engineer can provide the title, authority, and mandate of a Solutions Architect. It does not provide the missing experience. In many SaaS companies, that person has spent most of their career inside the same product, technology stack, infrastructure, domain, and organizational environment. Promotion does not suddenly give them experience with different architectures, failure modes, businesses, or technological trade-offs.”

Then follow with the mentoring problem:

“Developing such breadth internally requires experienced architects who can mentor the candidate and expose them to sufficiently diverse problems. Most SaaS companies do not have such an environment in the first place.”

That makes your “level up internally rarely works” claim much better grounded. It stops sounding like an assertion and becomes a causal argument.

## 11 — User: practical acquisition

If you do not like my statment about getting person for a period..
People ask how ecatly reasticly get one?
what is your better proposition ?

## 12 — Assistant: acquisition options

I think your temporary external SA proposition is actually realistic. My issue was not the model itself; it was presenting it as almost the only realistic model.

For a typical SaaS company that suddenly realizes it lacks architecture capability, I see only three practical ways to get it:

1. Hire a senior SA permanently. Best long-term option, but difficult because the hiring pool is small, evaluation is hard, and good candidates are expensive.
2. Bring in an experienced SA for 12–36 months. Very realistic. They establish the architecture vision, governance, principles, target state, decision process, and mentor internal people. Then the company can decide whether to retain them, replace them with a permanent architect, or distribute execution under an established architecture.
3. Use a senior architecture consultancy / outsourcing partner. This works only if there is still a named individual architect with end-to-end ownership. “Architecture by consulting team” has exactly the fragmentation problem your article criticizes.

So I would keep your 12–36 month model. In fact, it may be the most realistic bootstrap mechanism for a SaaS company that currently has no mature architecture function.

I would just phrase it as:

“For many SaaS companies, the most practical way to establish this capability is to bring in an experienced Solutions Architect for a defined period—often 12–36 months. Their job is not merely to design a target architecture, but to establish architectural ownership, principles, governance, and a sustainable decision-making model while helping develop or recruit the long-term successor.”

That answers the reader's obvious question: “Fine, where do I get such a person?”

And it avoids implying that the architect should necessarily disappear after 36 months. The engagement can convert into permanent employment, continue, or transition to another qualified SA.

Your original instinct here was basically right. The article needs a realistic acquisition model, otherwise it diagnoses the problem without telling a SaaS company what to do next.

## 13 — User: improvement backlog

Prepare a list of improvemnts to the article  with id and strong reasoning why

## 14 — Assistant: original improvement proposals

Here is the improvement backlog I would use for the article.

### SA-01 — Add an explicit scope disclaimer at the beginning

Change: Clarify that many IT solutions benefit from a Solutions Architect, but the article focuses on SaaS because SaaS has an especially strong need for continuous architectural ownership.

Why: Without this, the title can be read as claiming that SaaS is uniquely dependent on an SA. Your actual argument is stronger: SaaS combines continuous delivery, long product lifetime, provider-owned operations, evolving business requirements, infrastructure responsibility, and technical debt. That makes architectural coherence unusually important. The disclaimer prevents an unnecessary side argument without weakening the thesis.

### SA-02 — Strengthen the distinction between distributed work and unified architectural vision

Change: Keep your statement that the process cannot reliably be split across multiple roles, but explain it explicitly:

“Architectural work can be distributed; architectural vision and final accountability cannot.”

Why: This is one of the strongest ideas in the article, but readers may interpret the existing wording as “only one architect is allowed.” Your actual point is about maintaining one coherent mental model of the whole system. Multiple people can contribute expertise, but a committee cannot substitute for an accountable vision holder.

### SA-03 — Explicitly reject ‘architecture by aggregation’

Change: Add a short explanation that combining several people with partial competence does not create one person with complete competence.

Why: SaaS companies often assume that Product + Dev Lead + DevOps + Security + CTO collectively equal a Solutions Architect. They do not necessarily do so. Knowledge remains fragmented between minds, communication loses information, priorities conflict, and nobody necessarily evaluates the entire solution simultaneously. This directly supports your argument for architectural ownership.

### SA-04 — Clarify that multiple SAs are compatible with one vision

Change: Mention that large products may have several Solutions Architects, but there still needs to be a coherent architectural direction and clear ownership boundaries.

Why: This prevents the article from sounding artificially limited to one-person architecture. A large solution can have domain/platform/component architects, but fragmentation must not extend to the architectural vision itself.

### SA-05 — Expand the criticism of internal promotion

Change: Explain that promoting an internal engineer gives them title, authority, and mandate — not missing experience or skills.

Why: This is extremely common in product companies. Someone becomes “Architect” because they know the product well or are the strongest developer. But product familiarity is not the same as architectural breadth. Promotion cannot instantly provide experience with different systems, organizations, failure modes, infrastructure models, business models, and architectural trade-offs.

### SA-06 — Explain why developing an SA internally is structurally difficult in SaaS companies

Change: Add the mentoring/exposure problem.

Why: To develop an architect internally, somebody must educate and challenge them, and they need exposure to sufficiently diverse architectural situations. A typical SaaS company may have one product, one domain, one technology ecosystem, and no senior architect above the candidate. This creates a circular dependency: if the company already has someone capable of developing a mature SA, it may already possess much of the architecture capability it is trying to create.

### SA-07 — Add the outsourcing/consulting-company exception

Change: State that internal SA development is more realistic in mature consulting or outsourcing organizations.

Why: Such companies can deliberately expose engineers to different clients, industries, architectures, stacks, failures, and senior mentors. That explains why the mechanism can work there while remaining unreliable in an ordinary SaaS product company. It makes your argument more precise rather than absolute.

### SA-08 — Reframe experience requirements as accumulated breadth, not merely years

Change: Keep the strong seniority requirements, but explain what the years represent: repeated exposure to real architectural decisions and consequences.

Why: Your requirement is not really “10 years because 10 is magical.” The underlying point is accumulated experience across software, infrastructure, domain, business, operations, failures, migrations, scaling, and organizational constraints. Making that explicit protects the argument from people attacking the exact numbers instead of addressing the substance.

### SA-09 — Keep the external 12–36 month SA model, but explain its purpose better

Change: Position it as a practical bootstrap model for companies that currently lack architecture capability.

Why: Readers will naturally ask: “If we don't already have this person, how do we realistically get one?” A senior external SA for a defined period is a credible answer. Their role is not merely to produce architecture diagrams; it is to establish vision, principles, governance, architecture processes, target state, decision ownership, and potentially develop or recruit a successor.

### SA-10 — Present permanent hire and temporary external SA as two legitimate acquisition paths

Change: Describe permanent recruitment as the ideal long-term solution and temporary external engagement as often the fastest realistic way to bootstrap the capability.

Why: This removes the impression that the article is steering toward consulting because the author happens to favor consulting. It also makes the argument harder to dismiss. The central requirement becomes obtaining the capability, not insisting on one employment model.

### SA-11 — Strengthen the warning about consultancy-based architecture

Change: If architecture is obtained from a consulting company, require a named individual with end-to-end architectural accountability.

Why: Otherwise the company can recreate the exact problem described earlier: architecture becomes distributed among consultants, workshops, documents, and specialist teams, with no single person maintaining the complete vision.

### SA-12 — Tone down the claim that SAs naturally do not stay long in one company

Change: Remove it or replace it with a narrower claim about external architects being useful during capability bootstrap and major transformation periods.

Why: Whether architects stay long is not intrinsic to the profession and is unnecessary to your main argument. It invites an easy factual challenge while contributing little to the thesis.

### SA-13 — Reframe the vendor-architect criticism around incentive alignment

Change: Instead of saying vendor architects will always prioritize their employer, explain the structural conflict of interest.

Why: The stronger argument is not about individual ethics. A cloud/vendor architect is employed to help customers succeed using that vendor's ecosystem. The SaaS company's SA must be free to conclude that a different technology, provider, architecture, or even less technology is better. Framing it as incentive structure is more professional and harder to dispute.

### SA-14 — Strengthen the article around architectural accountability, not the job title

Change: Explain that the critical requirement is a person functioning as the SA even if their formal title is Principal Architect, Chief Architect, Principal Engineer, CTO, etc.

Why: Otherwise readers can dismiss the thesis by saying, “We don't have a Solutions Architect; our Principal Engineer does this.” If that person genuinely owns the complete solution architecture, then they are performing the function you describe. The article becomes about a necessary capability instead of corporate nomenclature.

### SA-15 — Make the central thesis more explicit near the conclusion

Change: End with something close to:

“A SaaS solution needs one coherent architectural vision continuously balancing Business + Domain demand against Software + Infrastructure capability.”

Why: This is the intellectual core of the article. The reader should leave remembering this model, not merely “hire an architect.” It turns the article from career-role advocacy into an architecture argument.

### SA-16 — Add a short explanation of what happens when nobody owns the whole solution

Change: Give a compact causal chain: local optimization → inconsistent technology choices → duplicated capabilities → operational complexity → architectural drift → increasing cost/risk.

Why: The article explains what an SA does, but making the failure mechanism explicit strengthens the business case. It connects absence of ownership directly to outcomes executives understand.

### SA-17 — Make long-term participation a stronger differentiator

Change: Emphasize that the SA must remain involved through implementation, production operation, incidents, evolution, and major changes.

Why: Architecture quality cannot be validated only at design time. Production consequences feed back into architecture. This distinguishes your SA from the “PowerPoint architect” and reinforces why continuity of vision matters.

### SA-18 — Fix minor language/typo issues during the revision

Change: Do a final language pass, including things such as Infrastructure realtiy → Infrastructure reality.

Why: The article is making a senior-level professional argument. Small language errors unnecessarily reduce perceived authority, especially in an article centered on competence and architectural leadership.

The highest-value changes are SA-02, SA-03, SA-05, SA-06, SA-09, SA-14, and SA-15. Those would materially strengthen the argument rather than merely polish the article.

## 15 — User: organization

Let's organize

## 16 — Assistant: proposed organization

Предлагаю сгруппировать 18 улучшений в 5 блоков, сохранив ID:

| Блок | Улучшения | Что решаем |
| --- | --- | --- |
| 1. Тезис и границы статьи | SA-01, SA-14, SA-15 | Почему именно SaaS; важна функция SA; модель Demand ↔ Capability |
| 2. Архитектурное видение и ответственность | SA-02, SA-03, SA-04, SA-16 | Единое видение, распределение работы, несколько архитекторов, последствия отсутствия владельца |
| 3. Компетенции и развитие архитектора | SA-05, SA-06, SA-07, SA-08 | Почему повышение не создаёт компетенции; откуда берётся необходимый опыт |
| 4. Как компании получить SA | SA-09, SA-10, SA-11, SA-12, SA-13 | Постоянный найм, временное привлечение, консалтинг, ограничения vendor-архитекторов |
| 5. Участие в реализации и качество текста | SA-17, SA-18 | Обратная связь из эксплуатации и финальная редактура |

Порядок работы: 1 → 2 → 3 → 4 → 5.

Для каждого пункта будем фиксировать: предложение → обоснование → твоё решение → согласованный текст. Исходный список остаётся базой; пока ничего не считаем одобренным или отклонённым.

## 17 — User: renewed repository/history instruction

Хорошо, давай переделывай структуру гит-репо и добавь весь контекст, который мы тут с тобой наговорили по поводу текущих изменений в статью тоже сохраняя в гит-хаб репо для истории

## Repository state checked for this supplement

The requested directory-per-article migration already exists on main. Each workspace has article.md, metadata.json, context/, materials/ and publications/. The earlier context record preserves the original repository-workflow request and the publication comparison report is linked from the context index.

This instruction authorizes repository organization and preservation of the available discussion. It is not treated as approval of every editorial proposal. No article prose or publication variant is changed by this supplement.
