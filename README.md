# STP FKP & Mesh Adoption Dashboard

**Herman Kwong's Organization - Service Adoption Tracking**

## 🌐 Live Dashboard

**https://swaid-sys.github.io/stp-fkp-mesh-dashboard/**

---

## 📊 Overview

Comprehensive dashboard tracking FKP (Falcon Kubernetes Platform) and Service Mesh adoption across 301 services in Herman Kwong's STP organization.

### Key Metrics
- **301 Total Services**
- **164 Services** FKP Completed (54.5%)
- **154 Services** Mesh Enabled (51.2%)
- **7 STP Leaders** tracked

---

## 📋 Features

### FKP Adoption Tab
Services organized by adoption status from Google Sheet Column E:

- **✅ Completed (164 services)** - 100% FKP adoption
- **⚠️ Completed with Clean-Up Required (24 services)** - On FKP but needs cleanup
- **🔄 In Progress: Dev (1 service)** - Currently in development
- **❌ Not Started (3 services)** - Haven't begun FKP adoption
- **🚫 Blocked (2 services)** - Blockers preventing progress
- **📅 Path to Deprecation (71 services)** - Scheduled for deprecation
- **⚪ Can Not / Should Not Containerize (36 services)** - Not suitable for containerization

### Mesh Adoption Tab
- **✅ Mesh Enabled (TRUE)** - Services with Mesh active
- **❌ Mesh Disabled (FALSE)** - Services needing attention
- **⚪ N/A** - Not applicable for Mesh

### Organization Metrics
- Performance breakdown by STP Leader
- Total services, Mesh %, FKP % per leader
- Overall adoption statistics

---

## 📁 Data Source

**Google Sheet**: [FKP & Mesh Onboarding - Commercial](https://docs.google.com/spreadsheets/d/1OAQ8L-XR0zaUwZb_fWFIy_lrykc-Y14lFweSMhLuwoQ/edit?gid=921844013#gid=921844013)

**Filters Applied**:
- Manager: Herman Kwong
- Environment: Gia2h excluded

**Data Columns**:
- Column C: Mesh Commercial Adoption Status from E360
- Column D: FKP adoption status % (numeric)
- Column E: FKP Commercial Adoption Status (used for tables)

---

## 🔄 Updating the Dashboard

### When to Update
Run bi-weekly to sync with Eng360 data updates.

### How to Update

1. **Download fresh data from Eng360 Tableau**:
   - URL: [Eng360 Falcon Adoption Dashboard](https://prod-uswest-c.online.tableau.com/#/site/salesforce/views/Eng360-FalconAdoption/ManagedServicesAdoption-OrgLeaderView?:iid=1)
   - Filter: Manager Name = Herman Kwong
   - Filter: FKP Hyperforce Env = Gia2h de-selected
   - Download: CSV export

2. **Update your Google Sheet** (Columns C & D)

3. **Regenerate dashboard HTML**:
   ```bash
   # Update the data in index.html with fresh Google Sheet data
   # Script available at: /tmp/create_status_based_dashboard.py
   python3 create_status_based_dashboard.py
   ```

4. **Commit and push**:
   ```bash
   cd ~/Downloads/stp-fkp-mesh-dashboard
   git add index.html
   git commit -m "Update dashboard data - $(date +%Y-%m-%d)"
   git push origin main
   ```

5. **Wait 1-2 minutes** for GitHub Pages to update

---

## 🎨 Dashboard Structure

### Header
- Title and organization info
- Generation timestamp

### Organization Metrics
- Summary cards (Total Services, FKP Completed, Mesh Enabled, Path to Deprecation)
- STP Leader performance table

### Tabbed Interface
- **FKP Adoption Tab**: 7 separate tables by status
- **Mesh Adoption Tab**: 3 tables (Enabled/Disabled/N/A)

### Each Table Shows
- Service Name
- STP Leader
- Mesh/FKP Status with color-coded badges
- Adoption status

---

## 🛠️ Technical Details

- **Framework**: Pure HTML/CSS/JavaScript (no dependencies)
- **Data Format**: JSON embedded in HTML
- **Responsive**: Works on desktop, tablet, and mobile
- **Hosting**: GitHub Pages
- **Update Frequency**: Manual (bi-weekly recommended)

---

## 📈 STP Leaders

1. Ajith Jayamohan - 78 services
2. Claudia Santoro - 70 services
3. Satish Raghunath - 68 services
4. Fiaz Hossain - 57 services
5. Wolfgang Krause - 13 services
6. Ramya Subramani - 9 services
7. Garren Bellew - 6 services

---

## 🔗 Related Dashboards

- **Path to Deprecation Dashboard**: https://swaid-sys.github.io/stp-deprecation-dashboard/path_to_deprecation_dashboard.html
- **Service Deprecation Dashboard**: https://swaid-sys.github.io/stp-deprecation-dashboard/

---

## 📞 Contact

For questions or updates, contact Herman Kwong's STP organization.

---

*Last Updated: June 4, 2026*
*Dashboard URL: https://swaid-sys.github.io/stp-fkp-mesh-dashboard/*
