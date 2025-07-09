# SINGLE WINDOW – REQUIREMENTS DOCUMENT

**Version:** 1.0  
**Date:** 2025-07-09  
**Prepared by:** Musa A. Jallow

## 1. Overview

Gambia Business Gateway (GBG) is a centralized digital platform developed to simplify business registration and compliance in The Gambia. It is designed as a one-stop-shop to allow entrepreneurs and business owners to register, apply for legal documentation, and fulfill ongoing compliance obligations online.

## 2. Objectives

- Enable end-to-end online business registration.
- Integrate with key institutions (MOJ, GRA, SSHFC, Local Councils).
- Allow document upload and digital submission.
- Provide a dashboard for tracking compliance.
- Accept digital payments (Wave, Gamswitch).
- Generate automated reminders for filing obligations.

## 3. Key Modules

### 3.1. Business Name Search & Reservation

**Input:** Desired company name.

**Features:**

- Check name availability (Search API via MOJ).
- Reserve name (store in backend with expiry).
- Notify user of expiration (6-month validity).

**Cost:** D500–D700 (payable via Wave/Gamswitch).

---

### 3.2. Online Application Submission

**Form Sections:**

- Company Type (Ltd, NGO, Sole Prop, etc.)
- Shareholders, Directors, Secretary
- Registered Office
- Business Activity

**Document Upload:**

- Memorandum of Association (PDF)
- Articles of Association (PDF)

**Integration:**

- MOJ API for registration submission

**Cost:** D15,000 base fee (share capital-based)

### 3.3. Payment Module

**Integration with:**

- Wave
- Gamswitch

**Allow:**

- Card payments
- Mobile Money
- Bank transfers

**Receipts & Confirmations:**

Issue receipts and confirmations for all payments.

### 3.4. TIN Application

- Integrate with GRA TIN API
- Auto-fill using user registration details
- Status tracking for TIN issuance

### 3.5. Social Security Registration

- Integration with SSHFC System
- Auto-registration into:
  - Federated Pension Scheme
  - Industrial Injuries Scheme
  - Housing Finance Scheme
- Notify user upon completion

### 3.6. Business License Application

- Integration with Area Councils/Municipalities (Kanifing, Banjul, Brikama, etc.)
- Allow upload of supporting documents
- Track approval status

---

### 3.7. Compliance Dashboard

- Track all annual and periodic obligations
- Display upcoming deadlines
- Alert users for:
  - Annual Returns
  - Tax Filings
  - License Renewals
  - Social Security Submissions

## 4. Ongoing Compliance Modules

### 4.1. Annual Returns Filing

- Upload financial statements
- Fill annual return form
- Update directors/shareholders
- Confirm registered office
- Calculate and process fees: D2,000–D5,000

### 4.2. Tax Compliance Integration

- Integration with GRA
  - Submit tax returns (March 31)
  - Upload quarterly payments
  - Monthly PAYE declaration
- Auto reminders for PAYE (15th of each month)

### 4.3. Social Security Contributions & Payroll

- Monthly calculator for payroll contributions
- Auto-generate SSHFC files
- Submit to SSHFC system
- Reminder system for 15th monthly submission

### 4.4. Director/Shareholder Changes

- File change forms
- Upload resolution documents
- Notify MOJ
- Update backend profile

### 4.5. License Renewal Module

- Auto-track expiry dates
- Send notifications
- Allow renewal submission to councils

## 5. Admin Panel Features (Summary)

- View all applications and statuses
- Download documents
- Edit submissions
- Communicate with applicants
- Manage payment records
- Add/remove compliance items

## 6. Technical Stack (Summary)

