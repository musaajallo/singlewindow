
# SINGLE WINDOW – GAMBIA BUSINESS GATEWAY

**Version:** 1.0  
**Date:** 2025-07-09  
**Prepared by:** Musa A. Jallow

## Overview

Gambia Business Gateway (GBG) is a centralized digital platform designed to simplify business registration and compliance in The Gambia. It serves as a one-stop-shop for entrepreneurs and business owners to register, apply for legal documentation, and fulfill ongoing compliance obligations online.

## Features

- End-to-end online business registration
- Integration with key institutions (MOJ, GRA, SSHFC, Local Councils)
- Document upload and digital submission
- Compliance dashboard with reminders
- Digital payments (Wave, Gamswitch)
- Automated reminders for filing obligations
- Admin panel for application and compliance management

## Key Modules

- **Business Name Search & Reservation:** Name availability check, reservation, and expiry notifications
- **Online Application Submission:** Company registration forms, document upload, and MOJ API integration
- **Payment Module:** Card, mobile money, and bank transfer support with receipts
- **TIN Application:** GRA TIN API integration and status tracking
- **Social Security Registration:** SSHFC integration and auto-enrollment
- **Business License Application:** Area Council integration and document upload
- **Compliance Dashboard:** Track annual/periodic obligations and deadlines
- **Ongoing Compliance:** Annual returns, tax, social security, director/shareholder changes, license renewal

## Technical Stack

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

## Getting Started

1. Install dependencies:
   ```bash
   npm install
   ```
2. Run the development server:
   ```bash
   npm run dev
   ```
3. Open [http://localhost:3000](http://localhost:3000) in your browser.

You can start editing the app by modifying `src/app/page.tsx`. The page auto-updates as you edit the file.

## Admin & Compliance

- View and manage all applications and statuses
- Download and edit submissions
- Communicate with applicants
- Manage payment records and compliance items

## Windows Setup

See the following for Windows-specific instructions:

- **[Windows Setup Guide](.github/SETUP-WINDOWS.md)**
- **[Windows Troubleshooting](.github/TROUBLESHOOTING-WINDOWS.md)**
- **[PowerShell Commands](.github/WINDOWS-COMMANDS.md)**

## License

This project is licensed for use by the Gambia Business Gateway project team.
