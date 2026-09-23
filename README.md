# 🚆 Manual Testing For BANGLADESH Railway Web Application

[![QA Status](https://img.shields.io/badge/QA%20Status-Passed%20(99.56%25)-success?style=for-the-badge&logo=checkmarx)](https://eticket.railway.gov.bd)
[![Total Test Cases](https://img.shields.io/badge/Total%20Test%20Cases-225-blue?style=for-the-badge&logo=testrail)](#-test-execution-summary--metrics)
[![Execution Rate](https://img.shields.io/badge/Execution%20Rate-100%25-informational?style=for-the-badge)](#-test-execution-summary--metrics)
[![Target Platform](https://img.shields.io/badge/Target-eticket.railway.gov.bd-orange?style=for-the-badge&logo=googlechrome)](https://eticket.railway.gov.bd)
[![Tested By](https://img.shields.io/badge/SQA%20Engineer-Tanzim%20Rahman-darkgreen?style=for-the-badge&logo=github)](https://github.com/TanzimSQA)

A comprehensive, industry-standard Software Quality Assurance (SQA) test documentation suite for the **Bangladesh Railway E-Ticketing System** ([eticket.railway.gov.bd](https://eticket.railway.gov.bd)).

This repository contains full lifecycle testing artifacts including an **IEEE 829 Test Plan**, **System Mind Map**, **225 Manual Test Cases**, **Defect Card Report with Severity/Priority Triage**, **Traceability & Test Matrices**, and **Executive Test Metrics**.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Target Application](#-target-application)
- [System Mind Map](#-system-mind-map)
- [Scope of Testing](#-scope-of-testing)
- [Test Environment & Tools](#-test-environment--tools)
- [Test Execution Summary & Metrics](#-test-execution-summary--metrics)
- [Module Breakdown](#-module-breakdown)
- [Defect Tracking & Bug Report](#-defect-tracking--bug-report)
- [Test Deliverables Structure](#-test-deliverables-structure)
- [How to Review This Project](#-how-to-review-this-project)
- [Author & Acknowledgements](#-author--acknowledgements)

---

## 📖 Project Overview

The Bangladesh Railway e-Ticketing platform handles millions of passenger searches, reservations, seat selections, and online ticketing transactions across the country. Ensuring platform stability, security, accurate schedule lookup, responsive UI, and seamless form validations is critical for passenger experience.

This testing project delivers an end-to-end quality audit of the live web portal using **Black-Box Testing methodologies**, covering functional workflows, input validation, edge cases, error handling, security checks, and cross-browser responsiveness.

---

## 🌐 Target Application

- **Application Name**: Bangladesh Railway E-Ticketing Portal
- **Live URL**: [https://eticket.railway.gov.bd](https://eticket.railway.gov.bd)
- **Application Type**: High-Traffic Public Transportation E-Commerce Web Application
- **Core Workflows**: Train Search & Availability, Class & Berth Selection, User Registration & NID Verification, User Login & Password Recovery, Contact & Refund Support Information.

---

## 🗺️ System Mind Map

A structured visual breakdown of the application architecture, user flows, train schedule mappings, and verification checkpoints was designed prior to test case authoring:

<p align="center">
  <img src="assets/mindmap.jpeg" alt="Bangladesh Railway QA Mind Map" width="950" />
</p>

### Architecture at a Glance
- **Home / Booking Engine**: Station inputs (`From` / `To`), Date Picker, Class Selection (`AC_B`, `AC_S`, `SNIGDHA`, `F_BERTH`, `F_SEAT`, `F_CHAIR`, `S_CHAIR`, `SHOVAN`, `SHULOV`, `AC_CHAIR`), and Train Search.
- **Login Module**: Mobile Number, Password, Forgot Password (`Phone Number`, `reCAPTCHA`), Help Links.
- **Registration Module**: Two-step flow consisting of Identity Verification (`Full Name`, `Mobile`, `NID`, `DOB`, `reCAPTCHA`) followed by Registration Data Submission (`Email`, `Identification Type`, `Post Code`, `Password`, `ID/Birth Certificate Photo Upload`).
- **Train Information & Schedule**: Detailed route, stoppage, and schedule lookups for over 40 intercity and commuter train services nationwide.
- **Contact Us & Support**: Support hotlines and payment gateway helplines (`bKash`, `Nagad`, `Rocket/DBBL Nexus`, `Upay`, `Visa/Mastercard`, Email Support).

---

## 🎯 Scope of Testing

### In-Scope
- ✅ **Functional Testing**: End-to-end journey search, train route listings, seat class availability, and navigation.
- ✅ **Form & Field Validation**: Name, Bangladeshi 11-digit mobile number, NID formats, email pattern, date of birth constraints.
- ✅ **Boundary Value Analysis (BVA)**: Character limits, boundary date selections, minimum/maximum password length.
- ✅ **Negative Testing**: Invalid inputs, mismatched passwords, unselected station edge cases, same source-destination selection.
- ✅ **Security Testing**: Empty form bypass attempts, reCAPTCHA enforcement, password masking.
- ✅ **UI / UX & Layout Testing**: Grid alignment, placeholder texts, logo & branding display, mobile viewport adaptability.
- ✅ **Cross-Browser Compatibility**: Validated across Chrome, Edge, Firefox, Brave, and Opera Mini.

### Out-of-Scope
- ❌ Internal railway administrative dashboards and backend operational databases.
- ❌ Direct payment settlement clearing via live third-party commercial bank APIs.

---

## 💻 Test Environment & Tools

| Category | Details |
|---|---|
| **Operating System** | Windows 10 & Windows 11 Desktop PC |
| **Browsers Tested** | Google Chrome, Mozilla Firefox, Microsoft Edge, Brave, Opera Mini |
| **Test Case Management** | Microsoft Excel (Card Style Design & Formatted Traceability Grid) |
| **Mind Mapping Tool** | XMind |
| **Inspection Tools** | Chrome DevTools (Console, Elements, Network, Device Emulation) |
| **Version Control** | Git & GitHub |

---

## 📊 Test Execution Summary & Metrics

All test cases were executed and measured against predefined entry and exit criteria.

### Key Performance Indicators (KPIs)

```
┌───────────────────────────────────────────────────────────────┐
│                    TEST EXECUTION SUMMARY                     │
├──────────────────────────┬──────────┬─────────────────────────┤
│ Metric                   │ Count    │ Percentage              │
├──────────────────────────┼──────────┼─────────────────────────┤
│ Total Test Cases Written │ 225      │ 100.00 %                │
│ Test Cases Executed      │ 225      │ 100.00 %                │
│ Test Cases Not Executed  │   0      │   0.00 %                │
├──────────────────────────┼──────────┼─────────────────────────┤
│ Passed Test Cases        │ 224      │  99.56 %                │
│ Failed Test Cases (Bugs) │   1      │   0.44 %                │
│ Blocked Test Cases       │   0      │   0.00 %                │
└──────────────────────────┴──────────┴─────────────────────────┘
```

> **Execution Rate**: **100%** (225 / 225 executed).  
> **Pass Rate**: **99.56%** (224 / 225 test cases successfully passed).

---

## 📂 Module Breakdown

| Module / Feature Area | Total Test Cases | Primary Testing Focus |
|---|:---:|---|
| **Train Information & Schedule** | 149 | Route availability, train number lookup, stops & timing accuracy |
| **Registration Module** | 20 | Full Name, Password, NID, Date of Birth, Verification button |
| **UI & Layout / Navigation** | 17 | Logo display, navigation bar redirects, responsive cards, placeholders |
| **Mobile Number Input** | 11 | Format validation, digit length, BD prefix rules, boundary checks |
| **Train Search & Station Selection** | 7 | Origin/Destination dropdowns, same-station error, date selection |
| **Refund & Helpline Support** | 5 | Gateway shortcode displays, dial link functionality, layout |
| **Authentication / Login** | 4 | Credential validation, session entry, error prompts |
| **Security & reCAPTCHA** | 4 | Bot prevention, submission blocking without captcha |
| **NID Verification** | 3 | National ID formatting, validation rules, error handling |
| **Form Validation** | 1 | Required fields & submission integrity |
| **Choose Class** | 1 | Coach class selection & berth tier mapping |
| **Total** | **225** | **100% Executed** |

---

## 🐞 Defect Tracking & Bug Report

Active defects are logged and triaged in the standardized bug report:

### Defect Details: BUG_01

| Field | Detail |
|---|---|
| **Bug ID** | `BUG_01` (Related: **TC-070**) |
| **Module** | Registration — Submit Button |
| **Environment** | Production ([https://eticket.railway.gov.bd](https://eticket.railway.gov.bd/register)) |
| **Severity** | **Critical** (Blocker / Critical) |
| **Priority** | **High** |
| **Status** | **Open** |
| **Assigned To** | Dev Team Lead |
| **Responsible QA** | Tanzim Rahman |
| **Reported Date** | 26/08/2026 |

#### Issue Description
Form submits successfully and redirects to the next page when all required fields are left blank.

#### Steps to Reproduce
1. Open Registration page: `https://eticket.railway.gov.bd/register`
2. Leave **Full Name**, **Mobile Number**, and **NID** fields blank.
3. Leave **reCAPTCHA** unchecked.
4. Click the **'Verify'** button.

#### Expected Result
System displays validation error prompts for all required fields and prevents form submission.

#### Actual Result
Form accepts blank input data, bypasses captcha validation, and redirects to the next page.

---

## 📑 Test Deliverables Structure

The testing deliverables are available in the updated repository workbook:  
[`Manual Testing For BANGLADESH Railway Web Application.xlsx`](./Manual%20Testing%20For%20BANGLADESH%20Railway%20Web%20Application.xlsx)

```
Manual Testing For BANGLADESH Railway Web Application.xlsx
├── 📄 Sheet 1: Test Plan          # IEEE 829 Compliant Test Strategy & Scope
├── 📄 Sheet 2: Mind Map           # Visual System Architecture & Flow Diagram
├── 📄 Sheet 3: Test Cases         # 225 Formatted Card-Style Test Cases
├── 📄 Sheet 4: Bug Report         # Standardized Defect Card Logs & Reproduction Steps
├── 📄 Sheet 5: Test Matrix        # Execution %, Defect Metrics & Quality KPIs
├── 📄 Sheet 6: Test Case Report   # Executive Sign-Off & Status Overview (224 Pass / 1 Fail)
└── 📄 Sheet 7: Test Metrics       # High-Level Execution Summary (99.56% Pass Rate)
```

---

## 🔍 How to Review This Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/TanzimSQA/Manual-Testing-For-BANGLADESH-Railway-Web-Application.git
   cd Manual-Testing-For-BANGLADESH-Railway-Web-Application
   ```

2. **Inspect the Test Artifacts**:
   - Open [`Manual Testing For BANGLADESH Railway Web Application.xlsx`](./Manual%20Testing%20For%20BANGLADESH%20Railway%20Web%20Application.xlsx) in Microsoft Excel, WPS Office, or Google Sheets.
   - Navigate through the sheet tabs:
     - Check **Test Plan** for governance, entry/exit criteria, and suspension conditions.
     - Review **Mind Map** for the end-to-end component mapping.
     - Browse **Test Cases** to examine test scenarios, test steps, test data, and actual vs expected results.
     - Inspect **Bug Report** to review active defect details, severity triage, and steps to reproduce.

---

## 👤 Author & Acknowledgements

- **SQA Engineer**: **Tanzim Rahman**  
  - 🌐 GitHub: [@TanzimSQA](https://github.com/TanzimSQA)  
  - 📧 Email: [tanzimsqa@gmail.com](mailto:tanzimsqa@gmail.com)
- **Reviewed By**: **Md Rubel Hossain**  
- **Test Timeline**: August 26, 2026 – August 28, 2026

---

<p align="center">
  <i>Crafted with precision for Quality Assurance & Excellence in Software Testing.</i>
</p>
