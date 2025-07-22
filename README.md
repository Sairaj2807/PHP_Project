# PHP Currency Exchange Platform

A complete PHP-based web application with login/signup, referral system, dynamic currency exchange calculator, email notifications, and user data management. Hosted on Hostinger with MySQL backend.

---

## 🔧 Features

- 🔐 **User Authentication**: Signup & Login system with validation
- 🧑‍🤝‍🧑 **Referral System**: Unique referral codes with tracking
- 💱 **Currency Exchange**: Real-time & fixed-rate conversions (e.g., USDT ⇄ INR)
- 📧 **Email Notifications**: Email confirmations & updates (PHPMailer)
- 💾 **MySQL Integration**: Securely stores user data
- 🌐 **Hostinger Hosting**: Easily deployable on shared or VPS plans
- 🔐 **Security**: Input sanitization & basic protections

---

## 🧑‍💻 Technologies Used

- PHP 8+
- MySQL
- JavaScript (for dynamic UI)
- PHPMailer
- HTML/CSS
- Hostinger (for deployment)

---

## 🗃️ Database Schema (MySQL)

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password_hash VARCHAR(255),
    referral_code VARCHAR(20),
    referred_by VARCHAR(20),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    from_currency VARCHAR(10),
    to_currency VARCHAR(10),
    amount DECIMAL(10, 2),
    exchanged_amount DECIMAL(10, 2),
    rate DECIMAL(10, 4),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
