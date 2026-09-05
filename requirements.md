# 📋 Requirements Specification – STM Internet Cafe Management System

## 1. Introduction
This document outlines the requirements for the STM Internet Café Management System.  
It defines the functional and non-functional requirements, as well as constraints that guide development.

---

## 2. Functional Requirements
The system must provide the following features:

### 2.1 User Login
- Staff and administrators can log in securely with username and password.  
- Role-based access control (Admin vs. Staff).  
- Passwords must be stored using hashing and salting.  

### 2.2 Session Tracking
- Automatically track customer computer usage time.  
- Allow staff to start, pause, and end sessions.  
- Display real-time session duration and cost.  

### 2.3 Billing
- Generate bills based on session duration and services used.  
- Support manual adjustments (discounts, promotions).  
- Print or export receipts in PDF format.  

### 2.4 Inventory Management
- Track café inventory (snacks, drinks, accessories).  
- Update stock levels automatically after sales.  
- Generate low-stock alerts.  

---

## 3. Non-Functional Requirements
The system must meet the following quality attributes:

- **Performance:**  
  - Support at least 50 concurrent users without degradation.  
  - Response time for billing and session queries must be under 2 seconds.  

- **Security:**  
  - Encrypt all sensitive data (passwords, billing info).  
  - Role-based access control to prevent unauthorized actions.  

- **Usability:**  
  - Provide a clean, intuitive interface for staff.  
  - Support accessibility standards (WCAG 2.1 compliance).  

- **Reliability:**  
  - System uptime must be at least 99.5%.  
  - Automatic recovery from server crashes within 5 minutes.  

---

## 4. Constraints
- **Budget:** Limited to [insert amount, e.g., $5,000].  
- **Timeline:** Must be completed within [insert duration, e.g., 12 weeks].  
- **Technology Stack:**  
  - Backend: [e.g., Python Django or Node.js].  
  - Database: PostgreSQL or MySQL.  
  - Deployment: Compatible with Windows/Linux servers.  

---

## 5. Approval
This requirements specification serves as the baseline for design and development.  
Approved by: ______________________  
Date: ______________________
