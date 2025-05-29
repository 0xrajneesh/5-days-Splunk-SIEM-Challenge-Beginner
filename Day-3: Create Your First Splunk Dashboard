# Day-3 Project: Create Your First Splunk Dashboard

## 🎯 Objective

Build a Splunk Dashboard using uploaded SSH logs to display:

- ✅ Source IP Addresses  
- ✅ Destination IP Addresses  
- ✅ Number of Failed SSH Logins  
- ✅ Number of Successful SSH Logins  

---

## 🧰Requirements

- Splunk installed and accessible  
- Dataset: `ssh_logs.txt`  
- Index name: `ssh_index`  
- Basic SPL knowledge  
- Familiarity with Splunk Dashboard UI  

---

## 🛠️Step-by-Step Guide

### 🔹Step 1: Upload the Dataset

1. Go to `Settings → Add Data → Upload`
2. Upload file: `ssh_logs.txt`
3. Set source type as `json`
4. Create index named `ssh_index`
5. Finish upload and go to `Search & Reporting`

---

### 📊Step 2: Panel 1 – Source IP Count (Bar Chart)

**SPL Query:**
```spl
index=ssh_index
| stats count by id.orig_h
| rename id.orig_h as "Source IP"
| sort - count
- Save As: Dashboard Panel
- Title: Top Source IPs
- Visualization: Bar Chart

### 📊Step 3: Panel 2 – Destination IP Count (Bar Chart)
SPL Query:
```
index=ssh_index
| stats count by id.resp_h
| rename id.resp_h as "Destination IP"
| sort - count
```
- Save As: Dashboard Panel
- Title: Top Destination IPs
- Visualization: Bar Chart

### 📈Step 4: Panel 3 – Failed SSH Login Count (Single Value)
SPL Query:

```
index=ssh_index auth_success=false
| stats count as "Failed SSH Logins"
```
- Save As: Dashboard Panel
- Title: Total Failed SSH Logins
- Visualization: Single Value

### 📈Step 5: Panel 4 – Successful SSH Login Count (Single Value)
SPL Query:

spl
Copy
Edit
index=ssh_index auth_success=true
| stats count as "Successful SSH Logins"
Save As: Dashboard Panel

Title: Total Successful SSH Logins

Visualization: Single Value

📋 Step 6: Panel 5 – Source vs Destination IP Table
SPL Query:
```
index=ssh_index
| stats count by id.orig_h, id.resp_h
| rename id.orig_h as "Source IP", id.resp_h as "Destination IP", count as "Total Connections"
| sort - "Total Connections"
```
- Save As: Dashboard Panel
- Title: Source to Destination IP Pairs
- Visualization: Table

## 📌Conclusion
You've now created a 5-panel Splunk dashboard that provides visibility into SSH activity patterns, including IP relationships and login statistics. This is a foundational skill for security analysis.

## 📸Submission
Upload a screenshot of your final dashboard showing all 5 panels:
- Top Source IPs
- Top Destination IPs
- Total Failed SSH Logins
- Total Successful SSH Logins
- Source to Destination IP Mapping

