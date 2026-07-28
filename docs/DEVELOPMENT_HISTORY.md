# Retrospective Development History

> This is an honest reconstruction from project conversations, source material, handoff documentation, and the saved production checkpoints. It is not presented as the repository's original Git commit history. The application was developed before this public portfolio repository was created.

## 1. Workflow Discovery

The project began with the UMKC NSBE Executive Board's need to manage Monthly Activity Reports in one place. The existing process was fragmented across calendars, forms, files, and conversations.

The initial product requirements were:

- Preserve the approved activity schedule.
- Show reporting progress at full-year, semester, month, and week levels.
- Organize activities by NSBE programming lane and subcategory.
- Keep event information, supporting files, and Board feedback connected.
- Make the tracker usable by multiple Board members.
- Leave enough documentation for future chapter leadership.

## 2. Source Reconciliation

The source material was treated as authoritative. No new event was invented without chapter approval.

The baseline became:

- 53 base activity IDs, `NSBE-001` through `NSBE-053`
- 100 total reporting rows
- 95 dated occurrences
- 5 undated activities
- 53 Fall 2026 reports
- 47 Spring 2027 reports

Repeated occurrences were counted as separate reports while retaining their source identity. Missing and conflicting details were preserved through source-issue flags so uncertainty could be resolved rather than erased.

## 3. Information Architecture

A single master event record became the foundation for every view. This prevented separate dashboards, lists, and forms from drifting into inconsistent copies.

The application was organized into:

- A full-year and semester dashboard
- A searchable and sortable master list
- Month, week, status, lane, and undated views
- An Event Details Form
- A separate Executive Board Comments workspace
- File-upload and preview controls

## 4. Programming-Lane Model

The application formalized six programming lanes and their subcategories.

The classification rule became **fit first, balance second**. The reporting purpose determines the best lane; distribution counts help only when more than one lane is genuinely appropriate. Pre-Collegiate Initiative requires direct K–12 involvement, while ordinary meetings, socials, membership activities, and fundraisers belong in Functional Zone Initiatives.

The interface later allowed lane and subcategory changes more than once while updating distribution totals.

## 5. First Functional Tracker

The first functional system established:

- Stable NSBE IDs
- Report titles and dates
- Semester and month grouping
- Three states: **Not Started**, **Gathering Information**, and **Submitted**
- Red, yellow, and green visual status feedback
- Search, filtering, and sorting
- An editable event-details form
- Shared record saving

## 6. Review and File Workflow

Review features grew from a general review area into a dedicated Executive Board workflow.

Important decisions included:

- Renaming **Leadership Review** to **Executive Board Comments**
- Separating Board feedback from event details
- Replacing ambiguous **Evidence** terminology with supporting-file language
- Supporting multiple comments and multiple attachments
- Allowing comment edits
- Supporting single and multi-select deletion
- Displaying comment counts in report views

## 7. Navigation and Responsive Design

The interface was repeatedly refined around the way Board members moved through reports:

- Clickable dashboard totals and status summaries
- Collapsible sidebar and compact semester navigation
- Fall and Spring minimized navigation controls
- Clear-filters behavior
- Stable ascending and descending sorting
- Removal of unnecessary table controls
- Responsive desktop, tablet, and phone layouts
- A compact upload area
- A How to Use guide that opens separately

The product name was standardized as **Monthly Activity Report**, the name used by the Executive Board.

## 8. State and Performance Corrections

Testing exposed several interaction issues that were corrected:

- Status changes initially felt delayed during rapid updates.
- Save feedback needed a clear success state.
- Refreshes needed to preserve the current view.
- Browser back and forward navigation needed to restore routes.
- Route restoration briefly exposed the dashboard before the intended view.
- A single filtered result should remain in the list instead of opening automatically.
- Lane and subcategory counts needed to refresh after repeated reclassification.

The resulting behavior uses manual save feedback, route persistence, browser-history support, and conflict-aware record merging.

## 9. Shared Storage Architecture

The application was packaged as a Worker-compatible JavaScript service:

- `/api/events` reads and writes shared event records.
- D1-compatible storage keeps each event as a JSON document plus freshness metadata.
- `/api/files` manages supporting-file operations.
- R2-compatible storage holds file bytes under event-specific keys.
- The client falls back to the approved seed dataset when shared records are unavailable.

This provided a compact deployment path while leaving modularization and automated tests as future work.

## 10. Production Stabilization and Handoff

By July 27, 2026, the production site had reached saved version 71.

The handoff package documented:

- The current dataset and classification rules
- The application structure and workflows
- Operational limitations
- The need to preserve record IDs, statuses, details, comments, uploads, shared saving, and the existing production site during future maintenance
- The distinction between tracker status and official national report submission

The public GitHub repository was created afterward as a safe engineering portfolio. It contains application source and seed data, but excludes production records, uploads, comments, and the operational editing URL.

## Continuing History

Future work should be recorded through normal Git commits, pull requests, and issues. The retrospective ends at the creation of the public portfolio repository; new repository activity is the live development record.

