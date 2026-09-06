# Changelog

All notable product changes to Todoist Rewind are documented here. Documentation-only commits do not create a product version.

## [Unreleased]

### Documentation

- Added a visual product tour to the README and aligned feature descriptions with the current interface.

## [2.0.0] - 2026-09-05

### Added

- Period-aware Insights for day, week, month, year, and custom ranges.
- Comparisons with the immediately preceding equivalent period across headline metrics and charts.
- Label support throughout the app: task metadata, filters, grouping, and Insights.
- Grouping by day, week, month, project, or label when relevant to the selected period.
- Project search in the filter menu and a visible active-filter counter.
- Theme support that follows the system preference and remembers the user's choice locally.
- Keyboard shortcuts for period navigation, time-frame changes, filters, grouping, and Insights.
- A deterministic demo dataset for repeatable testing and product discovery.
- Responsive, full-screen Insights on small screens.

### Changed

- Rebuilt the dashboard around a compact sticky period bar, a clearer summary rail, and a more readable task log.
- Reworked task rows to show project, labels, and completion time without truncating longer titles to a single line.
- Replaced the generic report with context-specific KPIs and charts for each time frame.
- Replaced Chart.js with lightweight inline SVG and CSS charts, removing a runtime dependency and canvas redraw work.
- Reduced dashboard rendering to the selected period and active filters rather than maintaining separate view-specific report code paths.
- Calculated daily averages from elapsed days rather than the full length of an in-progress period.
- Calculated yearly monthly averages from elapsed months for the current year.
- Updated task links to the current Todoist URL format.
- Redesigned sign-in copy to make the privacy model and demo route easier to understand.
- Made the interface consistently English, including date and time formatting.

### Fixed

- Preserved Todoist labels returned by the completed-tasks endpoint instead of dropping them during normalization.
- Prevented misleading comparisons when the preceding period has not been loaded yet.
- Made day and streak calculations resilient to daylight-saving time changes.
- Restored functional PNG export; the earlier design prototype's export button was visual only.
- Prevented horizontal overflow in the dashboard and Insights at mobile widths.
- Added modal focus restoration, keyboard focus containment, Escape handling, and accessible labels for key controls.
- Added retry handling for rate limits and transient Todoist API failures.

### Privacy

- The application remains fully client-side: the Todoist token is stored only in the browser, Todoist data is kept in memory, and no application backend was added.

## [1.1.0] - 2026-05-26

### Added

- A Custom scope alongside Day, Week, Month, and Year.
- A date-range picker with start and end validation.
- Custom-range navigation that moves by the selected range's own duration.

### Changed

- Reworked the responsive layout for tablet and mobile widths.
- Made the period selector a five-column control on smaller screens.
- Made Insights full-screen on mobile and stacked charts into one column.

### Fixed

- Kept the custom-range picker functional after the responsive redesign.
- Prevented sorting, loading progress, modal controls, and footer content from overflowing on narrow screens.

## [1.0.0] - 2026-03-26

### Added

- Initial release of Todoist Rewind: a browser-only way to review completed Todoist tasks.
- Day, Week, Month, and Year views with previous/next period navigation.
- Filtering by Todoist priority and project.
- Completed-task log with priority or newest-first sorting and direct links back to Todoist.
- Insights with completed-task totals, Focus Score, productive-day and hour signals, activity timeline, weekday breakdown, and project distribution.
- PNG export for the Insights view.
- Demo data for exploring the app without a Todoist API token.

### Privacy

- Todoist API tokens are stored locally in the browser; no application backend or third-party data collection is used.
