# **Capstone-SDI28-SupraDev**

## **Problem Statement**  
There is currently no formal site used to request application creation/development services from Supra Coders or other entities within the USSF.

---

## **Project Name**  
**SupraDev App - Capstone**

## **Team Name**  
**OMEGA FALCON EAGLE SQUADRON**

---

## **Description**  
SupraDev is a full-stack application consisting of a database, backend, and frontend. It serves as a platform for Supra Coders to create, manage, and track projects while maintaining a repository of all previously developed applications.

---

## **New Features and Updates**  

1. **Login and Authentication**:  
   - Moved login and authentication functionality from the frontend to the backend for improved security.  
   - Added confirmation messages for successful logins.  

2. **Bug Fixes**:  
   - Performed a comprehensive bug extermination and code optimization sweep across both old and new code.  

3. **User Account Management**:  
   - Modified the **POST** routing for user creation.  
   - Prevented duplicate usernames during account registration.  
   - Added the ability for users to create accounts with improved validation.  

4. **Roles and Privileges**:  
   - Enforced roles and privileges: **Admin**, **SupraCoder**, and **General Users** for future scalability.  

5. **Routing Improvements**:  
   - Reworked backend routing to improve security, functionality, and scalability.  

6. **Milestone Features**:  
   - Added a **Milestone Status Bar** and **Milestone Status Page** for easier tracking of project progress.  

7. **GUI and Functionality Enhancements**:  
   - Improved functionality and design of the **Home Page** and **Profile Pages**.  
   - Updated the **Project Submission Page** with enhanced functionality and user experience.  

8. **Database Updates**:  
   - Updated database **seeding** and **migrations** to reflect new features.  

---

## **Prerequisites**  
Before running this project, ensure the following tools and software are installed:  

- [Docker](https://www.docker.com/)  
- [VSCode](https://code.visualstudio.com/)  
- Google Chrome Browser  
- GitHub Access (internet required)  

---

## **Getting Started**  

### **1. Clone the Repository**  
Run the following command:  
```bash
git clone git@github.com:jsanders36/Capstone-SDI18-SupraDev.git
cd Capstone-SDI18-SupraDev
```

### **2. Backend Setup**  
1. Open the project in VSCode:  
   ```bash
   code .
   ```
2. Open a terminal in VSCode:  
   ```bash
   ctrl/command + shift + J
   ```
3. Navigate to the backend folder:  
   ```bash
   cd api
   ```
4. Install dependencies:  
   ```bash
   npm install
   ```
5. Ensure Docker is running:  
   ```bash
   docker --version
   ```
6. Start a PostgreSQL container:  
   ```bash
   docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres
   ```
7. Create the database:  
   ```bash
   docker exec -it [ContainerID] bash
   psql -U postgres
   CREATE DATABASE supradb;
   ```

8. Run migrations and seed the database:  
   ```bash
   cd api
   npx knex migrate:latest
   npx knex seed:run
   ```
9. Start the backend server:  
   ```bash
   npm start
   ```

---

### **3. Frontend Setup**  
1. Open a new terminal and navigate to the frontend:  
   ```bash
   cd ui
   ```
2. Install dependencies:  
   ```bash
   npm install
   ```
3. Start the frontend:  
   ```bash
   npm start
   ```
4. Open the application in your browser:  
   ```
   http://localhost:3000
   ```

---

## **Testing**  

### **Backend API Testing**  
1. A test database, `supradb_test`, is used for testing.  
2. Ensure the `pg-docker` container is running.  
3. Create the test database using:  
   ```bash
   sudo bash ./test/supradb_test_create.sh supradb_test pg-docker
   ```
4. Run tests with Jest:  
   ```bash
   npm test
   ```
5. After testing, destroy the test database:  
   ```bash
   sudo bash ./test/supradb_test_destroy.sh supradb_test pg-docker
   ```

---

## **Troubleshooting**  
If you encounter **PostgreSQL version conflicts**, specify the version when running the container:  
```bash
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql@15/data postgres
```
Ensure the correct version matches your existing data directory.

---

## **Future Updates**  
- Additional improvements to security, user roles, and milestone features.  
- Enhanced functionality for project tracking and reporting.  

---

## **Contributors**  
- Team: **OMEGA FALCON EAGLE SQUADRON**  

---

Let me know if you need further edits or formatting adjustments! 🚀