| Component        | Tech Stack                                 |
|------------------|--------------------------------------------|
| Frontend         | Next.js (15 with App Router)               |
| Styling          | TailwindCSS / ShadCN UI                    |
| Backend          | Node.js API (Next.js API routes or NestJS) |
| Database         | PostgreSQL or MongoDB                      |
| Auth             | Clerk/Auth.js/Supabase Auth                |
| File Uploads     | Cloudinary or AWS S3                       |
| Payments         | Wave & Gamswitch SDKs                      |
| Integration APIs | MOJ, GRA, SSHFC, Area Councils             |

# SINGLE WINDOW – REQUIREMENTS DOCUMENT

**Version:** 1.0  
**Date:** 2025-07-09  

## 1. Overview

Gambia Business Gateway (GBG) is a centralized digital platform developed to simplify business registration and compliance in The Gambia. It is designed as a one-stop-shop to allow entrepreneurs and business owners to register, apply for legal documentation, and fulfill ongoing compliance obligations online.

## 2. Objectives

- Enable end-to-end online business registration.
- Integrate with key institutions (MOJ, GRA, SSHFC, Local Councils).
- Allow document upload and digital submission.
- Provide a dashboard for tracking compliance.
- Accept digital payments (Wave, Gamswitch).
- Generate automated reminders for filing obligations.

## 3. Key Modules

### 3.1. Business Name Search & Reservation

**Input:** Desired company name.

**Features:**

- Check name availability (Search API via MOJ).
- Reserve name (store in backend with expiry).
- Notify user of expiration (6-month validity).

**Cost:** D500–D700 (payable via Wave/Gamswitch).

---

### 3.2. Online Application Submission

**Form Sections:**

- Company Type (Ltd, NGO, Sole Prop, etc.)
- Shareholders, Directors, Secretary
- Registered Office
- Business Activity

**Document Upload:**

- Memorandum of Association (PDF)
- Articles of Association (PDF)

**Integration:**

- MOJ API for registration submission

**Cost:** D15,000 base fee (share capital-based)

### 3.3. Payment Module

**Integration with:**

- Wave
- Gamswitch

**Allow:**

- Card payments
- Mobile Money
- Bank transfers

**Receipts & Confirmations:**

Issue receipts and confirmations for all payments.

### 3.4. TIN Application

- Integrate with GRA TIN API
- Auto-fill using user registration details
- Status tracking for TIN issuance

### 3.5. Social Security Registration

- Integration with SSHFC System
- Auto-registration into:
  - Federated Pension Scheme
  - Industrial Injuries Scheme
  - Housing Finance Scheme
- Notify user upon completion

### 3.6. Business License Application

- Integration with Area Councils/Municipalities (Kanifing, Banjul, Brikama, etc.)
- Allow upload of supporting documents
- Track approval status

---

### 3.7. Compliance Dashboard

- Track all annual and periodic obligations
- Display upcoming deadlines
- Alert users for:
  - Annual Returns
  - Tax Filings
  - License Renewals
  - Social Security Submissions

## 4. Ongoing Compliance Modules

### 4.1. Annual Returns Filing

- Upload financial statements
- Fill annual return form
- Update directors/shareholders
- Confirm registered office
- Calculate and process fees: D2,000–D5,000

### 4.2. Tax Compliance Integration

- Integration with GRA
  - Submit tax returns (March 31)
  - Upload quarterly payments
  - Monthly PAYE declaration
- Auto reminders for PAYE (15th of each month)

### 4.3. Social Security Contributions

- Monthly calculator for payroll contributions
- Auto-generate SSHFC files
- Submit to SSHFC system
- Reminder system for 15th monthly submission

### 4.4. Director/Shareholder Changes

- File change forms
- Upload resolution documents
- Notify MOJ
- Update backend profile

### 4.5. License Renewal Module

- Auto-track expiry dates
- Send notifications
- Allow renewal submission to councils

## 5. Admin Panel Features

- View all applications and statuses
- Download documents
- Edit submissions
- Communicate with applicants
- Manage payment records
- Add/remove compliance items

## 6. Technical Stack

