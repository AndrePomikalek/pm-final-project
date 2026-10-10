# Affordability guidance, not just a maximum., Simplified PRD (Your Riverty case)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** Mara, a consumer from Germany

## 1. The Big Picture
- **Vision:** To eliminate the moment when Mara cannot tell whether the instalment is affordable, by preselecting a comfortable instalment and explaining in one sentence why it fits the income she already entered.
- **Press release:** Today, Riverty launched affordability guidance in the instalment journey for the Germany pilot. Before Mara agrees, she sees a preselected instalment below the maximum and one sentence on why it fits her income. The highest instalment is not the suggestion.

This ends the moment on her phone when she cannot tell whether the plan will make her situation worse, and abandons the journey or calls. She does not have to search, calculate it herself, or upload proof.
- **Success metric:** Share of starters who see the comfortable instalment and the reason before deciding, and do not call within 7 days. Today, 31% call.
- **Guardrail:** The share of new agreements kept through the first 60 days stays at or above 81%. Today, 19% miss a payment.

## 2. The Details
### User stories
- As Mara, I want a comfortable instalment preselected, so that I can tell the plan is affordable before I agree.
- As Mara, I want one sentence on why that instalment fits the income I already entered, so that I do not have to calculate it myself.
- As Mara, I want the highest instalment not to be the default, so that I do not agree to a payment I cannot keep.
### Screens to build
- 1) Entry: the plan step opens with the income figure already stored. No new income field.
- 2) Core: one comfortable instalment is preselected and marked, with one sentence of reasoning beside it. The maximum is shown and is not selected.
- 3) Confirmation: the chosen monthly instalment and the same reason are repeated. She can only reach this screen from the core screen.
### Functional requirements
- The system must preselect exactly one instalment.
- The preselected instalment must be strictly below the maximum monthly amount.
- The preselected instalment must be labelled as comfortable.
- The maximum instalment must be visible and must not be preselected.
- The system must show one sentence of reasoning on the same screen as the instalment.
- That sentence must include the income amount already stored in the journey.
- The confirmation screen must stay closed until both the comfortable instalment and the sentence are rendered.
- The confirmation screen must repeat the selected monthly amount.
### Smart behaviors (Situation → Outcome)
- When Mara opens the plan step with an income figure in state, the system preselects a comfortable instalment below the maximum.
- When that instalment is shown, the system writes one sentence that names her stored income figure.
- When she confirms, the system keeps that instalment and shows it on the confirmation screen.
- When no income figure is stored, the system shows no instalment and no reason.
### Technical constraints
- No external API calls. No database. React useState only.
- No model, no income-range field, no document upload, no combining of claims, no missed-payment copy, and no reminders.
- The income figure and the maximum are fixed values already in state.

## 3. The Logistics
### Features out
- No login, settings, or history. No income-range field, document upload, combining both claims, missed-payment copy, reminders, or a model that sets the rate.
### Edge cases & safety guard
- No income stored → show no instalment and no reason.
- The only permitted rate is the maximum → do not label it as comfortable and do not preselect it.
- Safety: never invent an income figure or a rate.
### Decision log
- The model was removed to keep one readable rule: a comfortable instalment below the maximum, plus one sentence.
- Extra options, proof, both claims, missed-payment consequences, and reminders were removed to stay on that single result.
### Evals
- Rule match ≥ 90%: with a stored income, the preselected instalment is below the maximum and the sentence names that income.
- Render time under 100 ms, from state only, with no network wait.
- Safety: 0 invented incomes or rates, and the maximum is never preselected.

## MoSCoW scope
- **Must:** The preselected instalment is below the maximum and is marked as comfortable.; One sentence of reasoning, tied to the income figure she already gave in this journey.
- **Should:** A lower and a higher option beside the suggestion. The higher one is not preselected.; The monthly amount and the term in months appear in the same view.
- **Could:** The total amount over the full term.; A note that the instalment still holds at the low end of a typical month.; Won't have (now)
- **Won't (now):** A rate set by a model with no readable rule.; The highest permitted instalment as the default.; A new income range, proof of income, combining both claims, missed-payment consequences, or reminders on this step.

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
