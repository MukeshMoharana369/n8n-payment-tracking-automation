# Payment Tracking & Billing (n8n)

This repository contains **Automation 4: Payment Tracking & Billing**, built using **n8n**.

The purpose of this automation is simple:
- Track client payment due dates
- Send automated reminders at the right time
- Keep payment records updated
- Remove manual payment chasing

This automation is designed for **coaches, consultants, and service-based businesses**.

---

## 🧠 What This Automation Does

Once a client exists, the system:

1. Checks payment due dates daily
2. Calculates how close each payment is to its due date
3. Sends reminders automatically:
   - Before due date
   - On due date
   - After due date (overdue)
4. Updates reminder history to avoid duplicate messages
5. Stops completely once payment is marked as paid

No leads.  
No onboarding.  
Only payment protection.

---

## 🗂 Data Source

The automation uses **Google Sheets** as the single source of truth.

Required columns:
- ClientName
- ClientEmail
- PlanType
- Amount
- DueDate
- Status (paid / unpaid)
- LastReminderSent

---

## ⚙️ How It Works (High Level)

- Runs once per day using a Cron trigger
- Reads all client payment records
- Ignores paid clients automatically
- Calculates `daysUntilDue` internally (not stored in the sheet)
- Uses switch logic to decide which reminder to send
- Updates reminder history after sending messages

---

## 🖐 Manual Control

The coach remains in full control.

- When payment is received:
  - Change `Status` to `paid`
- The automation will immediately stop for that client

No automation ever changes payment status automatically.

---

## 🚫 What This Automation Does NOT Do

- Does not collect payments
- Does not negotiate or handle refunds
- Does not use AI for financial decisions
- Does not trigger from leads or forms

---

## 📦 Files in This Repository

- `automation-payment-tracking.json`  
  → n8n workflow export

- `demo-data-sample.csv` (optional)  
  → Sample data for testing and demo

---

## 🎯 Use Case

This automation is ideal once a business has:
- Multiple active clients
- Recurring or scheduled payments
- A need to protect cash flow without manual tracking

---

## 🏁 Summary

This is a **boring but critical automation**.

It doesn’t try to be smart.  
It tries to be **reliable**.

That’s the point.
