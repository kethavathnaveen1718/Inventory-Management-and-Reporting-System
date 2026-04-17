# Inventory Management and Reporting System

A comprehensive full-stack inventory solution built with a secure Spring Boot REST API and a dynamic React frontend. This system delivers role-based access control, real-time stock monitoring, automated low-stock email alerts, and analytical insights.

**Developed by Kethavath Naveen**

---

## 🚀 Features

### Backend (Spring Boot)
- **JWT Authentication:** Stateless security using JJWT with secure token management.
- **Role-Based Access Control:** Protects endpoints based on `ADMIN`, `STAFF`, and `CUSTOMER` roles.
- **Automated Low-Stock Alerts:** Automatically scans inventory and dispatches SMTP email alerts to admins when items drop below reorder levels.
- **Product Management:** Full CRUD functionality with both soft deletion (deactivation) and permanent removal.
- **Stock Handling:** Secure and controlled inventory reduction/increase endpoints.

### Frontend (React)
- **Interactive Dashboard:** Displays key performance indicators, inventory value, and dynamic charts.
- **Product Management Interface:** Searchable, filterable tables with inline editing.
- **Theme Support:** Persistent dark/light mode using local storage.
- **Role Enforcement:** The user interface adapts dynamically based on user permissions (e.g., hiding sensitive buttons from customers).
- **Notification System:** Toast-based alerts for system feedback and real-time warnings.

---

## 💻 Tech Stack

**Backend:**
- Java 21
- Spring Boot 3.2.5
- Spring Security + JWT
- Hibernate + Spring Data JPA
- MySQL 8
- Jakarta Mail (SMTP)
- Maven

**Frontend:**
- React 18
- React Router v6
- Axios
- Custom CSS (Variables & Theming)

---

## 🛠️ Getting Started

### Prerequisites
- **Java 21**
- **Node.js**
- **MySQL Server**
- **Maven**

### 1. Database Setup
Create the MySQL database:
```sql
CREATE DATABASE stockmanagement;
```

### 2. Backend Setup
Navigate to the backend directory, ensure your MySQL credentials match in `application.properties`, and run the Spring Boot application:
```bash
cd backend
./mvnw spring-boot:run "-Dmaven.test.skip=true"
```
The API will start on `http://localhost:8080`.

### 3. Frontend Setup
Navigate to the frontend directory, install the dependencies, and start the React development server:
```bash
cd frontend
npm install
npm start
```
The React app will open automatically on `http://localhost:3000`.

---

## 🛡️ Security & Roles

| Action | CUSTOMER | STAFF | ADMIN |
|---|:---:|:---:|:---:|
| View Dashboard & Reports | ✓ | ✓ | ✓ |
| Add / Edit Products | ✗ | ✓ | ✓ |
| Trigger Email Alerts | ✗ | ✓ | ✓ |
| Delete Products | ✗ | ✗ | ✓ |

---

## 📧 Email Configuration
To enable the automated low-stock email alerts:
1. Open `backend/src/main/java/com/inventory/Report/EmailService.java`.
2. Update the `username` with your sender Gmail address.
3. Update the `password` with a **16-character Gmail App Password** (Generated via Google Account -> Security -> 2-Step Verification).
4. Update the receiver email address in `InventoryReportService.java`.

---

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
