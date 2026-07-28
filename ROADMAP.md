# Engineering Roadmap

This roadmap turns known limitations into visible, testable engineering work. Priorities protect chapter data and operational continuity before adding convenience features.

## Priority 1 — Safe Public Demonstration

### Read-only portfolio mode

**Goal:** Let recruiters explore the experience without gaining access to operational records or write actions.

Acceptance criteria:

- Uses demonstration data only
- Displays a clear demo banner
- Disables event edits, comments, uploads, and deletion
- Contains no production project ID, database content, or operational URL
- Works on desktop and mobile

### Role-based access

**Goal:** Separate viewers, contributors, and administrators.

Acceptance criteria:

- Unauthenticated users cannot modify records
- Contributors can update assigned workflow fields
- Administrators can manage records and access
- Sensitive actions have explicit confirmation
- Access decisions are tested and documented

## Priority 2 — Maintainability and Quality

### Modularize the Worker

**Goal:** Split the compact entry point without changing behavior.

Proposed boundaries:

- Seed data and validation
- Client templates and styles
- Route and view state
- Event API
- File API
- D1 repository
- R2 repository

Acceptance criteria:

- Production behavior remains unchanged
- Build output remains Worker compatible
- Data and storage interfaces are documented
- No operational data is copied into source control

### Automated tests

**Goal:** Protect reporting logic and navigation during future changes.

Initial coverage:

- Semester, month, week, and undated counts
- Programming-lane distribution
- Status transitions
- Conflict-aware record merges
- Route restoration and browser history
- File-size and request validation

## Priority 3 — Annual Operations

### Schedule import and export

**Goal:** Replace manual source editing for each academic year.

Acceptance criteria:

- Validates required fields and stable IDs
- Previews additions, changes, and removals before import
- Preserves source issues instead of silently discarding records
- Exports a chapter archive without uploaded file bytes
- Requires confirmation before replacing an active schedule

### Configurable reporting taxonomy

**Goal:** Let future Boards update lanes and subcategories without editing application code.

Acceptance criteria:

- Stores a versioned taxonomy
- Preserves existing record classifications
- Shows the effect of taxonomy changes before saving
- Documents annual review responsibility

## Priority 4 — Reporting and Auditability

### Archive exports

- Export progress summaries by semester and month
- Include source issues and outstanding fields
- Exclude sensitive attachments by default

### Visible change history

- Record who changed a report, what changed, and when
- Preserve prior values for recovery
- Provide administrators with filtered audit views

## Contribution Approach

Roadmap work should use one issue and one focused branch per change. Pull requests should explain:

- The chapter problem being solved
- The affected workflow and data
- Privacy and migration risks
- Tests performed
- Screenshots that contain demonstration data only