| Component        | Tech Stack                                 |
|------------------|--------------------------------------------|
| Frontend         | Next.js (15 with App Router)               |
| Styling          | TailwindCSS / ShadCN UI                    |
| Backend          | Node.js API (Next.js API routes or NestJS) |
| Database         | PostgreSQL or MongoDB                      |
| Auth             | Clerk/Auth.js/Supabase Auth                |
| File Uploads     | Cloudinary or AWS S3                       |
| Payments         | Wave & Gamswitch SDKs                      |
| Integration APIs | MOJ, GRA, SSHFC, Area Councils             |

## 3. Key Modules

### 3.1. Business Name Search & Reservation

**Input:** Desired company name.

**Features:**

- Check name availability (Search API via MOJ).
- Reserve name (store in backend with expiry).
- Notify user of expiration (6-month validity).

**Cost:** D500–D700 (payable via Wave/Gamswitch).

---

### 3.2. Online Application Submission

**Form Sections:**

- Company Type (Ltd, NGO, Sole Prop, etc.)
- Shareholders, Directors, Secretary
- Registered Office
- Business Activity

**Document Upload:**

- Memorandum of Association (PDF)
- Articles of Association (PDF)

**Integration:**

- MOJ API for registration submission

**Cost:** D15,000 base fee (share capital-based)

### 3.3. Payment Module

**Integration with:**

- Wave
- Gamswitch

**Allow:**

- Card payments
- Mobile Money
- Bank transfers

**Issue receipts & confirmations**

### 3.4. TIN Application

- Integrate with GRA TIN API
- Auto-fill using user registration details
- Status tracking for TIN issuance

### 3.5. Social Security Registration

- Integration with SSHFC System
- Auto-registration into:
  - Federated Pension Scheme
  - Industrial Injuries Scheme
  - Housing Finance Scheme
- Notify user upon completion

### 3.6. Business License Application

- Integration with Area Councils/Municipalities (Kanifing, Banjul, Brikama, etc.)
- Allow upload of supporting documents
- Track approval status

---

### 3.7. Compliance Dashboard

- Track all annual and periodic obligations
- Display upcoming deadlines
- Alert users for:
  - Annual Returns
  - Tax Filings
  - License Renewals
  - Social Security Submissions

## 4. Ongoing Compliance Modules

### 4.1. Annual Returns Filing

- Upload financial statements
- Fill annual return form
- Update directors/shareholders
- Confirm registered office
- Calculate and process fees: D2,000–D5,000

### 4.2. Tax Compliance Integration

- Integration with GRA
  - Submit tax returns (March 31)
  - Upload quarterly payments
  - Monthly PAYE declaration
- Auto reminders for PAYE (15th of each month)

### 4.3. Social Security Contributions

- Monthly calculator for payroll contributions
- Auto-generate SSHFC files
- Submit to SSHFC system
- Reminder system for 15th monthly submission

### 4.4. Director/Shareholder Changes

- File change forms
- Upload resolution documents
- Notify MOJ
- Update backend profile

### 4.5. License Renewal Module

- Auto-track expiry dates
- Send notifications
- Allow renewal submission to councils

## 5. Admin Panel Features

- View all applications and statuses
- Download documents
- Edit submissions
- Communicate with applicants
- Manage payment records
- Add/remove compliance items

## 6. Technical Stack

| Component        | Tech Stack                                 |
|------------------|--------------------------------------------|
| Frontend         | Next.js (15 with App Router)               |
| Styling          | TailwindCSS / ShadCN UI                    |
| Backend          | Node.js API (Next.js API routes or NestJS) |
| Database         | PostgreSQL or MongoDB                      |
| Auth             | Clerk/Auth.js/Supabase Auth                |
| File Uploads     | Cloudinary or AWS S3                       |
| Payments         | Wave & Gamswitch SDKs                      |
| Integration APIs | MOJ, GRA, SSHFC, Area Councils             |
