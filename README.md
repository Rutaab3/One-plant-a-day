# ONE PLANT A DAY

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![HTML5](https://img.shields.io/badge/Frontend-HTML5%20%7C%20CSS3%20%7C%20JS-blue.svg)](index.html)
[![Framework](https://img.shields.io/badge/UI--Framework-Bootstrap%205.3-purple.svg)](no-wifi/bootstrap/)
[![Data Source](https://img.shields.io/badge/Data-Google%20Sheets%20API%20v4-lightgrey.svg)](https://developers.google.com/sheets/api)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)](#)

An interactive, responsive web portal dedicated to daily botanical discovery, education, and plant conservation awareness. **One Plant a Day** connects plant enthusiasts, researchers, and casual learners to detailed species documentation refreshed daily from a centralized Google Sheets API backend.

---

## TABLE OF CONTENTS

- [Overview](#overview)
- [Key Features](#key-features)
- [Architecture & Data Flow](#architecture--data-flow)
- [Technology Stack](#technology-stack)
- [Application Structure](#application-structure)
- [Detailed Page Documentation](#detailed-page-documentation)
- [Google Sheets API Integration](#google-sheets-api-integration)
- [Interactive Features Overview](#interactive-features-overview)
- [Getting Started & Local Setup](#getting-started--local-setup)
- [Offline Capability](#offline-capability)
- [Browser Compatibility & Performance](#browser-compatibility--performance)
- [Contributing](#contributing)
- [License](#license)

---

## OVERVIEW

**One Plant a Day** is designed around a single educational principle: continuous learning through daily bite-sized discovery. Rather than overwhelming users with huge taxonomical databases, the application calculates the day of the year and highlights a specific plant species every 24 hours. Users can examine botanical taxonomy, geographical origins, key characteristics, fun facts, medicinal and practical uses, and environmental habitats.

---

## KEY FEATURES

- **Dynamic Daily Rotation**: Calculates the day-of-year offset to automatically present a distinct plant every 24 hours.
- **Asynchronous Live Data Sync**: Pulls real-time botanical records directly from a Google Sheets spreadsheet serving as an accessible headless CMS.
- **Carousel & Dynamic Widgets**: Interactive rotation of fun facts and practical plant uses every 10 seconds on the landing page.
- **Interactive Calendar Archives**: Browse past and upcoming plant schedules through an interactive calendar interface.
- **AI-Powered Chat Assistant**: Integrated Chatling AI assistant (`chtl-script`) providing real-time botanical Q&A for visitors.
- **Zero-Dependency Local Fallback Support**: Bundled vendor assets inside the `no-wifi/` directory ensuring layout and styling integrity in offline environments.
- **Modern Responsive Design**: Mobile-first architecture built with Bootstrap 5 grids, custom CSS variables, Animate On Scroll (AOS), and GSAP animations.
- **No Registration & Zero Trackers**: Unrestricted access with no mandatory user login, paywalls, or privacy-invasive advertising.

---

## ARCHITECTURE & DATA FLOW

```
+-----------------------------------------------------------------------+
|                         Google Sheets Backend                         |
|                   (Spreadsheet ID: 1Nw784Uoe9QoCCA0...)                |
+-----------------------------------------------------------------------+
                                    |
                                    | REST API (fetch)
                                    v
+-----------------------------------------------------------------------+
|                          Web Application Client                       |
|                                                                       |
|  +-----------------+  +------------------+  +----------------------+  |
|  |   index.html    |  |    today.html    |  |    calendar.html     |  |
|  | (Facts Carousel)|  | (Featured Plant) |  | (Monthly Navigation) |  |
|  +-----------------+  +------------------+  +----------------------+  |
|          |                     |                       |              |
|          +---------------------+-----------------------+              |
|                                |                                      |
|                                v                                      |
|  +-----------------------------------------------------------------+  |
|  |                 Rendering & UI Frameworks                       |  |
|  |   - Bootstrap 5 Grid / Components                               |  |
|  |   - AOS (Animate On Scroll) Scroll Interactions                  |  |
|  |   - GSAP (GreenSock Animation Platform) Hero Effects            |  |
|  |   - FontAwesome Vector Icons                                    |  |
|  |   - Chatling AI Interactive Assistant Embedded Widget           |  |
|  +-----------------------------------------------------------------+  |
+-----------------------------------------------------------------------+
```

---

## TECHNOLOGY STACK

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend Markup** | HTML5 | Semantic page structure and accessibility markup |
| **Styling & Layout** | CSS3, Bootstrap 5.3 | Responsive layouts, grid systems, custom root color schemes |
| **Animations** | GSAP 3.x, AOS 2.3 | Entry animations, fluid transitions, scroll triggers |
| **Icons** | FontAwesome 6 (SVG/CSS) | UI vector icons across navigation, headers, and metadata cards |
| **Data Source** | Google Sheets REST API v4 | Headless CMS for storing plant attributes and schedule data |
| **AI Integration** | Chatling AI Embed | Real-time automated botanical inquiry assistant |
| **Offline Vendors** | Local Vendor Assets (`no-wifi/`) | Localized Bootstrap, AOS, GSAP, and FontAwesome fallbacks |

---

## APPLICATION STRUCTURE

```
.
├── index.html          # Landing page featuring hero banner, facts carousel, stats, categories
├── today.html          # Dynamic plant of the day highlight page driven by calendar date
├── calendar.html       # Visual calendar grid to inspect plant schedule by date
├── about.html          # Mission statement, project philosophy, and platform objectives
├── faq.html            # Frequently asked questions accordion and help desk
├── Sheet1.html         # Data sheet export view / tabular presentation
├── css/                # Stylesheet directory
│   ├── base.css        # Core reset, typography, variable definitions, navigation, footer
│   ├── index.css       # Landing page specific Hero, Carousel, and Card layouts
│   ├── today.css       # Plant of the day detail layout and metadata styles
│   ├── calendar.css    # Interactive calendar grid formatting
│   ├── about.css      # Team and mission layout styling
│   └── faq.css         # Collapsible FAQ item styling
├── images/             # Static image assets, icons, and logos
│   └── favicon.ico     # Site favicon mark
├── plant/              # Plant media assets and localized media cache
└── no-wifi/            # Bundled offline libraries (Bootstrap, FontAwesome, AOS, GSAP)
```

---

## DETAILED PAGE DOCUMENTATION

<details>
<summary><strong>1. Landing Page (index.html)</strong> - Click to expand</summary>

<br>

The entry point to the platform. Features an energetic presentation powered by GSAP entrance transitions and AOS scroll triggers.

- **Hero Banner**: GSAP bounce animation on headline text with quick call-to-action buttons targeting today's plant feature.
- **Value Proposition**: 3-card breakdown illustrating knowledge expansion, nature connection, and personal wellbeing.
- **Dual Live Carousels**: Asynchronous side-by-side carousels fetching Google Sheets data every 10 seconds to alternate between "Fun Facts" and "Plant Uses".
- **Impact Metrics**: Stat counter grid displaying plant count, enthusiast reach, country distribution, and ad-free policy assurance.
- **Category Grid**: Visual cards representing Flowering Plants, Succulents & Cacti, Medicinal Plants, and Global Trees.
</details>

<details>
<summary><strong>2. Today's Plant (today.html)</strong> - Click to expand</summary>

<br>

Calculates current day-of-year offset (`dayOfYear % plantCount`) to select and render the active species.

- **Header Profile**: Displays image hero, botanical name (Latin nomenclature), common name, and publishing date.
- **Information Sections**: Formatted cards highlighting historical significance, natural habitat, geographical region, and taxonomical category.
- **Facts & Uses Bulletins**: Key points structured in icon-backed list displays for quick scanning.
- **Interactive Navigation Controls**: Allows stepping forward or backward through plant indexes to inspect past/future listings.
</details>

<details>
<summary><strong>3. Calendar View (calendar.html)</strong> - Click to expand</summary>

<br>

Visual archive for navigating plant entries by date.

- **Date Mapping**: Aligns dates with sheet entry indexes to allow quick access to historical plant features.
- **Interactive Selection**: Clickable date tiles that trigger full detail modals or redirects to selected plant records.
</details>

<details>
<summary><strong>4. About Us (about.html)</strong> - Click to expand</summary>

<br>

Provides context regarding the mission of **One Plant a Day**.

- **Mission Framework**: Details the philosophy of accessible, ad-free educational content.
- **Platform Architecture**: Highlights the serverless, privacy-preserving design model.
</details>

<details>
<summary><strong>5. FAQ (faq.html)</strong> - Click to expand</summary>

<br>

Collapsible accordion interface addressing common visitor questions regarding data sources, accuracy, local asset storage, and contribution pathways.
</details>

---

## GOOGLE SHEETS API INTEGRATION

The project uses Google Sheets API v4 as a lightweight backend. The client queries the public JSON endpoint without requiring a dedicated server process.

### Endpoint Structure

```
https://sheets.googleapis.com/v4/spreadsheets/{SHEET_ID}/values/{SHEET_NAME}?key={API_KEY}
```

### Data Schema Mapping

| Field Name | Type | Description |
| :--- | :--- | :--- |
| `plant_name` | String | Common English name of the plant |
| `botanical_name` | String | Binomial Latin classification |
| `date` | String | Scheduled publication date |
| `description` | String | Comprehensive species summary |
| `image_url` | String | Public image URL |
| `region` | String | Native continent / geographical region |
| `habitat` | String | Natural ecosystem (e.g., Rainforest, Arid desert) |
| `category` | String | Grouping (e.g., Angiosperm, Succulent) |
| `history` | String | Historical / cultural significance |
| `fact_1`, `fact_2`, `fact_3` | String | Curated interesting facts |
| `use_1`, `use_2`, `use_3` | String | Practical, medicinal, or ecological uses |

### Sample Fetch Implementation

```javascript
async function fetchPlantData() {
  const API_KEY = "YOUR_API_KEY";
  const SHEET_ID = "YOUR_SHEET_ID";
  const SHEET_NAME = "plants";
  const url = `https://sheets.googleapis.com/v4/spreadsheets/${SHEET_ID}/values/${SHEET_NAME}?key=${API_KEY}`;

  try {
    const response = await fetch(url);
    const json = await response.json();
    const rows = json.values;
    const headers = rows[0];

    return rows.slice(1).map(row => {
      const item = {};
      headers.forEach((header, index) => {
        item[header] = row[index] || "";
      });
      return item;
    });
  } catch (error) {
    console.error("Failed to load plant dataset:", error);
  }
}
```

---

## INTERACTIVE FEATURES OVERVIEW

<details>
<summary><strong>Interactive Code Snippets & Utility Actions</strong> - Click to expand</summary>

<br>

### Day of Year Calculation snippet

```javascript
function getTodayPlantIndex(totalPlants) {
  const today = new Date();
  const startOfYear = new Date(today.getFullYear(), 0, 0);
  const diff = today - startOfYear;
  const dayOfYear = Math.floor(diff / (1000 * 60 * 60 * 24));
  return dayOfYear % totalPlants;
}
```

### Image URL Optimization snippet

```javascript
function getOptimizedImageUrl(rawUrl, targetWidth = 600) {
  if (!rawUrl) return "";
  const delimiter = rawUrl.includes("?") ? "&" : "?";
  return `${rawUrl}${delimiter}w=${targetWidth}`;
}
```

</details>

---

## GETTING STARTED & LOCAL SETUP

### Prerequisites

No build tools (Node.js, npm, Webpack) or database installations are strictly required to run or modify the application. Any standard web browser is sufficient.

### Installation & Execution Steps

1. **Clone the repository**:
   ```bash
   git clone https://github.com/rutaabali3/One-Plant-A-Day.git
   cd One-Plant-A-Day
   ```

2. **Launch via Local Web Server** (Recommended for fetch API CORS consistency):

   - **Using Python 3**:
     ```bash
     python3 -m http.server 8000
     ```
     Navigate to `http://localhost:8000` in your web browser.

   - **Using Node.js (`serve` or `http-server`)**:
     ```bash
     npx serve .
     ```

   - **Using VS Code Live Server Extension**:
     Right-click `index.html` and select **Open with Live Server**.

3. **Direct File Viewing**:
   Alternatively, open `index.html` directly in any web browser.

---

## OFFLINE CAPABILITY

The application includes local dependencies bundled in the `no-wifi/` directory to preserve full UI formatting even without internet connectivity:

- **Bootstrap**: `no-wifi/bootstrap/css/bootstrap.min.css` and `no-wifi/bootstrap/js/bootstrap.bundle.min.js`
- **AOS**: `no-wifi/aos/dist/aos.css` and `no-wifi/aos/dist/aos.js`
- **GSAP**: `no-wifi/gsap/dist/gsap.min.js`
- **FontAwesome**: `no-wifi/fontawesome/css/all.css`

*Note: Fetching live API updates requires an active internet connection to communicate with Google Sheets endpoints.*

---

## BROWSER COMPATIBILITY & PERFORMANCE

| Browser | Minimum Version | Status |
| :--- | :--- | :--- |
| **Google Chrome** | v80+ | Fully Supported |
| **Mozilla Firefox** | v75+ | Fully Supported |
| **Apple Safari** | v13+ | Fully Supported |
| **Microsoft Edge** | v80+ | Fully Supported |
| **Mobile Browsers (iOS/Android)** | Current | Fully Supported |

---

## CONTRIBUTING

Contributions, suggestions, issue reports, and feature proposals are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on guidelines and code conventions.

---

## LICENSE

This project is open-source and released under the [MIT License](LICENSE).
