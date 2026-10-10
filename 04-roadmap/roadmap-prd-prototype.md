# Roadmap, PRD & Prototype (Module 4)

## Your strategic anchors
- **Persona (M2), who are you solving for?:** Mara, a consumer in the Germany pilot. Her income is stable but varies with shift work. She has one or more open claims and little time. After a digital reminder she starts the instalment journey alone on her smartphone and wants a plan she can keep, without making her situation worse.
- **Primary success metric (M3), your leading indicator:** The share of starters who see all four points in the portal before deciding and do not contact an agent within 7 days: an affordable instalment, why income is requested, what a missed payment means, and whether both claims can be combined. Today, 31% of starters contact an agent within 7 days. A feature that does not reduce this share cannot score 5 on value.
- **Moment of misery (M2), the specific friction blocking the goal:** On the smartphone the journey asks for proof of income while it is still unclear whether the instalment is affordable, why income is requested, what a missed payment triggers, and whether both claims can be combined. Mara cannot tell whether the plan will make her situation worse, so she abandons the journey or calls.
- **Guardrail metric (M3), what must not drop or break:** The share of new instalment agreements kept through the first 60 days must not fall below 81%. Today, 19% of new agreements miss a payment within 60 days. The self-service rate does not protect this base, because it counts a plan as a success the moment it is created.

## Scan the backlog & set a human baseline
- **My instinctive “quick wins” before touching the AI (2 to 3 feature IDs + why):** 1) Digital installment plan
Rationale: Direct link to the core problem—consumers should be able to independently agree on a viable installment plan.

2) Affordability check
Why: Particularly relevant because, according to the briefing, consumers are unsure what constitutes an affordable plan, and new agreements sometimes fail early on.

## Audit, override & decide
- **Where did you override the AI? (feature + old vs. new score + why):** Variable-income input: Score 4 → 5. Mara’s shift range is the reason why a single figure does not represent a sustainable rate. Without the range, one of the four points is formally demonstrated yet remains incorrect for her case.
Document guidance and quick check: Score 4 → 5. The quote states that she calls when requested documents cannot be found. Subsequently, 28% of uploads require clarification, and 31% of those who started the process call within 7 days. This represents the call-related component of the primary metric.
Agent handoff summary: Score 3 → 2. The M2 friction occurs prior to the call. The 31% figure counts contacts, not rework. The effort level exceeding 50% does not substantiate the handoff.
Plan confirmation and payment reminders: Score 3 → 2. The 19% figure indicates the drop-off rate, not that a reminder causes it. The guardrail protects the affordability rule; the reminder does not.
Outcome instrumentation: Score 3 → 4. M3 indicates that the drop-off is not visible in the portal. Without measurement, the 31% figure and the 81% compliance rate cannot be validated. A score of 5 remains incorrect because nothing changes on the smartphone interface.
- **Did the AI over-value a Sales/Eng request your M2 interviews don’t support?:** Yes. "Build instrumentation first" is a development preference. It measures the leading indicator but does not eliminate it, and is therefore excluded from the "snapshot" analysis. The handover to Daniel also had an excessively high value of 3: M2 supports Mara’s cancellation and call, not an internal summarization tool.
- **Did it underweight something your M3 cohort/funnel data strongly supports?:** Yes. The documentation support was rated a 4, even though 28% of the evidence requires clarification and the call is directly linked to the citation. Instrumentation was rated a 3, even though the funnel currently cannot show the drop-off point or the 60-day adherence rate.

## Generate your interactive roadmap
- **My “Now” lane (this sprint), the 2 to 3 quick wins I’ll build first:** 1) “Why we ask” appears alongside every income-related question. Mara can see the reason for the income inquiry. 

2) Explanation of consequences before submission. Before confirming, she is informed of the consequences of a missed payment or incorrect information, and she can still make changes.

3) Guidance on documentation and a quick check. It is clear which proofs are accepted and what alternatives suffice. Providing proof doesn't turn into a phone call; currently, 28% of uploads require follow-up clarification.
- **What I cut, and the “no” I’m protecting the scope from:** The AI ​​image-quality check and full comparison instrumentation have been cut; both are time-consuming. The simple notification and alternative-option logic accounts for the 28%. The granular measurement of 7-day contact and 60-day retention rates is being deferred to the "Next" phase.

The bottom line is: in this sprint, there is no image check, no extensive comparison step, no reminders, and no summary for Daniel. The scope is limited to the smartphone response provided before Mara disconnects or calls.
- **Prototype/roadmap screenshot link (paste into your deliverables):** revised version: spotlight-roadmap.png
first Version: spotlight-roadmap.html
