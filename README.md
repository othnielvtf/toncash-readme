# TONCA$H Project

<div align="center">
  <img src="https://images.squarespace-cdn.com/content/v1/66b9a1afe4355a5823dc7d8b/f5b11dd2-3393-48f3-b62c-3f2ed2560179/TS+Logomark+Color+%281%29.png?format=300w" alt="TONCA$H Logo">
</div>

## Frontend
**Hosting:**
- **Platform:** Vercel
- **Purpose:**
  - Deploy TONCA$H static and serverless web components of the Telegram web app.
  - Handle dynamic rendering for the app.
- **Features:**
  - Automatic CI/CD pipeline from Git repositories.
  - Edge caching for fast content delivery.
- **Tech Stack:**
  - **Framework:** React JS with Vite
  - **Styling:** Tailwind CSS for responsive design.
  - **Language:** JavaScript/TypeScript for frontend logic.

## Backend APIs
**Hosting:**
- **Platform:** AWS EC2 instances
- **Purpose:**
  - Run backend services and APIs for authentication for Affiliate Network integration, third-party or partner integration, and Telegram Bot messaging.
  - Provide integration endpoints for public routes.
- **Tech Stack:**
  - **Language:** Node.js and PHP (SlimPHP)
- **Database:**
  - **Primary:** Firebase Firestore (real-time database for user data, rewards, deals).
  - **Secondary:** MySQL

## Database and Authentication
**Database:**
- **Firebase Firestore:**
  - For storing user profiles, deals, redemptions, and rewards.
**Authentication:**
- **Platform:** Firebase Authentication.
- **Purpose:**
  - Authenticate admin users to the CMS and other third-party integration to the database.

## Cloud Functions
**Platform:** Firebase Functions
- **Purpose:**
  - Execute serverless tasks like validating user rewards, processing transactions, or triggering notifications.
  - Process image upload.

## Notifications and Webhooks
**Telegram API Integration:**
- Send user-specific notifications for new deals, redemption confirmations, and rewards.
- **Implementation:**
  - Use webhooks to log Telegram interactions.

## DevOps and Monitoring
**CI/CD:**
- Vercel and GitHub integration for frontend deployment.
**Monitoring:**
- **Platform:** AWS CloudWatch (for API and server monitoring), Firebase Crashlytics (for frontend).
- **Purpose:**
  - Monitor latency, errors, and usage analytics.

## Security
**SSL/TLS:**
- Use Vercel for frontend SSL and AWS ACM for backend SSL certificates.
**Firebase Rule:**
- Use Firebase rules for whitelisting domains, permissions to read, write and update the database.
**Multi-factor auth:**
- Implement MFA for admin users to login to the CMS.
**Audit Trails:**
- Every change on the user balance, cashback has an audit trail of each change and person who changed it.

## Caching Layer
- **Purpose:**
  - Optimize performance for frequently accessed data (e.g., deal listings, user profiles).
- **Implementation:**
  - Use Cloudflare and Vercel as a caching layer for frequently queried data.
  - Integrate caching mechanisms in AWS EC2 for backend APIs.

## Backup and Disaster Recovery
**Database Backup:**
- Schedule backups for Firestore (GCP) and MySQL databases (AWS RDS automated snapshots).
**Disaster Recovery Plan:**
- Define RTO (Recovery Time Objective) and RPO (Recovery Point Objective).
- Implement multi-region backups for databases and deploy backend services in multiple AWS regions for failover.

## Analytics
**Purpose:**
- Gain insights into user behavior, deal performance, and system usage.
**Implementation:**
- Use Google Analytics, Firebase Analytics, Telemetry, and Mixpanel for frontend and in-app tracking.

## Payment Integration
**Purpose:**
- TONCA$H involves payments for redemptions in TON, Bitcoin, or USDT.
**Implementation:**
- Use trusted payment processors or wallets.
- Encrypt payment data at rest and in transit.

## Localization and Multi-language Support
**Purpose:**
- Support multiple languages for deals and user interfaces, currently in English, Spanish, German, Bahasa Indonesia and Malaysia, Italian, Vietnamese, and Russian.
- Show deals that are region-based.
**Implementation:**
- Utilize React multi-language libraries support.
- Filter deals via region through Firebase multi-lang support.

## Development Setup
To set up the development environment, follow these steps:

1. Use Node Version Manager (NVM) to switch to Node.js version 18:
   ```bash
   nvm use 18
   ```

2. Install the necessary npm packages:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```
