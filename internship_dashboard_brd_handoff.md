# Business Requirements Document (BRD) & AI Handoff
**Project Name:** Thailand Internship Open Data Dashboard 2026
**Target Developer:** Antigravity (AI Dashboard Generator)
**Context:** This document serves as the structural and functional requirement for building a single-file interactive HTML dashboard analyzing internship open data in Thailand (1,000+ companies, 20+ job categories).

---

## 🏗️ โครงสร้าง Dashboard และ Functional Requirements

### Tab 1: สถิติอัตราการเปิดรับเด็กฝึกงาน และข้อมูลบริษัท (Internship Demographics)
**เป้าหมาย:** ตอบคำถามว่า "สายงานไหนรับเด็กฝึกงานมากที่สุด สภาพแวดล้อมและผลตอบแทนเป็นอย่างไร"

**KPI Metric Cards (Top Banner):**
1. **Total Companies:** จำนวนบริษัททั้งหมดที่เปิดรับ (Target: 1,000+)
2. **Total Positions:** จำนวนตำแหน่งงานฝึกงานรวมทั้งหมด
3. **Avg. Daily Allowance:** ค่าเฉลี่ยเบี้ยเลี้ยงต่อวัน (บาท/วัน)
4. **Top Demanded Field:** สายงานที่มีสัดส่วนการเปิดรับสูงสุด

**Visual Components:**
*   **Horizontal Bar Chart / Treemap:** แสดงสัดส่วนปริมาณบริษัทและจำนวนตำแหน่งที่รับเด็กฝึกงาน เรียงลำดับจากมากไปน้อย (Top 20+ Categories) เน้น Highlighting สายงานที่รับมากที่สุด
*   **Donut Chart:** แสดงสัดส่วนรูปแบบการทำงาน (On-site vs Hybrid vs Remote)
*   **Choropleth Map / Bar Chart:** แสดงการกระจายตัวของตำแหน่งฝึกงานตามภูมิภาค/จังหวัด (เน้น กทม., ปริมณฑล และจังหวัดหัวเมืองเศรษฐกิจ)
*   **Box Plot / Histogram:** สถิติการกระจายตัวของเบี้ยเลี้ยงฝึกงาน (ค่ามัธยฐาน, ค่าต่ำสุด, ค่าสูงสุด) แยกเปรียบเทียบตามสายงาน
*   **Data Table:** ตารางแสดง Raw Data (รายชื่อบริษัท, สายงาน, ตำแหน่ง, รูปแบบงาน, เบี้ยเลี้ยง) พร้อมระบบ Pagination, Sorting (เรียงคอลัมน์ได้) และ Global Search Bar

---

### Tab 2: ทักษะและความต้องการของตลาดแรงงาน (Skills & Requirements)
**เป้าหมาย:** ตอบคำถามว่า "บริษัทต้องการเด็กฝึกงานที่มี Skill และ Tools แบบไหนในแต่ละสายงาน"

**KPI Metric Cards:**
1. **Top Hard Skill:** ทักษะทางวิชาชีพ/เทคนิคที่ถูกระบุในประกาศมากที่สุด
2. **Top Soft Skill:** ทักษะทางสังคม/การทำงานที่ถูกระบุมากที่สุด
3. **Top Tool / Software:** เครื่องมือหรือโปรแกรมที่ตลาดต้องการสูงที่สุด

**Visual Components:**
*   **Interactive Controls:** Dropdown Menu สำหรับเลือกดูข้อมูลเฉพาะ 1 สายงาน หรือเปรียบเทียบทั้งหมด
*   **Stacked Bar Chart / Grouped Bar Chart:** แสดง 10 อันดับ Hard Skills ยอดนิยม (สามารถ Filter แยกตามสายงานที่เลือกได้)
*   **Radar Chart / Spider Chart:** เปรียบเทียบระดับความสำคัญของ Soft Skills (เช่น Communication, Teamwork, Problem Solving, Adaptability) 
*   **Word Cloud / Interactive Bubble Chart:** เครื่องมือ, ภาษาโปรแกรม และ Software/Tools ที่นายจ้างระบุ (ขนาด Node แปรผันตาม Frequency ของคำนั้นๆ)
*   **Skill Heatmap:** ตาราง Matrix แสดงความสัมพันธ์ระหว่าง 20 สายงาน (แกน Y) กับ Skills/Tools ยอดนิยม (แกน X) สีเข้มแสดงถึงความต้องการสูง

---

### Tab 3: วิเคราะห์ความสอดคล้องและการเปรียบเทียบ (Demand & Skill Analysis)
**เป้าหมาย:** วิเคราะห์ Skill Mismatch, ความกระจุกตัวของตลาดแรงงาน และความคุ้มค่าของผลตอบแทนเทียบกับความคาดหวังทางทักษะ

**KPI Metric Cards:**
1. **Most Competitive Field:** สายงานที่มีการแข่งขัน/ความต้องการทักษะสูงที่สุด (High Demand - High Skill Requirement)
2. **Skill Diversity Index:** ดัชนีความหลากหลายของทักษะโดยรวมในตลาด (สายงานไหนต้องรู้กว้างที่สุด)

**Visual Components:**
*   **Scatter Plot (Demand vs Compensation Matrix):**
    *   **X-Axis:** ปริมาณบริษัทที่เปิดรับ (Demand Volume)
    *   **Y-Axis:** เบี้ยเลี้ยงเฉลี่ย (Average Allowance)
    *   **Bubble Size:** จำนวน Skill เฉลี่ยที่บังคับว่าต้องมี
    *   *Interaction:* มี Tooltip เมื่อ Hover เพื่อดูชื่อสายงานและ Insight สรุป
*   **Sunburst / Treemap Chart:** แสดง Hierarchical Data (สายงานหลัก -> สายงานย่อย -> ทักษะเฉพาะเจาะจงที่ต้องมี) 
*   **Skill Intensity Index (Bar Chart):** เปรียบเทียบ "จำนวนทักษะเฉลี่ยที่บริษัทคาดหวัง" จากเด็กฝึกงานต่อ 1 ตำแหน่ง แยกตามสายงาน 

---

## 🛠️ Handoff Instructions for Antigravity (Developer AI)
**System Prompt / Instructions for AI Developer:**

1. **Architecture Requirement:** Generate a fully functional single-page application (SPA) in a **single `.html` file**. Do NOT split into separate CSS or JS files.
2. **Tabbed Navigation:** Implement a clean tab system to switch seamlessly between Tab 1, Tab 2, and Tab 3 without page reloads.
3. **Tech Stack & CDNs:** 
    *   **HTML5/CSS3** with **Tailwind CSS** (via CDN) for responsive, modern styling. Support Light/Dark mode if possible.
    *   **JavaScript (Vanilla)** for logic and state management.
    *   **Charting Library:** Use `Chart.js`, `D3.js`, `ApexCharts`, or `ECharts` (via CDN) to render complex visuals like Scatter plots, Radar charts, and Heatmaps.
    *   **Icons:** Use `FontAwesome` or `Heroicons` via CDN.
4. **Mock Data Engine:** You MUST generate an embedded JSON mock dataset internally within the JS `<script>` tag. The dataset should realistically reflect the 20 job categories, metrics, and skill data described in the BRD above so the dashboard is fully populated upon rendering.
5. **Interactive Table:** The Data Table in Tab 1 must be built using either Vanilla JS or a library like `Grid.js` or `DataTables` to support sorting, searching, and pagination.
6. **Responsiveness:** Ensure CSS classes allow the dashboard to adapt cleanly to desktop, tablet, and mobile views (e.g., stacking charts on smaller screens).