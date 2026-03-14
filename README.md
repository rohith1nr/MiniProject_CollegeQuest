# 🎓 CollegeQuest — College Information Website

CollegeQuest is a static college information website built as a mini project. It provides a comprehensive front-end interface for a college, featuring announcements, events, campus news, alumni testimonials, a photo gallery, placement recruiters, and a student/faculty login portal backed by a PHP–MySQL backend.

---

## 📁 Project Structure

```
MiniProject_CollegeQuest-main/
│
├── index.html        # Main homepage of the website
├── style.css         # Stylesheet for the homepage
├── login.html        # Student / Faculty login page
├── login.css         # Stylesheet for the login page
├── login.php         # PHP backend for handling login form submission
│
├── images/           # All image assets used across the site
│   ├── logo.png
│   ├── naac.jpg
│   ├── nba.png
│   ├── g1.jpg – g8.jpg       (Gallery images)
│   ├── r1.jpeg – r10.jpeg    (Recruiter logos)
│   ├── placement/            (Placement event photos)
│   └── ...
│
└── img/              # Additional icon assets
    ├── lock-icon.png
    └── user-icon.png
```

---

## ✨ Features

- **Announcement Banner** — Scrolling marquee for real-time college announcements.
- **Navigation Bar** — Links to Home, Search, Contact, Student Login, Faculty Login, Placements, Research & Development, and Exam Branch.
- **Event Slider** — Prominent image banner at the top of the homepage.
- **Recent Events** — Auto-scrolling list of dated campus events and notices.
- **Campus News** — Section highlighting notable college happenings.
- **College Event Calendar** — Key dates such as Orientation Day, Fresher Day, Cultural Fests, Alumni Meet, and Annual Day.
- **About Us** — Overview of the college's philosophy and values.
- **Chairman & Principal Section** — Profiles of college leadership.
- **Mission Statement** — College's educational mission and goals.
- **Alumni Testimonials** — Quotes and ratings from former students.
- **Photo Gallery** — A grid of campus images.
- **Top Recruiters** — Auto-scrolling marquee of company logos.
- **Login Portal** — Email/password form for students and faculty, connected to a MySQL database via PHP.
- **Footer** — Contact details, address, social media links, and site navigation.

---

## 🛠️ Tech Stack

| Layer       | Technology          |
|-------------|---------------------|
| Markup      | HTML5               |
| Styling     | CSS3                |
| Icons       | Font Awesome        |
| Backend     | PHP                 |
| Database    | MySQL (via MySQLi)  |

---

## ⚙️ Setup & Installation

### Prerequisites

- A local web server with PHP support (e.g., [XAMPP](https://www.apachefriends.org/), [WAMP](https://www.wampserver.com/), or [LAMP](https://ubuntu.com/server/docs/lamp-applications))
- MySQL database

### Steps

1. **Clone or download** the repository and place it in your server's root directory (e.g., `htdocs/` for XAMPP).

2. **Create the database** in MySQL:
   ```sql
   CREATE DATABASE `student login`;

   USE `student login`;

   CREATE TABLE users (
     id INT AUTO_INCREMENT PRIMARY KEY,
     email VARCHAR(255) NOT NULL,
     password VARCHAR(255) NOT NULL
   );
   ```

3. **Configure `login.php`** with your database credentials:
   ```php
   $servername = "localhost";   // e.g., localhost
   $username   = "root";        // your MySQL username
   $password   = "yourpassword"; // your MySQL password
   $database   = "student login";
   ```

4. **Start your local server** and navigate to:
   ```
   http://localhost/MiniProject_CollegeQuest-main/index.html
   ```

---

## 🔐 Login Page

The login form (`login.html`) collects an email and password, then submits via `POST` to `login.php`, which stores the credentials in the MySQL `users` table.

> ⚠️ **Security Note:** The current implementation stores passwords in **plain text** and uses raw SQL queries, making it vulnerable to SQL injection. Before deploying to production, it is strongly recommended to:
> - Hash passwords using `password_hash()` / `password_verify()`
> - Use **prepared statements** with parameterized queries to prevent SQL injection
> - Implement proper session management for authenticated users

---

## 📸 Assets

- **Gallery images** (`g1.jpg` – `g8.jpg`): Campus photographs displayed in the gallery grid.
- **Recruiter logos** (`r1.jpeg` – `r10.jpeg`): Company logos shown in the placement marquee.
- **Accreditation logos**: NAAC and NBA badge images displayed in the header.
- **Social media icons**: Facebook, Twitter, Instagram, and LinkedIn icons in the footer.

---

## 🚧 Known Issues & Limitations

- Navigation links (Search, Contact, Placements, R&D, Exam Branch) are placeholder `#` links and not yet implemented.
- Login links in the navbar use absolute local file paths (`file:///C:/Users/...`) that need to be updated to relative paths for portability.
- The login system currently lacks authentication logic — it only stores submitted credentials and does not verify them against existing records.
- No responsive/mobile design has been implemented.

---

## 🔮 Future Enhancements

- Add full authentication with session management
- Make all navigation links functional with dedicated pages
- Implement a search feature for courses and departments
- Add a responsive layout for mobile devices
- Build a dynamic admin panel for managing events and news
- Integrate a proper placement portal with student profiles

---

## 👤 Author

**Rohith Nagapuri**  
Mini Project — College Website Development  
📧 info@CollegeQuest.com

---

## 📄 License

This project is intended for educational purposes. No license has been specified.
