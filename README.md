# Student Dashboard

A barcode/QR scanning solution designed to monitor student attendance and track time spent in a learning center (e.g., Kumon). This app provides a real-time view of which students are currently in the building and alerts staff when a student has stayed past a certain time threshold.

## Key Features

- **QR-Based Attendance:** Check students in and out instantly using a hardware scanner or manual input.
- **Live Monitoring:** A dashboard that updates time-elapsed in real-time.
- **Visual Alerts:** Automatic color-coding (Orange/Red) for students who have exceeded 25 or 30 minutes.
- **QR Management:** Generate and download printable PDF sheets containing QR codes for all students.
- **Admin Security:** Session-based authentication to protect student data.

## Tech Stack

- **Frontend:** React, TypeScript, Vite, React-PDF, React-Toastify.
- **Backend:** Node.js, Express, MongoDB, Mongoose.
- **Auth:** Express-Session with MongoStore for persistent logins.
- **Utilities:** Python scripts for bulk QR generation and CSV processing.

## Project Structure

- `/backend`: Express API and MongoDB schemas.
- `/frontend`: React SPA with TypeScript.
- `/backend/qr_processing`: Python utilities for batch-creating QR codes and UUIDs from student lists.

## Installation & Setup

### 1. Prerequisites
- Node.js (v16+)
- MongoDB (Local or Atlas)
- Python (Optional, for QR generation scripts)

### 2. Backend Setup
1. Navigate to `/backend` and run `npm install`.
2. Create a `.env` file in the `/backend` folder:
   ```env
   PORT=5000
   MONGO_URI=your_mongodb_uri
   SESSION_SECRET=your_secret_key
   PASSWORD=admin_login_password
   NODE_ENV=development
3. Start the server: npm run dev.

### 3. Frontend Setup
Navigate to /frontend and run npm install.

Create a .env file in the /frontend folder:

Code snippet

VITE_PORT=5000
Start the client: npm run dev.

### Usage
Populate Students: Add students manually via the "All Students" dashboard or use the Python scripts in /qr_processing to import from a CSV.

Print Codes: Go to the "QR Codes" tab to download a PDF of all student IDs.

Scanning: On the "Current" dashboard, keep the "Scanner" input focused. Scanning a QR code will:

Add the student to the board if they are arriving.

Remove the student if they are already present (auto-checkout).

Monitoring: The "Minutes" column updates automatically. Rows turn red when a student has been present for >30 minutes.
