
# Backend API Documentation

---

## Authentication and Authorization APIs

- **Login**  
  **Endpoint**: `/auth/signin`  
  **Method**: `POST`  
  **Purpose**: Authenticates a user and issues a JWT token.

- **Signup**  
  **Endpoint**: `/auth/signup`  
  **Method**: `POST`  
  **Purpose**: Registers a new user.

- **Confirm Signup**  
  **Endpoint**: `/auth/confirm-firsttime-signup`  
  **Method**: `POST`  
  **Purpose**: Verifies the user’s email during the initial signup process.

- **Send Password Reset Link**  
  **Endpoint**: `/adminuser/send-reset-link`  
  **Method**: `POST`  
  **Purpose**: Sends a link to reset the user’s password.

- **Resend Link**  
  **Endpoint**: `/adminuser/resend`  
  **Method**: `POST`  
  **Purpose**: Resends a previously generated link.

- **Reset Password**  
  **Endpoint**: `/auth/reset-password`  
  **Method**: `POST`  
  **Purpose**: Resets the user’s password.

- **Send Forgot Password Code**  
  **Endpoint**: `/auth/forgot-password`  
  **Method**: `POST`  
  **Purpose**: Sends a code for password reset.

- **Send Forgot Password Code (Cognito)**  
  **Endpoint**: `/auth/forgot-password/cognito`  
  **Method**: `POST`  
  **Purpose**: Sends a password reset code via AWS Cognito.

- **Verify Forgot Password Code**  
  **Endpoint**: `/auth/validate-forgot-password`  
  **Method**: `POST`  
  **Purpose**: Validates the code sent for password reset.

- **Validate OTP**  
  **Endpoint**: `/auth/validate-otp`  
  **Method**: `POST`  
  **Purpose**: Validates a one-time password (OTP).

- **Logout**  
  **Endpoint**: `/auth/logout`  
  **Method**: `POST`  
  **Purpose**: Logs the user out and invalidates the session.

- **Logout on Tab Close**  
  **Endpoint**: `/auth/logout-on-tab-close`  
  **Method**: `POST`  
  **Purpose**: Logs the user out automatically when the browser tab is closed.

- **Contact Form Submission**  
  **Endpoint**: `/auth/contactform`  
  **Method**: `POST`  
  **Purpose**: Submits a contact form for user inquiries.

---

## ARRK Admin APIs

- **Get All Users**  
  **Endpoint**: `/arrkadmin/users`  
  **Method**: `GET`  
  **Purpose**: Fetches a list of all users managed by ARRK Admin.

- **Add User**  
  **Endpoint**: `/arrkadmin/addUser`  
  **Method**: `POST`  
  **Purpose**: Adds a new user to ARRK Admin.

- **Edit User**  
  **Endpoint**: `/arrkadmin/users`  
  **Method**: `PUT`  
  **Purpose**: Edits user information in ARRK Admin.

- **Delete User**  
  **Endpoint**: `/arrkadmin/delete/user`  
  **Method**: `DELETE`  
  **Purpose**: Deletes a user from ARRK Admin.

- **Search Users**  
  **Endpoint**: `/arrkadmin/users/search`  
  **Method**: `GET`  
  **Purpose**: Searches for users in ARRK Admin.

- **Get Active Users**  
  **Endpoint**: `/arrkadmin/active-users`  
  **Method**: `GET`  
  **Purpose**: Fetches a list of active users in ARRK Admin.

- **User Statistics**  
  **Endpoint**: `/arrkadmin/user-stats`  
  **Method**: `GET`  
  **Purpose**: Retrieves user-related statistics for ARRK Admin.

- **Get All Companies**  
  **Endpoint**: `/arrkadmin/companies`  
  **Method**: `GET`  
  **Purpose**: Fetches a list of all companies managed by ARRK Admin.

- **List Companies**  
  **Endpoint**: `/arrkadmin/companies/list`  
  **Method**: `GET`  
  **Purpose**: Retrieves a simplified list of all companies.

- **Company Details**  
  **Endpoint**: `/arrkadmin/companies/details`  
  **Method**: `GET`  
  **Purpose**: Fetches detailed information about a specific company.

- **Edit Company**  
  **Endpoint**: `/arrkadmin/editcustomer`  
  **Method**: `PUT`  
  **Purpose**: Edits company details in ARRK Admin.

- **Delete Company**  
  **Endpoint**: `/arrkadmin/deletecustomer`  
  **Method**: `DELETE`  
  **Purpose**: Deletes a company from ARRK Admin.

- **Add Customer**  
  **Endpoint**: `/arrkadmin/addcustomer`  
  **Method**: `POST`  
  **Purpose**: Adds a new customer to ARRK Admin.

- **Restore Deleted Customer**  
  **Endpoint**: `/arrkadmin/restore/customer/{customerId}`  
  **Method**: `PUT`  
  **Purpose**: Restores a deleted customer account.

- **Deleted Customers**  
  **Endpoint**: `/arrkadmin/deleted/customers`  
  **Method**: `GET`  
  **Purpose**: Lists all deleted customer records.

- **Get Cost and Usage by Resources**  
  **Endpoint**: `/arrkadmin/fetchCostAndUsageWithResources`  
  **Method**: `GET`  
  **Purpose**: Fetches detailed cost and resource usage data.

- **Revenue Analytics**  
  **Endpoint**: `/arrkadmin/revenue`  
  **Method**: `GET`  
  **Purpose**: Retrieves revenue analytics.

- **Revenue by Years**  
  **Endpoint**: `/arrkadmin/allyears/revenue`  
  **Method**: `GET`  
  **Purpose**: Retrieves revenue data for all available years.

---

## External Admin APIs

- **Get All Users**  
  **Endpoint**: `/extadmin/users`  
  **Method**: `GET`  
  **Purpose**: Fetches a list of all users managed by External Admin.

- **Add User**  
  **Endpoint**: `/extadmin/ExAddUser`  
  **Method**: `POST`  
  **Purpose**: Adds a new user to External Admin.

- **Edit User**  
  **Endpoint**: `/extadmin/users`  
  **Method**: `PUT`  
  **Purpose**: Edits user information in External Admin.

- **Delete User**  
  **Endpoint**: `/extadmin/delete/user`  
  **Method**: `DELETE`  
  **Purpose**: Deletes a user from External Admin.

- **Search Users**  
  **Endpoint**: `/extadmin/users/search`  
  **Method**: `GET`  
  **Purpose**: Searches for users in External Admin.

- **Give Access to Application**  
  **Endpoint**: `/extadmin/giveAccess`  
  **Method**: `POST`  
  **Purpose**: Grants application access to a user.

- **Remove Access to Application**  
  **Endpoint**: `/extadmin`  
  **Method**: `DELETE`  
  **Purpose**: Removes application access for a user.

- **Activity by Month**  
  **Endpoint**: `/extadmin/count-by-month`  
  **Method**: `GET`  
  **Purpose**: Retrieves user activity data grouped by months for External Admin.

- **Users per Application**  
  **Endpoint**: `/extadmin/company`  
  **Method**: `GET`  
  **Purpose**: Fetches the list of users grouped by application usage.

---