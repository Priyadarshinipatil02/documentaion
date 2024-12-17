# To get started with setting up the Java backend for your project

# Contents

1. [Running a Maven Spring Boot Project](#running-a-maven-spring-boot-project)
   - [Prerequisites](#prerequisites)
   - [Steps to Run the Project](#steps-to-run-the-project)
     - [Clone or Download the Project](#clone-or-download-the-project)
     - [Build the Project](#build-the-project)
     - [Run the Application](#run-the-application)
     - [Access the Application](#access-the-application)
2. [Test API Using Postman](#test-api-using-postman)
3. [Troubleshooting](#troubleshooting)

---

## Running a Maven Spring Boot Project

### Prerequisites

1. **Install Java**: Ensure Java Development Kit (JDK) is installed (version 8 or above).
2. **Install Maven**: Verify Apache Maven is installed and configured in your system's `PATH`.
3. **Environment Variables**: Ensure `JAVA_HOME` and `MAVEN_HOME` are properly set.

## Steps to Run the Project

1. **Clone or Download the Project:**

   ```bash
   git clone <repository-url>
   cd <project-directory>/BackEnd
   ```

2. Add Environment Variable(.env) file in BackEnd.



3. **Build the Project:**
   Use the Maven `clean` and `install` commands to build the project.

   ```bash
   mvn clean install
   ```

4. **Run the Application:**
   Use the Maven `spring-boot:run` command to start the application.

   ```bash
   mvn spring-boot:run
   ```

5. **Access the Application:**
   By default, the application runs on `http://localhost:8080`. Check your application.properties or configuration for the exact port.

## Test API Using Postman
Postman API Collection: https://arrk44.postman.co/workspace/Arrk-Workspace~f53ded6c-ef1e-48e5-84a2-0ff38258d730/collection/39217044-36f3e603-8fee-4eff-854c-1818425827f4?action=share&source=copy-link&creator=39217044

## Troubleshooting

- Ensure no other application is using the configured port.
- Check logs for errors during startup using:
  ```bash
  mvn spring-boot:run
  ```
- If dependencies are missing, try running:
  ```bash
  mvn dependency:resolve
  ```


---



# To get started with backend features in your Java application

# Contents

1. [Add Customer](#add-customer)
2. [Add User / Signup](#add-user-signup)
3. [Sign In / Login](#sign-in-login)
4. [Edit / Delete Customer](#edit-delete-customer)
5. [Search and Sort Users](#search-and-sort-users)
6. [Get Users](#get-users)
7. [Analytics](#analytics)
8. [Total Customers](#total-customers)
9. [Active Now](#active-now)
10. [Users](#users)
11. [Number of Clicks](#number-of-clicks)
12. [Revenue Overview](#revenue-overview)
13. [New Licenses](#new-licenses)
14. [All Customer Details - Cost Analytics](#all-customer-details-cost-analytics)
15. [Yearly/Monthly/Fixed Chart](#yearlymonthlyfixed-chart)
16. [EC2 Unit Cost - Resource Analytics](#ec2-unit-cost-resource-analytics)

---

## <a id="add-customer"></a>Add Customer
1. In addition to the **customer's company name**, a **list of domains** and a **list of apps** the customer wants to use will be added.
2. Once the company is registered with us:
   - A **user** with the following details must be added:
     - Name
     - Email
     - Role
     - Apps
3. Only users with the **ARRKADMIN** role can add customers.

---

## <a id="add-user-signup"></a>Add User / Signup
1. Once a customer has been registered with ARRK:
   - **ARRKADMIN** or **EXTADMIN** can add more users to that company.

2. When a user is added by an admin:
   - The user will receive a **reset password email**.
   - The user can click on the link in the email to reset their password.

3. After resetting their password:
   - The user will be able to log in with their new credentials.

4. Reset Password Link:
   - The reset password link sent to the user will be valid for **3 hours**.
   - If the reset link expires, the user must contact their respective admin to request another reset password email.

5. User Limit for EXTADMIN:
   - **EXTADMIN** can add up to **100 users** under their company.

---

## <a id="sign-in-login"></a>Sign In / Login
1. **Registered Users**:  
   - Users who are registered with ARRK can log in using their credentials.

2. **Login Validation**:  
   - If the user details are correct, they will be able to log in successfully.  
   - Otherwise, they will receive appropriate response messages.

3. **Forgot Password**:  
   - If a user does not remember their password, they can submit a **forgot password request**.  
   - The user will receive an email with a link to reset their password.  
   - The **verification code** in the reset link will be valid for **3 hours** only.

---

## <a id="edit-delete-customer"></a>Edit / Delete Customer
1. **ARRKADMIN Privileges**:
   - Only **ARRKADMIN** can edit the customers registered with ARRK.

2. **Update Apps**:
   - **ARRKADMIN** can update the apps associated with the companies.

3. **App Access Management**:
   - **ARRKADMIN** can grant access to any app for any particular user within the company.
   - **ARRKADMIN** can remove access to any app for any company or user.

4. **Customer Deletion**:
   - **ARRKADMIN** can delete any customer.  
   - Deleting a customer will also remove all associated company details, including:
     - Licensed apps
     - All users
   - All customer data will be deleted from the ARRK database.

5. **ARRKADMIN Restrictions**:
   - **ARRKADMIN** cannot delete another **ARRKADMIN**.

---

## <a id="search-and-sort-users"></a>Search and Sort Users
1. **ARRKADMIN Privileges**:
   - **ARRKADMIN** can search for any user based on attributes such as:
     - Role
     - Name
     - Company
     - Email
     - And other relevant attributes.

2. **EXTADMIN Privileges**:
   - **EXTADMIN** can search users based on the same attributes but only within their own company.

3. **Sorting Users**:
   - Users can be sorted in either **ascending** or **descending** order by their **username**.

---

## <a id="get-users"></a>Get Users
1. **User Access for ARRKADMIN and EXTADMIN**:
   - Both **ARRKADMIN** and **EXTADMIN** will be able to view users in two views:
     - **User View**
     - **App View**

2. **User View**:
   - In the **User View**, the admin can see:
     - Which user is using which app.
     - The company to which the particular user belongs.
     - The user's role.
   - For **EXTADMIN**, this view will be limited to users within their own company.

3. **App View**:
   - In the **App View**, **ARRKADMIN** can see:
     - How many users are using each app.
     - The companies associated with each user.
     - The user rights for each app.
   - For **EXTADMIN**, this view will also be limited to their own company.

4. **App Access Management**:
   - Both **ARRKADMIN** and **EXTADMIN** can grant or remove app access for users.

---

## <a id="analytics"></a>Analytics
In the **Analytics** section, the following features are available:

1. **Total Customers**:
   - Displays the total number of customers registered with ARRK.

2. **Users**:
   - Shows the total number of users across all customers.

3. **Active Now**:
   - Displays the number of users who are currently active and logged in.

---

## <a id="total-customers"></a>Total Customers
1. **ARRKADMIN Access**:
   - **ARRKADMIN** will be able to view all the customers registered with ARRK.

---

## <a id="active-now"></a>Active Now
1. **ARRKADMIN Access**:
   - **ARRKADMIN** will be able to see the total number of users currently logged in.

2. **EXTADMIN Access**:
   - **EXTADMIN** will be able to see the number of users currently logged in from their own company only.

---

## <a id="users"></a>Users
1. **ARRKADMIN Access**:
   - **ARRKADMIN** will be able to see the total number of users using ARRK applications across all companies.

2. **EXTADMIN Access**:
   - **EXTADMIN** will be able to see the number of users using ARRK applications, but only for their own company.

---

## <a id="number-of-clicks"></a>Number of Clicks
1. **ARRKADMIN Access**:
   - **ARRKADMIN** will be able to see how many times ARRK iframe apps have been clicked.
   - **ARRKADMIN** can also view the number of clicks for each month, showing monthly click data.

---

## <a id="revenue-overview"></a>Revenue Overview
1. **ARRKADMIN Access**:
   - **ARRKADMIN** will be able to see the total revenue generated in the current year.
   - **ARRKADMIN** can also view the revenue for any specific month.
   - Revenue is calculated based on **monthly** and **yearly** licenses only.

---

## <a id="new-licenses"></a>New Licenses
1. **ARRKADMIN Access**:
   - **ARRKADMIN** will be able to see how many new licenses have been issued in the current month.

---

## <a id="all-customer-details-cost-analytics"></a>All Customer Details - Cost Analytics
1. **ARRKADMIN Access**:
   - In **Cost Analytics**, **ARRKADMIN** will be able to see all the details of all customers, including:
     - **License Type**
     - **Expiration Date** of the license
     - **License Model** the customer is using
     - **Number of Users** associated with the customer
     - **List of EXTADMIN details** for the customer's company

---

## <a id="yearlymonthlyfixed-chart"></a>Yearly/Monthly/Fixed Chart
1. **ARRKADMIN Access**:
   - In this feature, **ARRKADMIN** will be able to see:
     - Which customer is using which license model the most (**Yearly**, **Monthly**, or **Fixed**).
     - The number of users using each type of license model.

---

## <a id="ec2-unit-cost-resource-analytics"></a>EC2 Unit Cost - Resource Analytics
1. **ARRKADMIN Access**:
   - In **Resource Analytics**, **ARRKADMIN** will be able to see:
     - The total AWS cost generated for a particular month.
     - The cost breakdown for each day within the selected month.

2. **EXTADMIN Access**:
   - **EXTADMIN** can see resource analytics only for their respective company.

---
