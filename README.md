# Powder House - User & Admin Login System

✅ **Complete authentication system for Powder House E-commerce website**

Built with PHP, MySQL, and designed for XAMPP localhost development.

---

## 🎯 Features

✅ User Login & Authentication
✅ Admin Dashboard with User Management
✅ User Dashboard with Profile
✅ Role-Based Access Control (Admin/User)
✅ Password Hashing with Bcrypt
✅ Session-Based Authentication
✅ SQL Injection Prevention (Prepared Statements)
✅ Responsive Design
✅ Demo Credentials Included

---

## 📁 Files Included

```
├── db.php                    # Database connection
├── login.php                 # Login form & authentication
├── logout.php                # Logout handler
├── admin-dashboard.php       # Admin panel
├── user-dashboard.php        # User dashboard
├── includes/header.php       # Navigation with login/logout
└── README.md                 # This file
```

---

## 🚀 Quick Start (XAMPP)

### Step 1: Create Database

1. Open `http://localhost/phpmyadmin`
2. Create new database: `powder_house`
3. Run this SQL:

```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  email VARCHAR(150) NOT NULL UNIQUE,
  password VARCHAR(255) NOT NULL,
  role ENUM('user','admin') NOT NULL DEFAULT 'user',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO users (name, email, password, role) VALUES 
('Admin User', 'admin@powder.com', '$2y$10$N9qo8uLOickgx2ZMRZoMyeIjZAgcg7b3XeKeUxWdeS86E36P4/LLa', 'admin'),
('Regular User', 'user@powder.com', '$2y$10$N9qo8uLOickgx2ZMRZoMyeIjZAgcg7b3XeKeUxWdeS86E36P4/LLa', 'user');
```

### Step 2: Copy Files

1. Download the repository as ZIP
2. Extract to `C:\xampp\htdocs\powder_house\`
3. Create folder: `includes/`

### Step 3: Start Services

1. Start XAMPP → Apache + MySQL
2. Go to: `http://localhost/powder_house/login.php`

---

## 👤 Demo Credentials

| Role | Email | Password |
|------|-------|----------|
| **Admin** | admin@powder.com | admin123 |
| **User** | user@powder.com | user123 |

---

## 📝 File Contents

### 1. db.php (Database Connection)
```php
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "powder_house";

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

$conn->set_charset("utf8");
?>
```

### 2. login.php
Contains:
- Login form with email/password
- Credential verification
- Session management
- Role-based redirect (admin/user dashboard)
- Beautiful CSS styling
- Demo credentials display

### 3. logout.php
Simple logout handler that destroys session.

### 4. admin-dashboard.php
Shows:
- Total users count
- Admin count
- Regular users count
- All users table
- Admin quick actions

### 5. user-dashboard.php
Shows:
- User profile info
- Available features
- Quick action buttons
- Welcome message

### 6. includes/header.php
Updated navigation that shows:
- Login button (not logged in)
- Dashboard link (logged in)
- Logout button (logged in)
- User name display

---

## 🔒 Security Features

✅ **Prepared Statements** - Prevents SQL Injection
✅ **Password Hashing** - Uses PHP `password_hash()` & `password_verify()`
✅ **Session Management** - Secure PHP sessions
✅ **HTML Entity Encoding** - Prevents XSS attacks
✅ **Role-Based Access Control** - Admin/User separation
✅ **HTTPS Ready** - Can be deployed with SSL

---

## 📚 Usage Flow

```
1. User visits: localhost/powder_house/login.php
2. Enters email & password
3. System checks in database
4. If valid → Session created
5. If Admin → Redirect to admin-dashboard.php
6. If User → Redirect to user-dashboard.php
7. Click Logout → Session destroyed
```

---

## ⚙️ Configuration

Edit `db.php` if using different database:

```php
$servername = "localhost"; // Your server
$username = "root";         // Your MySQL user
$password = "";             // Your MySQL password
$dbname = "powder_house";   // Your database name
```

---

## 🐛 Troubleshooting

**Q: "Connection failed"**
- ✅ Ensure MySQL is running in XAMPP
- ✅ Check db.php credentials
- ✅ Verify `powder_house` database exists

**Q: "Invalid email or password"**
- ✅ Check users table exists
- ✅ Verify demo data was inserted
- ✅ Use correct credentials: admin@powder.com / admin123

**Q: "Cannot access admin dashboard"**
- ✅ Check session_start() is at top of files
- ✅ Verify user role in database is 'admin'
- ✅ Clear browser cookies

---

## 🔄 Next Steps

1. ✅ Customize login page styling
2. ✅ Add password reset functionality
3. ✅ Implement email verification
4. ✅ Create user registration form
5. ✅ Add product management pages
6. ✅ Integrate shopping cart

---

## 📦 Download & Install

### Option 1: Git Clone
```bash
git clone https://github.com/omkarsainath/powder-house-login-system.git
cd powder-house-login-system
```

### Option 2: Download ZIP
1. Click **Code** → **Download ZIP**
2. Extract to `C:\xampp\htdocs\powder_house\`

### Option 3: Manual Copy
Copy individual PHP files from this repository to your XAMPP folder.

---

## 📞 Support

For issues or questions:
1. Check troubleshooting section above
2. Review code comments in PHP files
3. Create an issue in this repository

---

## 📄 License

Free to use for personal and commercial projects.

---

**Built with ❤️ for Powder House E-commerce**

🌐 Repository: https://github.com/omkarsainath/powder-house-login-system

📧 Contact: omkarsainath.n@gmail.com
