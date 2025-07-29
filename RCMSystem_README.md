# RCM System HTML Dashboard

## Overview

This is an advanced Revenue Cycle Management (RCM) dashboard designed for use with **FileMaker** integration. It supports real-time filtering, sorting, masking of AR values, queue management, chart visualizations, and bulk actions across multiple RCM modules such as Claims, Billed AR, Unbilled AR, Validation, and more.

## Features

- 📊 Dynamic AR Dashboard with multiple charts
- 🗂 Sidebar navigation with module switching
- 🧮 AR masking/unmasking toggle
- 🔍 Advanced filtering: date ranges, payor, status, assigned users, aging buckets
- 📥 CSV export
- 🧑‍💼 Batch process & record selection
- 🧰 Column visibility toggle
- 🔎 Right panel queue display with locking and FileMaker script triggers
- 🔒 Persisted settings and filters using `localStorage`
- 📱 Responsive UI with zoom support
- 📅 Flatpickr-integrated date filtering

## Modules

- Dashboard
- Authorization
- Validation
- Claims
- Unbilled AR
- Billed AR
- Drop AR
- Correspondence
- Remittance
- Deposits
- Queue Manager
- Settings

## Technologies Used

- HTML, CSS, JavaScript
- Chart.js for chart visualizations
- Feather Icons for iconography
- Flatpickr for enhanced date pickers
- FileMaker script integration (via `FileMaker.PerformScript`)

## Setup Instructions

1. **Deployment**: Host the HTML file on a web server that supports JavaScript or load directly into FileMaker Web Viewer.
2. **FileMaker Integration**:
   - Ensure `FileMaker.PerformScript()` functions are mapped to valid FileMaker scripts.
   - Example: `FileMaker.PerformScript('OnClickRCMMenu', 'Dashboard')`
3. **Data Source**:
   - `tableData` is hardcoded in the file and can be updated to connect dynamically via JSON or FileMaker scripting.
4. **Persistence**:
   - Settings, filters, and selected records persist in `localStorage` per user.
   - Can be cleared via "Reset Filters".

## Customization Guide

- **Add a New Module**:
  - Add a `<div class="menu-item">` block in the sidebar.
  - Include a new entry in the `tableData` JavaScript object.
- **Modify Dashboard Charts**:
  - Edit `renderDashboardCharts()` (not shown but implied) and modify `dashboardChart1`, `dashboardChart2`, etc.
- **Change Field Visibility**:
  - Adjust the `visibleColumns` array inside the `loadTable()` function per module.
- **Security/Privacy Enhancements**:
  - Masked AR values by default (toggle via eye icons).
  - HIPAA compliance warning can be added to the About section if needed.

## Shortcuts and Tips

- `Zoom +` / `Zoom -` controls available for main view scaling
- `Export CSV` downloads the currently visible table view
- `Select All`, `Batch Process`, and `Save Selected` manage filtered records efficiently
- Sidebar auto-collapses on user setting

## Known Limitations

- Data is currently static and embedded.
- Does not include real-time server integration or backend validation.
- Requires manual update for `tableData` content if used outside FileMaker.

## License

Private use only. For proprietary use within ANX RCM systems.
