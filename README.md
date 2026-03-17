# Telemedicine Intake System

Web platform for automating patient intake and screening for telemedicine services.

The system collects patient registration data, consent forms, and screening information before consultations begin. It reduces administrative workload for healthcare staff and improves the accuracy of patient records.

Used in telemedicine services operated by Kamphaeng Phet Municipality, Thailand.

---

## Problem

Telemedicine appointments required nurses to manually collect:

- patient registration details
- consent forms
- preliminary screening information

This created administrative bottlenecks and delayed consultations.

---

## Solution

This system digitizes the intake workflow by:

- providing an online patient intake form
- validating and structuring patient data
- automatically storing records in Google Sheets
- allowing staff to review intake data before consultations

---

## Architecture

```
Patient
   ↓
Next.js Web App
   ↓
API Routes
   ↓
Google Sheets
```

---

## Tech Stack

- Next.js
- Node.js
- Google Sheets API
- TailwindCSS

---

## Project Structure

```
app/   Next.js application (UI, routing, API routes)
```

---

## Deployment Context

The system supports municipal telemedicine services operated by Kamphaeng Phet Municipality in Thailand.

Example deployment reference:
https://www.kppmu.go.th/news-detail?hd=1&id=124000

---

## License

MIT
