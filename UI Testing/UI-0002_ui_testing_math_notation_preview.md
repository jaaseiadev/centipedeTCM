## **ID:** UI-0002 Math notation preview renders correctly

### Summary
Validates that math notation input or preview areas render mathematical content in a readable format.

### Priority
Medium

### Preconditions
- Tester is authenticated as an organizer or mathlete depending on the page being tested.
- A page with math notation input or preview is available, such as problem authoring or arena answer entry.
- Tester has sample notation such as `x^2 + 2x + 1` or a fraction expression.

### Scenario 1

| Step # | Action | Expected Behavior |
| --- | --- | --- |
| 1 | Open a page with math notation input or preview. | The page loads the math input or preview component. |
| 2 | Enter a sample expression. | The raw input is accepted without unexpected character loss. |
| 3 | Review the preview. | The expression renders in readable math formatting. |
| 4 | Edit the expression. | The preview updates to match the edited expression. |
| 5 | Clear the expression. | The preview clears or shows a safe empty state. |

### Post-conditions
- No invalid problem or answer is saved unless the tester explicitly saves a valid form.

### Notes
- Current feature evidence: MathLive and KaTeX are dependencies in the current app.
- Related current coverage: `tests/math/latex-validation.test.ts`, `tests/ui/problem-form.test.tsx`, and `tests/ui/arena-experience.test.tsx`.
