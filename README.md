# Presales Scoping Helper

A single-page tool for sizing a financial-services implementation before a statement of work is signed. Enter what the client has asked for and it returns:

- a scoped go-live date, checked against the client's requested date (Achievable, Tight or Not achievable as scoped)
- a week-by-week timeline
- person-days by workstream, with governance, contingency and hypercare shown separately
- team size
- options for closing a gap when the date does not fit (add people, phase reporting, cut a UAT round, move the date)
- risks to raise, assumptions to state in the proposal, and questions to ask the client
- a plain-text summary you can copy

## Run it

Open `index.html` in a browser. There is no build step and no dependencies. Fonts load from Google Fonts and fall back to system fonts when offline.

## Read this before using the numbers

The effort rates are rules of thumb, not calibrated figures. Examples: 9 person-days per integration, 5 per custom dashboard, governance at 10% of delivery effort. The estimate is a starting point for a scoping conversation, not a quote. Calibrate the rates against your own closed engagements before relying on the output.

Known limitations:

- Team size changes in steps (4, 6, 8 or 10 people) at fixed effort thresholds, so a small change in scope can move the timeline by several weeks.
- Duration assumes the effort can be spread evenly across the team. Task dependencies are not modelled.
- Timeline bars use fixed shares of the total duration.
- Public holidays and client freeze periods are not modelled.

## Where to change the model

The estimation logic sits between the `MODEL-START` and `MODEL-END` comments in the script of `index.html`.

## Optional: Claude analysis

When the page is opened inside the Claude artifact viewer, an extra "Analyse with Claude" panel can read pasted client requirements and fill in the drivers the text supports. This panel stays hidden when the page is opened as a normal file or website, and everything else works the same.
