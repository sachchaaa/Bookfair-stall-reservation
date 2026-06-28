# 📚 Colombo International Book Fair 2026 Reservation System

![Book Fair Banner](https://placehold.co/1200x400/2563eb/ffffff?text=Colombo+International+Book+Fair+2026)

## 📖 Project Overview
The **Colombo International Book Fair 2026 Reservation System** is a modern, high-performance web application designed to streamline the vendor stall booking process. Built with a robust React frontend and a secure Spring Boot backend, the system enables an efficient, gamified checkout experience with real-time concurrency handling and role-based access control.

## 🚀 Key Features
- **Role-Based Access Control (RBAC):** Secure entry portals for Vendors and Administrators to ensure privilege isolation.
- **Optimistic Locking (Concurrency):** Prevents double-booking of stalls during high-traffic burst events.
- **Dynamic QR Code Ticketing:** Generates unique, verifiable QR tickets for booked stalls to simplify physical entry and validation.
- **Gamified Checkout Experience:** An engaging and intuitive reservation flow to optimize conversion rates for vendors.

## 💻 Tech Stack
- **Frontend:** React, Vite, Tailwind CSS
- **Backend:** Java, Spring Boot, Spring Data JPA
- **Security:** Spring Security with JSON Web Tokens (JWT)
- **Database:** MySQL

## 🛠️ Local Setup Instructions

Follow these instructions to run the application locally for evaluation or development.

### 1. Prerequisites
- Java 17+
- Maven 3.8+
- Node.js 18+
- MySQL Server 8.0+

### 2. Backend Setup (Java / Spring Boot)
1. Navigate to the `backend` directory:
   ```bash
   cd backend
   ```
2. **Create the Database:** Create a MySQL database named `bookfair_db`.
3. **Configure Properties:** Create a local `application.properties` (or `application-dev.properties` if using profiles) inside `src/main/resources/` with the following configuration to generate tables on the initial run:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/bookfair_db
   spring.datasource.username=root
   spring.datasource.password=your_mysql_password
   
   # Automatically create/update the schema based on entities
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
   
   # JWT Configuration
   jwt.secret=your_super_secret_jwt_key_that_is_at_least_256_bits_long
   
   # Gmail SMTP for notifications
   spring.mail.host=smtp.gmail.com
   spring.mail.port=587
   spring.mail.username=your_gmail_address
   spring.mail.password=your_gmail_app_password
   ```
4. **Run the Backend:**
   ```bash
   mvn spring-boot:run
   ```
   The backend will normally run on `http://localhost:8080`.

### 3. Frontend Setup (React / Vite)
1. Open a new terminal and navigate to the `frontend` directory:
   ```bash
   cd frontend
   ```
2. **Install Dependencies:**
   ```bash
   npm install
   ```
3. **Configure Environment Variables:** Create a `.env` file in the root of the `frontend` directory and define your API URL:
   ```env
   VITE_API_BASE_URL=http://localhost:8080/api/v1
   ```
4. **Run the Development Server:**
   ```bash
   npm run dev
   ```
   The frontend will be accessible at `http://localhost:5173`.

## 🔑 Default Credentials for Evaluators
To immediately test the RBAC capabilities and system flows, you can log in using the following demonstrative credentials (ensure you run the DB seed script if applicable):

**Administrator Portal:**
- **Email:** `admin@bookfair.lk`
- **Password:** `AdminSecure2026!`

**Vendor Portal:**
- **Email:** `vendor_demo@bookfair.lk`
- **Password:** `VendorDemo2026!`
