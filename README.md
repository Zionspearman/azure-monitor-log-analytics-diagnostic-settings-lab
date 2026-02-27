# Azure Monitor Lab: Log Analytics + Diagnostic Settings + Alerts

This repository supports my walkthrough video on setting up Azure Monitor using a Log Analytics workspace, Diagnostic settings, and creating both Metric and Log (KQL) alerts with an Action Group.  
📺 https://youtu.be/MkparcC6pbs
---

## 🔍 Lab Overview

In this lab, you’ll learn how to:
- Create a Log Analytics workspace
- Send platform logs using Diagnostic settings
- Verify logs in Log Analytics using KQL
- Create an Action Group for notifications
- Create a Metric alert (threshold-based)
- Create a Log alert (KQL/query-based)

These tasks are fundamental for AZ-104 monitoring and real-world alerting.

---

## 🛠️ Key Tasks

### ✅ Task 1: Create Log Analytics Workspace
- Create or use a resource group (example: `rg-monitor-lab`)
- Create a Log Analytics workspace named `law-az104-lab`
- Pick one region and stay consistent

### ✅ Task 2: Configure Diagnostic Settings
- Choose a resource (VM, Storage, or App Service)
- Open the resource → Diagnostic settings → Add diagnostic setting
- Name it `send-to-law`
- Select Logs categories (and Metrics if desired)
- Send to Log Analytics workspace: `law-az104-lab`
- Save

### ✅ Task 3: Verify Logs (KQL)
- Open the workspace → Logs
- Run a built-in query, or (VM example):
  - `Heartbeat | take 10`
- Confirm results appear (wait a few minutes if needed)

### ✅ Task 4: Create an Action Group
- Azure Monitor → Alerts → Manage actions
- Create action group: `ag-az104-lab` (short name: `aglab`)
- Add an email notification (your email)

### ✅ Task 5: Create a Metric Alert
- Azure Monitor → Alerts → Create alert rule
- Scope: your resource
- Condition example: VM Percentage CPU (threshold like > 80)
- Attach Action Group: `ag-az104-lab`
- Create alert rule (example name: `alert-metric-cpu`)

### ✅ Task 6: Create a Log Alert (KQL Alert)
- Azure Monitor → Alerts → Create alert rule
- Scope: Log Analytics workspace
- Condition: Log search / Logs
- Example query:
  - `Heartbeat | summarize Count=count()`
- Trigger when results > 0
- Attach Action Group: `ag-az104-lab`
- Create alert rule (example name: `alert-log-kql`)

---

## 📁 Files 
- `lab-guide.md`: detailed steps
- `screenshots/`: portal screenshots
- `notes.md`: quick AZ-104 takeaways (Metrics vs Logs, alert types, action groups)

---

## 🔗 Learn More
- [Azure Monitor Overview](https://learn.microsoft.com/azure/azure-monitor/overview)
- [Log Analytics Workspace Overview](https://learn.microsoft.com/azure/azure-monitor/logs/log-analytics-workspace-overview)
- [Diagnostic Settings](https://learn.microsoft.com/azure/azure-monitor/essentials/diagnostic-settings)
- [Metric Alerts](https://learn.microsoft.com/azure/azure-monitor/alerts/alerts-metric)
- [Log Alerts](https://learn.microsoft.com/azure/azure-monitor/alerts/alerts-log)
- [Action Groups](https://learn.microsoft.com/azure/azure-monitor/alerts/action-groups)

---

## 🧵 Tags
`#Azure` `#AzureMonitor` `#LogAnalytics` `#KQL` `#Alerts` `#ActionGroups` `#AZ104` `#AzureLabs`

---

**Created by:** Zion Spearman  
Use this repo to follow along with the video or build your own monitoring + alerting practice lab.
