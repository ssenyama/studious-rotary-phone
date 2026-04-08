# Automatic Google Sheet Data Loading

## Overview
This feature implements automatic loading of data from Google Sheets into the application.

### Key Changes:
- **Automatic Data Fetching:** Data can now be fetched completely automatically from Google Sheets, removing the need for manual URL input.
- **Error Handling:** Added error handling to gracefully manage issues that arise during data fetching.
- **Real-Time Updates:** Implemented a 15-second polling interval to enable real-time updates across devices, addressing synchronization issues.

### Benefits:
- Improves user experience by eliminating the need for manual updates.
- Ensures that data is always current and synchronized.