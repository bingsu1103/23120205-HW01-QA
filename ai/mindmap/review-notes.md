# Review of the AI-Generated QA/QC Mindmap

## Review status and source

- Original artifact: `ai/mindmap/ai-original.md`
- Reference: ISTQB Certified Tester Foundation Level Syllabus v4.0.1, Sections 1.4.1, 1.4.3 and 1.4.4
- Official source: <https://istqb.org/wp-content/uploads/2024/11/ISTQB_CTFL_Syllabus_v4.0.1.pdf>
- Review method: compare every activity and work-product branch in the AI output with the corresponding ISTQB list.
- Authorship disclosure: the three issues below were identified with OpenAI Codex assistance in `PROMPT-05`. The student must read the cited sections and be able to explain each correction during the oral defense.

The main activity sequence and the two principal testing roles in the original output are consistent with ISTQB. The review therefore does not treat those correct parts as mistakes. Exactly three independent classification or completeness problems are recorded below.

## Mistake 1 — Traceability was classified as a test-analysis work product

- **Exact AI statement:** Under `Important Test Work Products > Analysis Work Products`, the AI listed `Traceability links`.
- **Classification:** Misclassified.
- **ISTQB basis:** Section 1.4.3 lists prioritized test conditions and defect reports regarding defects in the test basis as test-analysis work products. Section 1.4.4 treats traceability as a relationship maintained throughout the test process between the test basis, testware, test results and defects.
- **Why this is a problem:** Putting traceability links only under test analysis implies that traceability belongs to one activity. This hides its cross-cutting use in coverage evaluation, change-impact analysis, monitoring, reporting and audits.
- **Correction:** Remove `Traceability links` from `Analysis Work Products` and add a separate `Cross-cutting Traceability` branch connecting the test basis, test conditions, risks, test cases, results and defects.

## Mistake 2 — Monitoring/control work products did not match the ISTQB set

- **Exact AI statement:** Under `Monitoring and Control Work Products`, the AI listed `Test progress reports`, `Updated plans and schedules`, and `Test control directives`.
- **Classification:** Incomplete and partly unsupported classification.
- **ISTQB basis:** Section 1.4.3 lists test progress reports, documentation of control directives, and information about risks as test monitoring and test control work products.
- **Why this is a problem:** The AI omitted `information about risks`, which is explicitly listed by ISTQB, and substituted `updated plans and schedules`. Updating a plan or schedule can be a consequence of test control, but it is not part of the specific work-product list given in Section 1.4.3.
- **Correction:** Use the three ISTQB items: `Test progress reports`, `Documentation of control directives`, and `Information about risks`.

## Mistake 3 — Completion work products mixed an activity with a deliverable and omitted required outputs

- **Exact AI statement:** Under `Completion Work Products`, the AI listed `Test completion report`, `Archived testware`, `Lessons learned`, and `Improvement actions`.
- **Classification:** Misclassified and incomplete.
- **ISTQB basis:** Section 1.4.1 says useful testware is identified and archived or handed over as a test-completion activity. Section 1.4.3 lists the completion work products as the test completion report, action items for improvement, documented lessons learned, and change requests such as product backlog items.
- **Why this is a problem:** `Archived testware` describes the result of an archiving activity but is not one of the completion work products in the syllabus list. The AI also omitted `change requests`, which are required for unresolved defects, change requests or backlog work arising at completion.
- **Correction:** Replace `Archived testware` in the work-product list with `Change requests or product backlog items`; retain archiving or handover under the `Test Completion` activity. Use `Action items for improvement` and `Documented lessons learned` as the other completion outputs.

## Student confirmation checklist

- [ ] I read Sections 1.4.1, 1.4.3 and 1.4.4 of the cited syllabus.
- [ ] I can explain why traceability is cross-cutting rather than analysis-only.
- [ ] I can name the three monitoring/control work products without looking at this file.
- [ ] I can distinguish archiving testware as an activity from the listed completion work products.
- [ ] I accept these corrections as my final reviewed version.
