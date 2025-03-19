# Interview Management System

## Introduction
The **Interview Management System** is a web-based tool that allows companies to post jobs, view available interviewers, and send interview invitations via email with an attached `.ics` (calendar invite) file. The system is built using **Node.js, Express, MongoDB, and EmailJS**.

---

## Features
- **Company Dashboard:** Allows companies to add jobs, view posted jobs, and see available interviewers.
- **Interviewer List:** Matches interviewers based on job skills and displays their details.
- **Email Invitation System:** Sends an email to the interviewer with a calendar invite (.ics file).
- **Database Integration:** Stores job postings and interviewers in **MongoDB**.

---

## Prerequisites
Before setting up the project, ensure that you have the following installed on your system:

1. **Node.js** (Download from [https://nodejs.org/](https://nodejs.org/))
2. **MongoDB** (Download from [https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community))
3. **Git** (Download from [https://git-scm.com/downloads](https://git-scm.com/downloads))

---

## Installation Guide

### **1. Clone the Repository**
Open a **Terminal/Command Prompt** and run:
```sh
 git clone https://github.com/yourusername/interview-management-system.git
 cd interview-management-system
```

### **2. Install Dependencies**
Run the following command to install required Node.js packages:
```sh
 npm install
```
This will install:
- `express` (for backend server)
- `mongoose` (for MongoDB integration)
- `nodemailer` (for sending emails)
- `ical-generator` (for generating `.ics` calendar invites)
- `cors` (for enabling cross-origin requests)

### **3. Set Up MongoDB**
#### **Option 1: Run MongoDB Locally**
1. Open a terminal and start the MongoDB server:
   ```sh
   mongod --dbpath /path/to/data/db
   ```
   *(Replace `/path/to/data/db` with the actual path where you want MongoDB to store its data.)*
2. Verify MongoDB is running by opening another terminal and typing:
   ```sh
   mongo
   ```
3. Create the database:
   ```sh
   use interview_tool
   ```

#### **Option 2: Use MongoDB Atlas (Cloud Database)**
1. Sign up at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Create a new cluster and get the **connection string**.
3. Replace `mongodb://localhost:27017/interview_tool` in `server.js` with your connection string.

### **4. Start the Server**
Run the following command to start the backend server:
```sh
 node server.js
```
You should see:
```
Server is running on port 3000
MongoDB connected locally...
```

### **5. Start the Frontend**
Since this is a simple **HTML, CSS, and JavaScript** frontend, no separate frontend server is needed.
1. Open the `public` folder in **File Explorer**.
2. Open **`welcome.html`** in your web browser.

Alternatively, you can start a simple server using Python:
```sh
 cd public
 python -m http.server 8000
```
Now open your browser and go to:
```
 http://localhost:8000/welcome.html
```

---

## Usage Guide

### **1. Company Login & Job Posting**
- Navigate to `company1.html`, `company2.html`, or `company3.html`.
- Click **“Add New Job”** and fill out the form.
- View posted jobs in the **Jobs Posted** section.
- Click **“Get Interviewer”** to see matching interviewers.

### **2. Viewing Interviewers & Sending Invitations**
- The **Interviewers Available** section displays interviewers and their availability.
- Click **“Contact Interviewer”**.
- A **pop-up modal** appears, allowing you to select a date and time.
- Click **Submit** to send the invitation email with a `.ics` attachment.
- A success message appears: `Invite sent successfully`.

---

## Troubleshooting

### **1. MongoDB Not Running?**
If you get a MongoDB connection error:
- Ensure MongoDB is installed and running (`mongod` command).
- If using Atlas, verify the connection string in `server.js`.

### **2. Emails Not Sending?**
- Ensure you have an **EmailJS account** and configured the service.
- Check `service_id`, `template_id`, and `user_id` in the API request.
- Verify that the email address is valid (only `gmail.com` emails except `in@gmail.com`).

### **3. Jobs or Interviewers Not Displaying?**
- Check the browser console (`F12 > Console`) for errors.
- Restart the server (`Ctrl+C` then `node server.js`).
- Ensure MongoDB collections have data.

---

## Future Improvements
- Add a **login system** for companies and interviewers.
- Improve UI/UX with **React.js or Vue.js**.
- Add **real-time notifications** for new job postings and interview invites.

---

## Contributors
- **Your Name** (Main Developer)
- **Additional Contributors** (If Any)

---

## License
This project is open-source and available under the **MIT License**.

