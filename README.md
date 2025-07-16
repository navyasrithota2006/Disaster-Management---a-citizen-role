# 🌐 Disaster Management Web App

A comprehensive offline-first disaster aid system built with **Flask**, **MySQL**, **HTML/CSS/JS**, and animated UI for robust user experience. The app connects affected users with help and enables volunteers and contributors to offer support. Admins can monitor the entire activity via a dashboard.

---

## 🚀 Features

### 🔹 General Public
- 📍 **Geolocation-based Help Requests**
  - Food, Medical, Shelter, Army, and Fund requests with location + contact
- 🌤️ **Weather Updates**
  - Location-based 5-day mock forecast (can be extended to real API)
- 📑 **Success Page** per category confirming help submitted
- 💬 **Contact Page** with social handles and phone numbers

### 🔹 Volunteers & Contributors
- 🔐 Protected **Login System**
- 📝 Submit form with:
  - Role (Volunteer / Contributor / Both)
  - Email & Opinion
- 📥 Stored in database for admin review

### 🔹 Admin
- 🛡️ **Admin Login**
  - Admin Email: `admin@gmail.com`
  - Password: `admin123`
- 📊 **Admin Dashboard**:
  - View all help requests (food, medical, shelter, army, funds)
  - Status indicators (🟡 Pending / 🟢 Resolved)
  - Filtered view of contributors/volunteers/both

---

## 🔧 Tech Stack

- **Frontend**: HTML5, CSS3, JavaScript
- **Backend**: Python Flask
- **Database**: MySQL (with `mysql-connector-python`)
- **Libraries**:
  - Chart.js (for dashboard visualization)
  - Font Awesome (for icons)
  - Animated background images

---

## 🛠️ Setup Instructions

### ✅ Prerequisites
- Python 3.x
- MySQL
- pip (Python package installer)

### 📦 Install Dependencies

```bash
pip install flask mysql-connector-python
pip install -r requirements.txt
```


# 🗄️ Database Setup


- CREATE DATABASE disaster_db;
  USE disaster_db;

- CREATE TABLE admin_users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    fullname VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(100)
  );

- CREATE TABLE volunteers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    role VARCHAR(20),
    opinion TEXT,
    date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
  );

- CREATE TABLE help_requests (
    id INT AUTO_INCREMENT PRIMARY KEY,
    disaster_type VARCHAR(50),
    latitude VARCHAR(50),
    longitude VARCHAR(50),
    timestamp DATETIME,
    status VARCHAR(20) DEFAULT 'pending'
  );

- CREATE TABLE medical_requests (
    id INT AUTO_INCREMENT PRIMARY KEY,
    latitude VARCHAR(50),
    longitude VARCHAR(50),
    needs TEXT,
    contact VARCHAR(50),
    notes TEXT,
    status VARCHAR(20) DEFAULT 'pending'
  );

- CREATE TABLE shelter_requests (
    id INT AUTO_INCREMENT PRIMARY KEY,
    latitude VARCHAR(50),
    longitude VARCHAR(50),
    needs TEXT,
    contact VARCHAR(50),
    notes TEXT,
    status VARCHAR(20) DEFAULT 'pending'
  );

- CREATE TABLE funds_requests (
    id INT AUTO_INCREMENT PRIMARY KEY,
    latitude VARCHAR(50),
    longitude VARCHAR(50),
    assistance TEXT,
    contact VARCHAR(50),
    notes TEXT,
    status VARCHAR(20) DEFAULT 'pending'
  );

- CREATE TABLE army_requests (
    id INT AUTO_INCREMENT PRIMARY KEY,
    latitude VARCHAR(50),
    longitude VARCHAR(50),
    needs TEXT,
    contact VARCHAR(50),
    notes TEXT,
    status VARCHAR(20) DEFAULT 'pending'
  );
  
---

# ✅ Insert admin:

INSERT INTO admin_users (fullname, email, password)
VALUES ('Admin', 'admin@gmail.com', 'admin123');


# ▶️ Running the App

python app.py


Visit: http://127.0.0.1:5000/


# 📂 Project Structure


project/
│
├── app.py
├── db_config.py
├── templates/
│   ├── index.html
│   ├── help.html
│   ├── help_food.html
│   ├── help_medical.html
│   ├── help_shelter.html
│   ├── help_army.html
│   ├── help_funds.html
│   ├── vc.html
│   ├── dashboard.html
│   ├── contact.html
│   ├── success.html
│   ├── admin_login.html
│   ├── signup.html
│   ├── weather.html
│   └── thank_you_*.html
│
├── static/
│   ├── weather.jpg
│   ├── dash.jpg
│   ├── login-hero-bg.jpg
│   ├── sw.js
│   └── styles.css (optional)


