# 🇹🇭 Thailand Internship Open Data Dashboard 2026

An interactive, responsive single-file web dashboard analyzing open data on internships in Thailand across 1,250+ companies and 20 job categories.

🌐 **Live Demo (GitHub Pages):** [https://kanokwantho.github.io/dasboard_by_666/](https://kanokwantho.github.io/dasboard_by_666/)  
📁 **Repository:** [https://github.com/kanokwantho/dasboard_by_666](https://github.com/kanokwantho/dasboard_by_666)  

---

## 📌 Executive Summary & Project Purpose

The **Thailand Internship Open Data Dashboard 2026** provides deep insights into the Thai student internship market. It answers critical questions for students, educators, academic advisors, and recruiters:
- Which job fields are hiring the most interns?
- What are the real compensation benchmarks (daily and monthly stipends) across industries?
- What hard skills, soft skills, and specialized tools are companies demanding in 2026?
- What are the work arrangements (On-site vs. Hybrid vs. Remote) and geographic distributions?
- Where do skill mismatches, competitive intensity, and high-value compensation opportunities exist?

---

## 🏗️ Architecture & Technical Specifications

This dashboard is built as an ultra-portable, self-contained Single Page Application (SPA):

- **Single-File Architecture**: Delivered as a standalone `index.html` file that runs directly in any modern browser without requiring backend servers, build steps, or bundle tools.
- **Styling & UI**: [Tailwind CSS (via CDN)](https://tailwindcss.com/) with responsive grid layouts, custom typography, dark/light theme support, and polished glassmorphism card components.
- **Icons**: [FontAwesome 6 / Lucide Icons (via CDN)](https://fontawesome.com/) for UI metrics and actionable buttons.
- **Data Visualization**: [Chart.js 4.x](https://www.chartjs.org/) and [ApexCharts / ECharts](https://apexcharts.com/) for responsive charts (Bar, Donut, Radar, Scatter/Bubble, Heatmap).
- **Interactive Grid**: Built-in interactive data table with global search, column sorting, category & format filtering, pagination, **live inline cell editing (ContentEditable)**, and automatic KPI/Chart live recalculation.
- **Export Engine**: Client-side export capabilities for **CSV** and modified **JSON** format.
- **Embedded Mock Engine**: Realistic dataset covering 20 major career paths, 1,250 companies, and 4,000+ internship openings throughout Thailand.

---

## 📊 Dashboard Modules & Core Features

### 📑 Tab 1: Internship Demographics (สถิติอัตราการเปิดรับและข้อมูลบริษัท)
- **Top KPI Metric Cards**:
  - **Total Companies**: 1,250+ participating employers
  - **Total Positions**: 4,000+ active internship openings
  - **Avg. Daily Allowance**: Market average daily stipend (THB/day)
  - **Top Demanded Field**: Leading field with highest opening share
- **Visual Analytics**:
  - **Horizontal Ranked Bar Chart**: Top 20 Job Categories ranked by internship demand volume.
  - **Work Format Donut Chart**: Breakdown of On-site vs. Hybrid vs. Remote arrangements.
  - **Geographic Distribution**: Distribution across Bangkok & Metropolitan, Chiang Mai, Chonburi/EEC, Phuket, Khon Kaen, etc.
  - **Compensation Distribution**: Daily and monthly allowance ranges and distribution by field.
- **Interactive & Editable Data Grid**:
  - Multi-parameter filtering (Search query, Job Category, Work Format, Location).
  - Sortable column headers and smooth pagination.
  - **Inline Cell Editing**: Modify positions, allowance, skills directly in table cells.
  - **Live Recalculation**: Changes immediately update top KPI cards and distribution charts.
  - **Export Options**: Download data as `.csv` or `.json`.

---

### 📑 Tab 2: Skills & Market Requirements (ทักษะและความต้องการของตลาดแรงงาน)
- **Top KPI Metric Cards**:
  - **Top Hard Skill**: Most demanded technical skill across listings.
  - **Top Soft Skill**: Most emphasized social/workplace capability.
  - **Top Tool / Software**: Essential software tools sought by employers.
- **Visual Analytics**:
  - **Interactive Controls**: Filter by single job category or view all aggregated fields.
  - **Top 10 Hard Skills Bar Chart**: Frequency distribution of technical requirements.
  - **Soft Skills Radar Chart**: Multi-axis radar visualizing core workplace traits (Problem Solving, Teamwork, Communication, Adaptability, Work Ethic, Fast Learning).
  - **Interactive Tools & Technology Cloud/Bubbles**: Frequency-weighted visual display of popular software, frameworks, and cloud platforms.
  - **Skill Heatmap Matrix**: Comprehensive 2D matrix matching 20 job categories against top tech skills with graduated heat density.

---

### 📑 Tab 3: Demand & Skill Analysis (วิเคราะห์ความสอดคล้องและการเปรียบเทียบ)
- **Top KPI Metric Cards**:
  - **Most Competitive Field**: High Demand × High Skill Requirement ratio.
  - **Skill Diversity Index**: Measurement of cross-functional skill breadth required.
- **Visual Analytics**:
  - **Demand vs. Compensation Scatter/Bubble Matrix**:
    - **X-Axis**: Hiring Volume (Positions / Company Demand)
    - **Y-Axis**: Average Daily Stipend (THB)
    - **Bubble Size**: Skill Intensity (Average number of required skills)
    - **Interactive Tooltip**: Hover details showing category insights, benchmarks, and ratio.
  - **Skill Intensity Index (Bar Chart)**: Average number of mandatory skills per position across categories.
  - **Hierarchical Field Category Breakdown**: Categorization of Technical, Creative, Business, and Operational roles.

---

## 🗄️ Data Structure Schema

The dashboard embeds a standardized JSON dataset structured as follows:

```json
[
  {
    "id": 1,
    "category": "Software Engineering",
    "companies_count": 185,
    "positions": 600,
    "percentage": 15.0,
    "stipend_daily_min": 350,
    "stipend_daily_max": 600,
    "stipend_daily_avg": 475,
    "stipend_daily": "350-600 THB",
    "stipend_monthly": "8,000-15,000 THB",
    "work_format": { "onsite": 15, "hybrid": 60, "remote": 25 },
    "locations": ["Bangkok & Metropolitan", "Chiang Mai"],
    "hard_skills": ["JavaScript/TypeScript", "Python", "React/Vue", "Git", "SQL"],
    "soft_skills": ["Problem Solving", "Critical Thinking", "Teamwork"],
    "tools": ["Git/GitHub", "VS Code", "Docker", "Postman", "Figma"],
    "skill_count": 8,
    "cluster": "Technology"
  }
]
```

---

## 🚀 Getting Started & Usage

### Running Locally
No build tools (Node.js, npm, or Python servers) are strictly required. Simply open the file:
```bash
# Double-click or open index.html in any modern browser
start index.html
```

Or serve via any static HTTP server:
```bash
# Using Python
python -m http.server 8080

# Using Node.js
npx serve .
```

### Keyboard & Interactivity
- **Tab Switching**: Click any tab at the top navigation bar to toggle views seamlessly.
- **Editing Data**: Click on any editable cell in the table on Tab 1, change the numeric value, and blur/press Enter to watch all metrics and charts update live.
- **Theme Toggle**: Switch between Dark and Light mode using the theme button in the header.
- **Exporting**: Click `Export CSV` or `Export JSON` to save the active or modified dataset.

---

## 📂 Project Structure

```
├── README.md                              # Project documentation & specification
├── PROJECT_STATUS.md                      # Step-by-step implementation progress
├── index.html                             # Standalone interactive dashboard SPA
├── gemini-code-1791295539437.md          # Technical task handoff specification
└── internship_dashboard_brd_handoff.md    # Business Requirements Document (BRD)
```

---

## 📜 License
Open data visualization project for educational, academic, and workforce research in Thailand. Released under the MIT License.
