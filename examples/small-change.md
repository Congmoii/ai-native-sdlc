# Example: change a button label

This is an illustrative walkthrough, not a record of an executed application test.

**Request:** Change the checkout button from "Continue" to "Review order" without changing its behavior.

**Path:** Small change. The request already provides the text and scope.

**Approach:** Find the checkout button and any existing assertion tied to its accessible name. Update the label and a related assertion if that assertion intentionally describes the label. Check the diff and inspect the affected screen when a preview is available.

**Record:** A short task note is enough. No three-document feature packet is needed.

**Handoff:** State the actual label change and checks performed. If no preview could run, say that visual verification was not performed. Do not claim the application was deployed.
