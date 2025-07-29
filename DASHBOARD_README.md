# ARDashboard: Interactive Revenue Cycle Management Dashboard

## Overview

The ARDashboard is an advanced, interactive web-based analytics tool for healthcare revenue cycle management (RCM). It provides dynamic visualizations, powerful filtering, and integrated workflows to track outstanding claims, aging categories, payor performance, staff assignments, and billing statuses across Home Health and Hospice services.

## Features

### 🔹 Charts & Visualizations
- **Aging A/R by Bucket**: Bar chart showing balance distribution by aging category (0–30 to 366+).
- **Payor Distribution**: Bar chart displaying claim balance by payor name.
- **Claim Status Summary**: Horizontal bar chart visualizing claim distribution by queue status.
- **RFNP (Reason for Non-Payment)**: Categorical bar chart representing common RFNP values.
- **DSO Trends**: Line chart tracking average Days Sales Outstanding (DSO) by month.
- **Follow-Up Status by Staff**: Stacked bar chart showing queue statuses grouped by assigned staff.

### 🔹 Dynamic Data Table
- Scrollable, paginated, and sortable table.
- Columns include: ClaimID, MRN, Patient, Payor Name, Bill Date, No. of Days, Start/End Date, Balance, Parent Unit, and Action.
- Zoom controls with persistent zoom level and history.

### 🔹 Filters
Accessible from a collapsible right panel:
- Parent Unit (e.g., Home Health, Hospice)
- Payor Name
- Assigned To
- Status
- RFNP
- Aging Buckets
- Date Range (customizable by field like Bill Date or Event Date)
- Negative Balance only (toggle)

### 🔹 Highlight & Multi-Select Filters
- Clicking chart bars temporarily highlights filtered datasets.
- Multi-highlight support across aging, payor, status, RFNP, and DSO charts.
- Filter interactions do not alter the UI state—ideal for exploratory analysis.

### 🔹 Persistent State
- All filters, highlights, zoom settings, and view states are saved to `localStorage` and persist across sessions.

### 🔹 FileMaker Integration
- Sidebar navigation triggers FileMaker scripts via `FileMaker.PerformScript`.
- Table “View” button calls `ViewMessagesDashboard` with the selected ClaimID.

## File Structure

- `rawData`: The primary dataset (JSON) embedded directly in the HTML.
- `<canvas>` elements: Dynamically populated by Chart.js charts.
- Filters and highlights: Powered by Tagify.js and custom filter logic.
- DataTable: jQuery DataTables with export, column reordering, and fixed headers.

## Dependencies

- [jQuery](https://jquery.com/)
- [Chart.js](https://www.chartjs.org/)
- [Tagify](https://yaireo.github.io/tagify/)
- [DataTables](https://datatables.net/)
- [Feather Icons](https://feathericons.com/)

## Usage Instructions

1. **Open in Browser**: Simply open the `ARDashboard_20250619 (35).html` file in any modern browser.
2. **Filter Data**: Use the right panel to narrow results by units, payors, dates, etc.
3. **Interact with Charts**: Click bars to isolate data without changing filter state.
4. **Analyze Trends**: Hover over charts for detailed breakdowns.
5. **View Details**: Click “View” in the table to trigger associated FileMaker workflows.
6. **Zoom Table**: Use the + / - buttons to adjust data table zoom level.

## Developer Notes

- **Highlight Filtering**: Uses `highlightFilters` array in `localStorage` to retain active highlights.
- **Negative Filter Constraint**: Aging filter is disabled when “Show Only Negative Balance” is active.
- **DSO Chart**: Tooltip includes claims count, balance, and avg days per month.

## Future Enhancements

- Backend API support to dynamically load data.
- Multi-user sync with server-side filter persistence.
- Role-based UI filtering logic.
- Export to Excel with current filter highlights.

## License

Proprietary. For internal use by authorized users in compliance with organizational RCM processes.
