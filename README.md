# UMKC NSBE Monthly Activity Report

### Executive Board Reporting Tracker · 2026–2027

A shared web application for organizing events, tracking report progress, reviewing event details, and recording Executive Board feedback.

## [Open the Monthly Activity Report](https://umkc-nsbe-submission-hub.amx42.chatgpt.site)

> **Portfolio visitors:** The link opens the operational tracker. Please view only—do not change statuses, comments, event details, or attachments.

## Project at a Glance

| | |
|---|---|
| **Project lead and developer** | Abreham Mesfin |
| **Organization** | National Society of Black Engineers — UMKC Chapter |
| **Reporting cycle** | Fall 2026–Spring 2027 |
| **Reports organized** | 100 |
| **Technology** | JavaScript, HTML, CSS, Cloudflare Worker, D1, and R2 |

## What I Built

- Centralized a fragmented reporting process into one shared application.
- Organized 100 activity reports across Fall 2026 and Spring 2027.
- Built dashboards for full-year, semester, month, week, status, and programming-lane progress.
- Added event search, filters, sorting, classification, and source-issue tracking.
- Created Event Details and Executive Board Comments workflows.
- Added multiple file uploads, previews, editing, and selective deletion.
- Supported responsive mobile and desktop layouts, browser history, and shared saving.
- Added conflict-aware merging to protect updates when multiple people work simultaneously.

## Quick Guide

1. **Open the report** using the link above.
2. **Choose a reporting period:** Full year, Fall 2026, or Spring 2027.
3. **Find an event** by its name or NSBE ID, or use the filters.
4. **Review progress** using the dashboard totals and status cards.
5. **Open Event Details** to review activity information and supporting files.
6. **Open Executive Board Comments** to review feedback connected to an event.

## Submission Status

| Status | Meaning |
|---|---|
| **Not Started** | Reporting work has not begun. |
| **Gathering Information** | The report is being prepared or information is missing. |
| **Submitted** | Event details and supporting files are complete. |

## Repository Structure

```text
worker/index.js              Application interface, data, API, and storage logic
package.json                 Build configuration
.openai/hosting.example.json Safe deployment-configuration example
```

The public repository contains the application source and original seed schedule. It does not contain saved production comments, uploaded files, or database records.

---

Designed and developed by **Abreham Mesfin** for the **UMKC NSBE Executive Board**.
