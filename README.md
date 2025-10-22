# SEC Company Concept Viewer

This is a single-file responsive HTML application built with Tailwind CSS that fetches and displays the maximum and minimum outstanding common stock shares for a given company, based on SEC XBRL data.

## Features

*   Displays company name, maximum shares outstanding, and minimum shares outstanding, along with their respective fiscal years (for `fy > 2020`).
*   Initial data for **AES Corporation (CIK 0000874761)**.
*   Dynamic CIK loading: Append `?CIK=<10-digit-CIK>` to the URL to fetch data for a different company without reloading the page.
    *   Example: `index.html?CIK=0001018724` (Apple Inc.)

## How to Run

1.  Save the `index.html` file to your local machine.
2.  Open `index.html` in a web browser.

The application will automatically fetch the data for AES Corporation. To view data for a different company, modify the URL in your browser's address bar.

## Technology Stack

*   **HTML5**: Structure of the web page.
*   **Tailwind CSS**: For responsive and modern styling.
*   **JavaScript (ES6+)**: For fetching data from the SEC API, processing it, and dynamically updating the UI.

## Data Source

Data is fetched from the SEC EDGAR API: `https://data.sec.gov/api/xbrl/companyconcept/CIK<CIK>/dei/EntityCommonStockSharesOutstanding.json`.

**Note on SEC API Access:**
When making requests to the SEC API, it is recommended to set a descriptive `User-Agent` header as per SEC guidance. For client-side JavaScript fetches, directly setting the `User-Agent` is not possible due to browser security restrictions. This application utilizes `https://api.allorigins.win/get?url=` as a client-side proxy to bypass CORS restrictions. In a production environment, a dedicated server-side proxy would be recommended to properly manage `User-Agent` headers and handle rate limiting.

## Attachment `uid.txt`

The content of the `uid.txt` attachment provided with this project is embedded directly within the `index.html` file for completeness, as per the project requirements.

```
This is the content of uid.txt for AES Corporation.
```

---
**Disclaimer**: This application is for demonstration purposes and uses a public proxy service. Please review SEC's API usage policy for any real-world applications.
