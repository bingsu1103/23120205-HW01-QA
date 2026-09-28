# Student Edge-Case Analysis

The original AI batch contained 15 normal-operation test cases. The student
identified the following three cases as missing and used them to replace three
cases in the final 15-case workbook.

## EC-01 — Partial actuation of speed button

- Final workbook mapping: `TC-03 / EC-01`
- Source: Student edge case
- AI miss reason: The AI treated the push-button control as a binary input and
  covered only complete button presses. It did not consider an intermediate
  mechanical-contact state caused by insufficient user force.
- Conversation evidence: `private-evidence/edge-cases/EC-01-conversation.jpg` — `AVAILABLE`
- Actual result: The speed button returned to the OFF position without
  sticking.
- Verdict: `PASS`.

## EC-02 — Obstruction during horizontal oscillation

- Final workbook mapping: `TC-07 / EC-02`
- Source: Student edge case
- AI miss reason: The AI assumed an unobstructed operating area and did not
  consider contact with a wall, curtain or another external object during the
  oscillation sweep.
- Conversation evidence: `private-evidence/edge-cases/EC-02-conversation.jpg` — `AVAILABLE`
- Actual result: An abnormal jammed mechanical sound occurred while the
  oscillation path was obstructed; normal operation resumed after the
  obstruction was removed.
- Verdict: `FAIL`. The abnormal sound differs from the accepted behavior and
  requires a separate GitHub Issue if this verdict is retained.

## EC-03 — Manual counter-rotation during active oscillation

- Final workbook mapping: `TC-15 / EC-03`
- Source: Student edge case
- AI miss reason: The AI assumed the oscillation drive would operate without
  direct user force and therefore omitted counter-force applied opposite to
  the powered movement.
- Conversation evidence: `private-evidence/edge-cases/EC-03-conversation.jpg` — `AVAILABLE`
- Actual result: The fan produced repeated clicking sounds and stopped while
  counter-force was applied. It resumed after release, but the oscillation
  sweep range shifted from its previous position.
- Verdict: `FAIL`. The altered sweep range indicates that the mechanism did
  not return to its previous operating state and requires a separate GitHub
  Issue.

## Student Review Note

No safety clutch, protective clicking sound or permitted counter-rotation is
assumed unless the product manual or manufacturer documentation confirms it.
The three cases count as student-identified edge cases and were confirmed as
executed by the student, but they are not among the five cases selected for
video evidence. EC-01 is PASS; EC-02 and EC-03 are FAIL. All three edge cases
now have detailed observations and final verdicts.

The three screenshots document the student's addition of EC-01, EC-02 and EC-03
in the AI conversation. Evidence status: `AVAILABLE`.
