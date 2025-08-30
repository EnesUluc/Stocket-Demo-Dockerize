# Stocket Demo

## ✨⬆️ How to Start the System
1- Start the system with Docker Compose
* docker compose up ---build

2- Add the default admin user
* docker exec -it mysqldb bash
  * mysql -uspringstudent -pspringstudent

      2.1 - Select the database
      * use stocket_db;
    
      2.2 - Add the default admin
      * INSERT INTO user (created_at, enabled, password, username, authorities)
        VALUES (NOW(), true, '$2a$10$XleMszcy2MZN040TMSnGC.mBpEKj81ZwNo9/V.WxcZVMsJzhfqZAW', 'admin', 'ROLE_ADMIN');

      2.3 - Check the database
      - select * from user;
      
3- Access the application
* Visit: localhost:8080 
  * username: admin  && password: 1313    

### User Side

A simple yet effective **e-commerce demo application** built to enhance my skills in **Spring Boot, Thymeleaf, JPA, Redis, and Database management**. The project demonstrates a dynamic and functional e-commerce system with both **user-facing features** and an **admin/manager control panel**.

---

## 🚀 Features

### User Side

* **Category browsing**: Users can select categories and view the products inside.
* **Shopping cart with Redis**: Add, remove, increase or decrease products in the cart. Cart state is managed using Redis (port 6379).
* **Account management**:

  * Update personal details.
  * Delete account (with confirmation email notification).
  * Register a new account with input validation patterns.
  * Email verification link sent upon registration (expires in 5 minutes). If not confirmed, account is deleted and a notification email is sent.
* **Login & Security**: Users cannot log in unless their account is activated.

### Admin/Manager Panel

* **User management**: Admins can add new admins and managers.
* **Category management**: Create new categories.
* **Product management**: Add, update, and manage products dynamically (reflected immediately on user and cart views).
* **Dashboard & Analytics**:

  * Total users, active users, new registrations.
  * Category-based product statistics.
  * Graph showing active vs total users.

### Technical Features

* **Spring Boot & Spring Security**: Secure authentication and role-based access control.
* **Thymeleaf**: Dynamic UI rendering.
* **JPA & DTO Design Pattern**: Database interaction and clean data handling.
* **Redis**: High-performance in-memory shopping cart system.
* **AOP (Aspect-Oriented Programming)**: Logging for better debugging and error detection.
* **Email Notifications**: For account verification and deletion alerts.

---

## 🛠 Tech Stack

* **Backend**: Spring Boot, Spring Security, JPA, AOP
* **Frontend**: Thymeleaf
* **Database**: MySQL (or any relational DB)
* **Cache**: Redis (port 6379)
* **Other**: DTO, Logging

---

## ⚙️ Installation & Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/stocket-demo.git
   cd stocket-demo
   ```

2. Configure your database settings in `application.properties`.

3. Start Redis server on port **6379**:

   ```bash
   redis-server
   ```

4. Run the Spring Boot application:

   ```bash
   mvn spring-boot:run
   ```

5. Open in browser:

   ```
   http://localhost:8080
   ```

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## 📜 License

This project is licensed under the MIT License.

---

💡 This project is part of my learning journey to improve full-stack development skills.
