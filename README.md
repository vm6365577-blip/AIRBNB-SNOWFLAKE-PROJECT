<p align="center">
  <img src="https://img.shields.io/badge/POWER%20BI-DASHBOARD-yellow?style=for-the-badge&logo=powerbi&logoColor=black" alt="powerbi" />
  <img src="https://img.shields.io/badge/DOMAIN-AIRBNB%20ANALYTICS-blue?style=for-the-badge" alt="domain" />
  <img src="https://img.shields.io/badge/STATUS-COMPLETE-brightgreen?style=for-the-badge" alt="status" />
</p>

<h1 align="center">Airbnb Performance Dashboard</h1>
<p align="center">
  An interactive Power BI dashboard analyzing Airbnb revenue, bookings, and pricing across cities, property types, and room types.
</p>

---

## 📊 At a glance

<p align="center">
  <img src="https://img.shields.io/badge/TOTAL%20REVENUE-62.53M-purple?style=for-the-badge" />
  <img src="https://img.shields.io/badge/TOTAL%20BOOKINGS-5K-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/TOTAL%20LISTINGS-500-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/TOTAL%20HOSTS-189-blue?style=for-the-badge" />
</p>

> This dashboard turns raw Airbnb booking data into a two-page interactive report — one page for a high-level performance overview, one for a deep dive into revenue and pricing drivers. Built to answer: *which cities, property types, and room types actually drive revenue?*

---

## 🖼️ Pages

### 1. Airbnb Performance Overview
High-level KPIs plus revenue breakdowns by city, property type, and room type, with global filters for city, property type, room type, and booking status.

<p align="center">
  <img src="docs/performance_overview.jpeg" width="850" alt="Airbnb Performance Overview page" />
</p>

**Key metrics on this page:**

| Metric | Value |
|---|---|
| Total Revenue | 62.53M |
| Total Bookings | 5K |
| Total Listings | 500 |
| Total Hosts | 189 |

**Total Revenue by City (top 5):**
| City | Revenue |
|---|---|
| West Jennifer | 0.49M |
| Lake Jason | 0.43M |
| Josemouth | 0.32M |
| Wellsberg | 0.30M |
| West Robertport | 0.29M |

**Total Revenue by Property Type:**
| Property Type | Revenue |
|---|---|
| House | 21.5M |
| Condo | 21.1M |
| Apartment | 19.9M |

**Total Bookings by Room Type:**
| Room Type | Bookings |
|---|---|
| Private room | 2.5K |
| Entire home | 2.5K |

---

### 2. Revenue & Pricing Analysis
A pricing-focused view with a decomposition tree (Total Revenue → Room Type → Property Type → City) and a property-type revenue split, filterable by room type, property type, and city.

<p align="center">
  <img src="docs/revenue_pricing_analysis.jpeg" width="850" alt="Revenue and Pricing Analysis page" />
</p>

**Key metrics on this page:**

| Metric | Value |
|---|---|
| Total Revenue | 62.53M |
| Average Booking Value | 12.51K |
| Average Price Per Night | 170.32 |
| Total Cleaning Fees | 250.72K |
| Total Service Fees | 150.54K |

**Total Revenue by Property Type (share of total):**
| Property Type | Revenue | Share |
|---|---|---|
| House | 21.49M | 34.36% |
| Condo | 21.14M | 33.8% |
| Apartment | 19.91M | 31.83% |

**Decomposition — Total Revenue (₹6,25,29,322) by Room Type → Property Type:**
| Room Type | Revenue |
|---|---|
| Private room | 3,20,09,608 |
| Entire home | 3,05,19,714 |

| Entire home → Property Type | Revenue |
|---|---|
| Condo | 1,12,79,671 |
| Apartment | 1,05,05,898 |
| House | 87,34,145 |

---

## 🧩 Filters available

Both pages support slicing by:
- **City**
- **Property Type**
- **Room Type**
- **Booking Status**

---

## 🛠️ Tech Stack

- **Power BI Desktop** — report authoring, data modeling, and DAX measures
- **Data model** — Airbnb bookings dataset (city, property type, room type, pricing, fees, host/listing dimensions)
- **Custom visual** — [Calendar Visual by MAQ Software](https://github.com/MAQ-Software-Solutions/CalendarVisual) (v4.3.0.4), used for date-based event/booking views
- **Report theme** — `CY26SU07`, Power BI's standard Fluent-based theme (40-color palette, Segoe UI/DIN typography)

---

## 📂 Repository Structure

```
.
├── AirbnbPerformanceDashboard.pbix   # Power BI report file
├── docs/
│   ├── performance_overview.jpeg     # Page 1 screenshot
│   └── revenue_pricing_analysis.jpeg # Page 2 screenshot
└── README.md
```

<details>
<summary><b>📦 .pbix internal structure (for reference)</b></summary>

A `.pbix` file is a zip archive. This report's package includes:

```
├── DataModel              # Compressed data model (tables, relationships, measures)
├── Layout                 # Visual layout and page definitions
├── DiagramLayout           # Model diagram view layout
├── Metadata                # Report metadata
├── Settings                 # Report-level settings
├── Version                  # Pbix schema version
├── SecurityBindings          # RLS / security bindings
├── LinguisticSchema           # Q&A natural language schema
├── [Content_Types].xml         # OPC package content type declarations
└── Resources/
    ├── CY26SU07.json                                 # Applied report theme
    ├── AccessibleTidal.json                           # Alternate/accessible theme option
    └── CalendarVisual.../
        ├── package.json                                # Custom visual manifest
        └── ...pbiviz.json                                # Custom visual resource definition
```

</details>

---

## 🚀 How to Use

1. Open `AirbnbPerformanceDashboard.pbix` in **Power BI Desktop**.
2. Use the filter panes (City, Property Type, Room Type, Booking Status) to slice the data.
3. On the Revenue & Pricing Analysis page, click into the decomposition tree to drill from Total Revenue down through Room Type → Property Type → City.

---

## 📄 License

MIT
