# 📘 RCM System Settings – README

## Overview

The **Settings** panel in the RCM System provides administrators with tools to configure core features including access control, audit logs, insurance parameters, queue workflows, documentation links, and user support. It is designed with usability and compliance in mind, particularly aligned with HIPAA and internal privacy policies.

---

## 🔐 Access Control

**Purpose:**  
Configure user roles and define permissions for system access.

**FileMaker Script Triggered:**  
`OpenAccessControl`

**Typical Use Cases:**
- Grant or revoke access to specific modules.
- Define role-based permissions for RCM staff.

---

## 🧾 System Logs

**Purpose:**  
Review system-wide logs for auditing and compliance tracking.

**FileMaker Script Triggered:**  
`ViewAuditLogs`

**Typical Use Cases:**
- Investigate user activity.
- Track data changes for audits.

---

## 🏥 Insurance Settings

**Purpose:**  
Set up and manage insurance provider information.

**FileMaker Script Triggered:**  
`OpenInsuranceSettings`

**Typical Use Cases:**
- Add new insurance payors.
- Update billing rules.

---

## 🗂 Queue Manager Settings

**Purpose:**  
Configure workflow statuses and set claim processing deadlines.

**FileMaker Script Triggers:**
- `OpenQueueStatusSettings` – Edit Queue Status options.
- `OpenDueDateSettings` – Adjust due date calculation logic.

---

## 📄 Read Me Files

**Purpose:**  
Quick access to documentation for major components.

**FileMaker Script Triggers:**
- `ReadMeDashboard` – Opens dashboard documentation.
- `ReadMeRCM` – Opens RCM core documentation.
- `ReadMeQueueManager` – Opens queue manager documentation.

---

## 📬 Contact Us

**Purpose:**  
Connect with IT Support for assistance.

**FileMaker Script Triggered:**  
`OpenContactUs`

---

## 🔗 Resource Links

**Purpose:**  
Dynamically create and manage a list of custom links.

**Features:**
- Add new links with title and URL.
- Edit or delete existing links.
- Stored via browser's localStorage for quick client-side access.

---

## ⚖️ Legal & Confidentiality Notice

> This system is for authorized users only. All contents are protected under HIPAA and internal NDAs. Unauthorized use is prohibited and may result in disciplinary or legal action.

---

## 🛠 Technical Notes

- Uses **Feather Icons**, **jQuery**, and **Select2** libraries.
- Responsive right panel toggles via JavaScript.
- CRUD operations for resource links handled entirely on the front end using `localStorage`.

---

## 📅 Version

**ANX RCM System v1.0**  
© 2025
