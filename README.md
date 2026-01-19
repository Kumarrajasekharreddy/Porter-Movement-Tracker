# 👤 Patient Kiosk: Face Recognition + Wait Time Dashboard

A real-time face recognition system for hospital patient check-in/check-out, with live dashboard showing waiting times.

---

## 🎯 Purpose

- Automate patient identification using face scan → fetch UHID, Name, Mobile  
- Track check-in/check-out times → calculate wait duration  
- Display live dashboard of patients waiting >2 mins  
- Auto-remove patient from dashboard when they leave camera view  
- Built for Apollo Hospitals (simulated environment)

[Click Here 👇](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/project-collage.png)  
![Project Collage](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/project-collage.png)

---

## 🖼️ Screenshots

### 1. Face Scan + Patient Info Display

[![Face Scan](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/System%20recognizes%20patient.png)](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/System%20recognizes%20patient.png)  
*System recognizes patient → displays UHID, Name, Mobile*

### 2. Multi-Person Detection + Wait Time Tracking

[![Multi-Face Detection](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/face-scan.png)](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/face-scan.png)  
*Detects multiple patients → assigns ID, tracks time since check-in*

### 3. Patient Leaves → Auto-Removed from Dashboard

[![Patient Left](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/When%20patient%20moves%20out%20of%20frame.png)](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/When%20patient%20moves%20out%20of%20frame.png)  
*When patient moves out of frame → removed from dashboard*

### 4. Live Waiting Patients Dashboard

[![Waiting Dashboard](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/Shows%20patients%20waiting.png)](https://github.com/Kumarrajasekharreddy/Face-Recognition-Checkin-Checkout-Dashboard/blob/main/screenshots/Shows%20patients%20waiting.png)  
*Shows patients waiting >2 mins → helps staff prioritize*

---

## 💡 Key Code Snippets (Just the Magic)

### Matching Face → Fetch Patient Info
```python
best_match = face_recognition.face_distance(encodings, face)[0] < 0.5
name, uhid, mobile = details[best_match_index] if best_match else ("Unknown", "", "")
