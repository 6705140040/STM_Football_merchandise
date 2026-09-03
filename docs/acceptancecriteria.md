# ✅ Acceptance Criteria – STM Internet Cafe Management System

## 1. Login (Secure Authentication)
- Users must log in with a valid username and password.  
- Passwords must be stored securely using hashing and salting.  
- Invalid login attempts must display an error message.  
- After 5 failed login attempts, the account must be locked for 15 minutes.  
- Successful login must redirect staff/admin to the dashboard within 2 seconds.  

---

## 2. Performance
- The system must support at least 50 concurrent users without noticeable slowdown.  
- Average response time for session tracking and billing queries must be under 2 seconds.  
- Reports must generate within 5 seconds for datasets up to 5,000 records.  
- The system must recover from server crashes within 5 minutes.  

---

## 3. Data Storage
- Session logs must be stored securely in the database.  
- Billing records must be encrypted at rest.  
- Daily backups must occur automatically every 24 hours.  
- Users must be able to retrieve session and billing records within 5 seconds of request.  
- Deleted records must not be recoverable by unauthorized users.  

---

## 4. Approval
This acceptance criteria document defines the measurable conditions required for project success.  
Approved by: ______________________  
Date: ______________________
