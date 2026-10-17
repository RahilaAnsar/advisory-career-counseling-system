# ACCS – Advisory and Career Counseling System

Bachelor's final-year project (Senior Design Project, IT400) — **BS Information Technology, International Islamic University Islamabad (IIUI), 2019**.

**Authors:** Rahila Ansar (78-FBAS/BSIT4/F15) and Sadaf Idrees (42-FBAS/BSIT4/F15)
**Supervisor:** Dr. Usman Nasir, Department of Computer Science, Software Engineering & IT, IIUI

## What it does

A web application that moves academic advising and career counselling at a university from manual, in-person processes to an online platform.
Three roles:

| Role | Main functions |
|---|---|
| **Administrator** | manage students, counselors, courses/subjects, results, news and scholarships; search and reporting |
| **Counselor** | profile, dashboard, student reviews/ratings, messaging with students |
| **Student** | registration/login, course registration, results, counselor list, ratings/feedback, scholarship info, chatbot help |

Modules implemented: administrator panel, counselor portal, student portal, course registration, results, user registration, help (chatbot), communication channel, notifications (e-mail), feedback/ratings, search, report generation, scholarships.

## Tech stack

* PHP 7 (procedural, `mysqli`), MySQL/MariaDB, HTML5, CSS3, JavaScript/jQuery
* XAMPP (Apache + MySQL) as local server
* Third-party components (not written by us): [AdminLTE](https://adminlte.io/) admin template and its `bower_components`, [PHPMailer 5.2](https://github.com/PHPMailer/PHPMailer), [BotMan](https://botman.io/) web driver for the help chatbot

## Where our own code is

```
/*.php                      student & counselor portals (login, dashboard, profile, courses, results, password, reviews)
/includes/                  DB connection, shared header/sidebar/footer
/admin/*.php                admin panel pages (add/edit/show students, counselors, courses, results, news, scholarships; search)
/admin/includes/            admin auth + helper functions
/botman.php, chat.js        help chatbot
/accs.sql                   database schema + sample data (9 tables)
```
Everything under `admin/bower_components`, `admin/dist`, `admin/plugins` and `admin/PHPMailer-5.2.25` is third-party.

## Run locally

1. Install XAMPP, start Apache and MySQL.
2. Copy this folder to `htdocs/accs`.
3. Create a database named `accs` and import `accs.sql` (phpMyAdmin).
4. DB connection defaults: `localhost`, user `root`, empty password (see `includes/connection.php`).
5. Optional e-mail notifications: set environment variables `ACCS_SMTP_USER` / `ACCS_SMTP_PASS` (Gmail SMTP, port 587 TLS). No credentials are stored in the repository.
6. Open `http://localhost/accs/` (student/counselor) or `http://localhost/accs/admin/login.php` (admin — sample login `admin` / `admin`).

## Notes

* 2019 student project, published unchanged apart from removing credentials and test files. It uses MD5 password hashing and string-built SQL, which we would replace today with `password_hash()` and prepared statements.
* Full project report (SRS, ER diagram, design, testing) is available on request.
