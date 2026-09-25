# Example: product search

An illustrative packet showing how intent, spec, and plan fit together. File names in the plan are hypothetical. No checks or approvals in this example represent executed work.

## User request

Add product search by name to the catalog. Ignore case and surrounding spaces. An empty query should show all products. Keep the current page's sort order. Implement and verify locally.

## Intent

**Problem:** Users have to browse the entire catalog to find a product they already know.

**Outcome:** Users can narrow the catalog by entering part of a product name.

**Scope:** The existing catalog and name field. No new search service, analytics, category filtering, or production release.

**Constraint:** Reuse the existing data source and visual conventions.

**Open decision:** The request says "search by name" but does not specify substring versus exact matching. Confirm substring matching if project behavior does not already resolve that decision. The acceptance criteria below assume that decision has been established; they do not record an actual user approval.

## Spec

| ID | Situation | Expected outcome |
| --- | --- | --- |
| AC-1 | Query is `lamp` | Names containing `lamp` are shown, preserving current order |
| AC-2 | Query is `  LAMP  ` | Results match AC-1 |
| AC-3 | Query is empty or spaces only | All current catalog products are shown |
| AC-4 | No names match | Show an empty-results message |
| AC-5 | Search is cleared | Restore the full current catalog |

**Interaction:** Give the search field an accessible label. Keep keyboard access and existing product navigation working. Preserve the existing loading and error presentation.

**Data:** Search existing product names. Avoid changing product records.

## Plan

First inspect where the catalog is loaded, filtered, sorted, and rendered. Replace these illustrative component names with the actual ones after inspection.

1. Add or reuse the name-filtering function near `catalog/search`.
2. Wire a search field into the catalog view.
3. Apply filtering without changing the established sort order.
4. Add behavior tests for AC-1 through AC-5.
5. Run the applicable project checks and exercise the rendered interaction.

**Risk:** A server-paginated catalog may contain only part of the data on the client. Inspect that boundary before choosing client-side filtering; searching only the loaded page could silently miss products.

**Proof:** Filter tests demonstrate matching, whitespace handling, case handling, empty input, and ordering. An interaction check demonstrates entering and clearing a query. A visual check examines the search field and empty state in relevant layouts.

## Handoff shape

Summarize actual behavior, changed components, acceptance results, and limitations. Name the version or working-tree state checked. Record release status as not requested. Until the checks run, verification remains not run.
