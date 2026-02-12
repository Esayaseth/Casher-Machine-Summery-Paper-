# Ethiopian Tax Calendar & Filing API

## Overview
In Ethiopia, businesses operate on a dual-calendar system. While daily operations (like hotel bookings and sales) often use the Gregorian Calendar (GC), government tax reporting must follow the Ethiopian Calendar (EC). 

This API solves the "Date Mapping" problem by automatically calculating the correct **Sales Period** for any given **Filing Deadline**.

## Features
- **Automatic Period Mapping:** Identifies the correct month of sales (e.g., Meskerem) based on the current filing date (e.g., Tikimt).
- **Fiscal Year Awareness:** Handles the complex December-to-January year wrap in the Gregorian calendar.
- **Database Ready:** Includes a PostgreSQL integration to automatically sum total sales for the calculated period.
- **MoR Compliance:** Follows the strict 30-day filing window required by the Ethiopian Ministry of Revenues.

## How it Works
The system uses a logic-based ruleset to map the 12 Ethiopian months. For example:
- **Reporting in February (GC):** The API automatically looks back to sales made between **Jan 9 and Feb 7** (representing the Ethiopian month of **Tir**).

## Tech Stack
- **Node.js & Express:** For the API framework.
- **Day.js:** For precise date manipulation and year-wrapping.
- **PostgreSQL:** For transaction data aggregation.

## Setup
1. Clone the repo.
2. Run `npm install`.
3. Set your `DATABASE_URL` in your environment variables.
4. Run `node index.js`.

## Future Enhancements
- [ ] Add Alarming the user before deadline 
- [ ] Integration with Virtual Fiscal (V-Fiscal) software.
- [ ] Automated email reminders for the 30th-day deadline.

