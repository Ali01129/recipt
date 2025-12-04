# AI Invoice Generator ("Recipt") — High‑Level Development Plan
A structured milestone roadmap to help you build the app in small, manageable phases while always keeping a minimal working version running.

---

## **Milestone 0 — Project Setup (Foundation)**
**Goal:** Prepare all environments, repos, CI/CD, and folder structure.
- Initialize React Native (TypeScript) project
- Initialize NestJS backend
- Create shared environment config (.env)
- Connect Firebase (auth + database)
- Set up Supabase buckets (invoice PDFs/images)
- Prepare Render backend deployment (free tier)
- Basic CI/CD (optional)

---

## **Milestone 1 — Minimal Working App (MVP)**
**Goal:** User can sign up, log in, and create a basic invoice without AI.
### **Frontend (RN)**
- User registration + login (Firebase Auth)
- Basic app navigation (Home, Create Invoice, My Invoices)
- Simple invoice creation form (title, items, total, due date)

### **Backend (Nest)**
- API to store invoices in Firebase
- API to upload invoice PDF to Supabase bucket
- API to fetch user invoices

### **Output**
- User can log in → create invoice → view invoice → download invoice
- **AI NOT implemented yet**

---

## **Milestone 2 — Invoice Sharing + Recipient Flow**
**Goal:** Allow invoices to be sent to another person.
### **Backend**
- Endpoint to send invoice email (using nodemailer or Resend API)
- Save recipient info (email, name)
- Logic to detect if recipient has an account

### **Frontend**
- Add recipient to invoice
- Page for "Incoming Invoices"
- Email link redirects user to the app or a web view

### **Output**
- Sender can create invoice → recipient receives email + sees invoice in-app (if registered)

---

## **Milestone 3 — Invoice Status Workflow**
**Goal:** Both parties can mark invoices as paid.
### **Backend**
- Invoice status: `pending`, `review`, `paid`
- Sender/receiver status update endpoints
- Notification triggers

### **Frontend**
- Button for receiver: **Mark as Paid** → sets status to `review`
- Sender gets notification → confirms → sets `paid`
- Add **paid stamp** to PDF
- Inbox notifications (Firebase Cloud Messaging)

### **Output**
Complete invoice lifecycle:  
created → sent → receiver marks paid → sender confirms → both notified.

---

## **Milestone 4 — AI Data Extraction (Images + Chat)**
**Goal:** Add AI that extracts fields from an uploaded image or via conversation.
### **Backend**
- AI endpoint using OpenAI API
- Image extraction: invoice OCR → structured data
- Chat endpoint: user can ask AI to fill invoice details

### **Frontend**
- Upload invoice image → show extracted fields → auto-fill invoice form
- Add chat UI with AI assistant

### **Output**
AI can:  
- read invoice images  
- extract numbers/dates/items  
- pre-fill a new invoice form
- chat with user about invoices

---

## **Milestone 5 — PDF Improvements + History**
**Goal:** Make invoices professional and stored properly.
### **Backend**
- Generate nicer PDFs (header, logo, paid stamp)
- Store PDFs in Supabase bucket
- Maintain invoice version history

### **Frontend**
- Better invoice UI
- Invoice preview
- Filter/search invoices

---

## **Milestone 6 — Subscription System (Monthly + Yearly)**
**Goal:** Monetization.
### **Backend**
- Stripe subscription API integration
- Free plan + paid plans (limits on invoices, AI usage)
- Webhook to sync subscription status

### **Frontend**
- Pricing page
- Upgrade/downgrade subscription
- Restrict features based on plan

---

## **Milestone 7 — Polish + Release**
**Goal:** Make the app ready for public use.
- Onboarding screens
- Profile page
- Better error-handling and loaders
- Cleanup UI/UX
- Deployment to Play Store + TestFlight

---

## **Optional Future Upgrades**
- Auto-send payment reminders
- Analytics dashboard (income/outgoing)
- Tax report generator
- AI smart invoice categorization
- Ability to receive payments inside the app (Stripe Connect)

---

## **Summary Roadmap**
1. **Setup**  
2. **MVP: Basic invoices**  
3. **Sharing + recipients**  
4. **Status workflow**  
5. **AI extraction + chat**  
6. **PDF + storage**  
7. **Subscriptions**  
8. **Polish + release**

---
