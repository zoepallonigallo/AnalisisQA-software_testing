# QA Analysis and Software Testing 

This repository contains simulations and practical cases of QA Testing applied to different web environments. It documents the tested functionalities, the bugs reported, the steps to reproduce them, and the classification of their impact.

> **Note:** All cases include supporting documentation (screenshots) and were initially managed using test matrices in Excel.

---

## Case 1: Order Management Software 
**Context:** Optimization and process fixing for a catering and artisanal product sales system.

**Tested functionalities:**
* Stock verification.
* Payment gateway security.
* Web ordering system.
* Client verification and registration.
* Recipe modification in the database.
* Delivery service contact interface.

<img width="1555" height="640" alt="image" src="https://github.com/user-attachments/assets/8777e93d-f184-439e-b12a-8883ec082f52" />

**Bug Report**
* **Bug ID:** `0123d`
* **Title:** Critical failure in the new client registration form.
* **Steps to reproduce:**
  1. Navigate to the registration page.
  2. Fill out all mandatory fields in the form.
  3. Click the "Register" button.
* **Expected Result:** The system creates the account and redirects to the user dashboard.
* **Actual Result:** No response on the client interface; the console throws a `400 Bad Request` error.
* **Severity:** Critical | **Priority:** High

---

## Case 2: Flight Search Web App - Flight Search (Despegar Web App)
**Context:** Integration testing on the main search engine.

**Tested functionalities:**
* Origin and destination airport selector.
* Date selector (round trip).
* Passenger quantity selector.
* Core flight search engine.

<img width="1385" height="341" alt="image" src="https://github.com/user-attachments/assets/5a58753a-eeb0-46af-b15f-5689e7be248b" />

**Bug Report**
* **Bug ID:** `A005`
* **Title:** Flight search engine crash.
* **Steps to reproduce:**
  1. Fill in the origin, destination, dates, and passengers fields with valid data.
  2. Press the "Search" button.
* **Expected Result:** Display the list of available flights according to the filters.
* **Actual Result:** Redirection to a blank page; proxy authentication error `407 Proxy Authentication Required`.
* **Severity:** Critical | **Priority:** High

---

## Case 3: Video Web App (YouTube Simulation)
**Context:** Usability and user interface interaction testing.

**Tested functionalities:**
* Video play and pause.
* Volume control.
* Subscription system.
* Full-screen mode toggle.
* Playback speed adjustment.

<img width="1518" height="414" alt="image" src="https://github.com/user-attachments/assets/38624f91-8f8b-479f-9fb6-c45966a796a9" />

**Bug Report**
* **Bug ID:** `b129`
* **Title:** State lock on the unsubscribe button.
* **Steps to reproduce:**
  1. Subscribe to a channel by pressing the "Subscribe" button.
  2. Attempt to revert the action by pressing the same button (now labeled "Unsubscribe").
* **Expected Result:** The user is unsubscribed from the channel and the button returns to its initial state.
* **Actual Result:** The button's user interface (UI) freezes and the unsubscribe request is not sent to the server.
* **Severity:** Major | **Priority:** High

---

## Case 4: Email Client (Gmail Simulation)
**Context:** Field validation and text formatting (Rich Text) testing.

**Tested functionalities:**
* "To" and "Subject" fields validation.
* "Send" button execution.
* Maximum character restrictions.
* Font formatting tools.
* File attachment function.
* Hyperlink (URL) insertion and parsing.

<img width="1527" height="516" alt="image" src="https://github.com/user-attachments/assets/a895c95c-76aa-4d2a-a047-d0db79fc1659" />

**Bug Reports**

**Bug ID:** `me239`
* **Title:** Failure in the automatic parsing of functional hyperlinks.
* **Steps to reproduce:**
  1. Copy three different URLs (e.g., YouTube, Instagram, Facebook).
  2. Paste the links into the email body keeping the original format.
* **Expected Result:** The system should recognize the structure and automatically convert the text into functional hyperlinks.
* **Actual Result:** The URLs are inserted and remain in inactive plain text format.
* **Severity:** Minor | **Priority:** Medium

**Bug ID:** `me236`
* **Title:** Absence of validation on the maximum character limit in the message body.
* **Steps to reproduce:**
  1. Write a string of more than 100 alphabetical characters in the message box.
  2. Repeat the test by injecting numbers and special characters (`. , - _`) exceeding the 100-character barrier.
* **Expected Result:** The system should block text entry upon reaching the established limit and inform the user.
* **Actual Result:** There is no limit validation; the field allows infinite text entry.
* **Severity:** Moderate | **Priority:** Medium
