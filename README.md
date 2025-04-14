# Dima Chat Support System

A lightweight and efficient chat support system built with **PHP**, **MySQL**, **Bootstrap**, and **jQuery**. This project is designed to provide a seamless chat experience for customers and administrators, with features like real-time messaging, admin panel, pagination, and security measures.

## Table of Contents
1. [Features](#features)
2. [Installation](#installation)
3. [Configuration](#configuration)
4. [Usage](#usage)
5. [Security Measures](#security-measures)
6. [Contributing](#contributing)
7. [License](#license)

---

## Features

- **Customer Chat**: Customers can send messages to the support team.
- **Admin Panel**: Administrators can view and respond to customer messages.
- **Real-Time Messaging**: Messages are displayed instantly using AJAX (WebSocket integration can be added later).
- **Pagination**: Efficiently manage large numbers of chats with pagination.
- **Secure Authentication**: Includes login, registration, and role-based access control (Admin/Customer).
- **CSRF Protection**: Protects against Cross-Site Request Forgery attacks.
- **Input Validation**: Prevents SQL Injection and XSS attacks.
- **Error Logging**: Logs errors for debugging purposes.
- **Responsive Design**: Built with Bootstrap for a mobile-friendly interface.

---

## Installation

### Prerequisites
Before you begin, ensure you have the following installed:
- PHP >= 7.4
- MySQL
- A web server (e.g., Apache or Nginx)
- Composer (optional, if you plan to add dependencies later)

### Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/chat-support.git
   cd chat-support
   ```

2. **Set Up the Database**
   - Import the database schema from `chat_support.sql` into your MySQL server.
     ```sql
     CREATE DATABASE chat_support;
     USE chat_support;

     -- Run the SQL queries from the provided file.
     ```
   - Update the database connection details in `includes/db.php`.

3. **Configure Environment**
   - Open `includes/db.php` and update the database credentials:
     ```php
     $host = 'localhost';
     $dbname = 'chat_support';
     $username = 'your_db_username';
     $password = 'your_db_password';
     ```

4. **Run the Application**
   - Place the project files in your web server's root directory (e.g., `/var/www/html` for Apache).
   - Start your web server and navigate to `http://localhost/chat-support`.

---

## Configuration

### Admin Account
To create an admin account, insert a new user into the `users` table with the `role` set to `'admin'`:
```sql
INSERT INTO users (username, email, password, role) 
VALUES ('admin', 'admin@example.com', '$2y$10$hashedpassword', 'admin');
```
Replace `$2y$10$hashedpassword` with a hashed password generated using `password_hash()`.

### CSRF Token
The system uses CSRF tokens for security. Ensure that `session_start()` is called at the beginning of every PHP script.

---

## Usage

### Customer Side
1. Register or log in as a customer.
2. Send messages to the support team.
3. View responses from the admin in real-time.

### Admin Side
1. Log in as an admin.
2. Navigate to the admin panel to view and respond to customer messages.
3. Use the pagination feature to manage large numbers of chats.

---

## Security Measures

1. **CSRF Protection**: Each form includes a CSRF token to prevent unauthorized requests.
2. **Password Hashing**: Passwords are securely hashed using `password_hash()`.
3. **Input Validation**: All user inputs are sanitized and validated to prevent SQL Injection and XSS attacks.
4. **Error Logging**: Errors are logged to a file (`/var/log/chat_support.log`) for debugging purposes.
5. **HTTPS**: Always use HTTPS in production to encrypt data in transit.

---

## Contributing

We welcome contributions from the community! Here’s how you can help:

1. **Report Issues**: If you encounter any bugs or issues, please open an issue on GitHub.
2. **Submit Pull Requests**: Feel free to fork the repository, make changes, and submit a pull request.
3. **Feature Requests**: Suggest new features or improvements by opening an issue.

### Code Style
- Follow PSR standards for PHP code.
- Use meaningful commit messages.

---

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Thanks to the open-source community for providing tools and libraries like Bootstrap, jQuery, and PHP.
- Special thanks to everyone who contributes to this project.

---

## Contact

If you have any questions or need further assistance, feel free to reach out:

- Email: [r.balvardi@gmail.com](mailto:r.balvardi@gmail.com)
- GitHub: [@balvardi](https://github.com/balvardi)

---

### Final Notes

This project is designed to be simple yet powerful. It can be extended with additional features like WebSocket for real-time communication, file uploads, or multi-language support. Contributions and feedback are highly appreciated!

Happy coding! 🚀

---

