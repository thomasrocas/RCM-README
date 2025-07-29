# Queue Manager Dashboard – RCM System

## Overview

The **Queue Manager Dashboard** is an HTML-based front-end interface designed to manage claims queues in a Revenue Cycle Management (RCM) system. It supports dynamic filtering, real-time insights, data export, FileMaker integration, and interactive actions (View, Close, Duplicate) for each claim record.

## Features

- ✅ Multi-level filters with persistent localStorage settings
- ✅ Sidebar navigation with feather icons and FileMaker scripting
- ✅ Interactive DataTable with:
  - Custom column visibility
  - Row color highlighting (overdue, due this week, high priority)
  - Inline action buttons: View, Close, Duplicate
- ✅ Insight widgets: Total Records, Unassigned, High Priority, Overdue Claims
- ✅ Batch processing with FileMaker scripting
- ✅ CSV export of filtered results

## Technologies Used

- HTML5, CSS3, JavaScript (ES6)
- [DataTables.js](https://datatables.net/)
- [Feather Icons](https://feathericons.com/)
- [Select2.js](https://select2.org/) for enhanced dropdowns
- FileMaker `PerformScript` integration for backend logic

## Setup Instructions

1. **Load HTML File**:
   - Serve it from a local web server or load into a FileMaker Web Viewer.
   - Ensure all script/CDN links are accessible in your environment.

2. **Data Integration**:
   - Data is initialized via `rawData` in the script block.
   - Replace or inject with live data from FileMaker via script.

3. **FileMaker Script Triggers**:
   - `OpenPanelRecord`: Opens a queue record in FileMaker.
   - `LockPanelRecord`: Closes (locks) a queue.
   - `DuplicateQueue`: Duplicates the queue record.
   - `BulkProcessSelectedClaims`: For batch actions.
   - `PSOS | QueueUpdate`: Triggers a server-side queue refresh.

4. **Persisted Settings**:
   - Filters are stored using `localStorage` and restored on load.
   - "Reset" button clears all saved filter state.

## Filters Available

- Assigned To
- Admin
- Status
- Patient
- Payor Name
- Parent Unit
- Source Table
- Priority
- RFNP
- Highlights: Overdue, Due This Week, High Priority
- Date Range (by Bill Date, Start Date, End Date, Due Date)

## UI Highlights

- 🔴 **Overdue**: Red rows
- 🟡 **Due This Week**: Yellow rows
- 🟠 **High Priority**: Orange rows

## Usage Tips

- Use the right sidebar filters to narrow results
- Action buttons per row allow quick FileMaker scripting
- Use `Select All` header button to batch select/deselect rows
- Click `BatchProcess` to bulk send selected records to FileMaker
- Use `Export` to download visible data as CSV

## Customization

- Modify `rawData` to accept dynamic payloads
- Adjust column definitions via `columns` array
- Override or expand `FileMaker.PerformScript` calls to fit business logic
- Add additional insights or KPIs in the `.insights` section

## License

Private use only — intended for internal deployment within ANX RCM systems.

---

