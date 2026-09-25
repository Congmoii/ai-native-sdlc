# Example: the empty cart shows an invalid total

This is an illustrative walkthrough. The observations below describe what to collect, not results from an executed test.

**Request:** Fix the cart total becoming invalid after the last item is removed.

**Expected behavior:** An empty cart displays zero in the existing currency format. Removing an item preserves the totals of any remaining items.

**Path:** Bug fix.

1. Inspect the cart calculation and existing tests.
2. Reproduce removal of the last item. Capture the invalid output and determine whether the failure comes from calculation or formatting.
3. Add or identify a check that fails on the original defect. An unrelated setup failure does not count.
4. Repair the responsible logic, preserving the intended currency behavior.
5. Run the original reproduction and relevant cases for one and several remaining items.
6. Review the implementation and test changes together.

**Record:** Expected and actual behavior, reproduction, relevant components, repair, and the observed before/after results.

**Handoff:** Report the checks that actually ran. If the runtime was unavailable, describe the proposed patch and the verification still needed; do not call the bug confirmed fixed.
