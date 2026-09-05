# Changelog

All notable changes to Todoist Rewind are documented in this file.

## [Unreleased]

### Added

- Period-aware Insights for day, week, month, year, and custom ranges.
- Comparisons with the immediately preceding equivalent period across headline metrics and charts.
- Label support throughout the app: task metadata, filters, grouping, and Insights.
- A real custom date-range picker with validation and equivalent-period navigation.
- Grouping by day, week, month, project, or label when relevant to the selected period.
- Project search in the filter menu and a visible active-filter counter.
- Theme support that follows the system preference and remembers the user's choice locally.
- Keyboard shortcuts for period navigation, time-frame changes, filters, grouping, and Insights.
- A deterministic demo dataset for repeatable testing and product discovery.
- Responsive, full-screen Insights on small screens.

### Performance

- Replaced the Chart.js-based report rendering with lightweight inline SVG and CSS charts, removing a runtime dependency and canvas redraw work.
- Reduced dashboard rendering to the selected period and active filters rather than maintaining separate view-specific report code paths.

### Changed

- Updated the README product overview to reflect flexible periods, comparative Insights, labels, filters, grouping, PNG export, and local-only data handling.
- Replaced the demo preview card with a quiet text action that matches the product’s existing controls.
- Added a compact play marker to the demo action and linked the “Made by julesbertolino” credit directly to alias-digital.fr.
- Added `todoist.julesbertolino.fr` to the Insights footer so it is included in PNG exports.
- Promoted demo mode from a low-visibility text link to a dedicated preview card with supporting copy.
- Reorganized the top Insights metrics into a balanced 3 × 2 desktop grid with clearer labels and comparison placement.
- Expanded the footer with linked julesbertolino and aliasdigital credits plus icon-led actions.
- Rebuilt the dashboard around a compact sticky period bar, a clearer summary rail, and a more readable task log.
- Reworked task rows to show project, labels, and completion time without truncating longer titles to a single line.
- Replaced the generic report with context-specific KPIs and charts for each time frame.
- Calculated daily averages from elapsed days rather than the full length of an in-progress period.
- Calculated yearly monthly averages from elapsed months for the current year.
- Updated task links to the current Todoist URL format.
- Redesigned sign-in copy to make the privacy model and demo route easier to understand.
- Made the interface consistently English, including date and time formatting.

### Fixed

- Preserved Todoist labels returned by the completed-tasks endpoint instead of dropping them during normalization.
- Prevented misleading comparisons when the preceding period has not been loaded yet.
- Made day and streak calculations resilient to daylight-saving time changes.
- Restored functional custom ranges; the design prototype had treated Custom as a weekly view.
- Restored functional PNG export; the design prototype's export button was visual only.
- Prevented horizontal overflow in the dashboard and Insights at mobile widths.
- Added modal focus restoration, keyboard focus containment, Escape handling, and accessible labels for key controls.
- Added retry handling for rate limits and transient Todoist API failures.

### Privacy

- The application remains fully client-side: the Todoist token is stored only in the browser, Todoist data is kept in memory, and no application backend was added.
