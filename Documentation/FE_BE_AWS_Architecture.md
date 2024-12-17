
# How The Frontend, Backend, & AWS Architecture

## 1. **System Context Diagram**
   
The System Context Diagram provides an overview of the entire system by defining how the **Frontend**, **Backend**, and **AWS Backend** components interact with each other. It identifies external entities that interact with the system, as well as the overall data flow.

### **Interaction Flow:**

1. **Frontend** sends requests (e.g., login, data retrieval) to the **Backend**.
2. **Backend** processes these requests, interacts with the **AWS Backend**, and retrieves necessary data or performs tasks.
3. **AWS Backend** supports backend operations with storage and external services.
4. Processed data or responses are sent back from the **Backend** to the **Frontend** for display.

### Diagram:

<p align="center">
  <img src="System_context_diagram.drawio.png" alt="System Context Diagram">
</p>


## 2. **Container Diagram**

The **Container Diagram** focuses on the architecture and interaction between containers that handle different layers of the application. This diagram breaks down the system into containers like the **Frontend**, **Backend**, **EKS Nodes**, and other **AWS services**.

### **Interaction Flow:**

1. **Frontend** interacts with the **EKS Node (Frontend)** to process user inputs.
2. **EKS Node (Frontend)** communicates with **EKS Node (Backend)** for data and logic processing.
3. **EKS Node (Backend)** interacts with **RDS** for database queries and **Cognito** for user authentication.
4. Responses flow back through the **EKS Nodes** to the **Frontend** for user display.

### Diagram:

<p align="center">
  <img src="Container_diagram.drawio.png" alt="Container Diagram">
</p>


## 3. **Component Diagram**

The **Component Diagram** provides more granular details, focusing on the key components inside the **Frontend** and **Backend**. It explains how different microservices and components inside the system interact with each other to deliver the required functionalities.

### **Interaction Flow:**
  
1. **Frontend** interacts with **EKS Node (Frontend)** to handle user input and display data.
2. **EKS Node (Frontend)** sends requests to **EKS Node (Backend)** for processing business logic.
3. **EKS Node (Backend)** communicates with **RDS** to retrieve/store data and **Cognito** for user authentication.
4. **AWS Lambda** may be triggered for additional processing, such as sending notifications or automating tasks.
5. **AWS SES** is used to send email notifications to users based on backend events (e.g., registration, password reset).
6. Processed data and responses are sent back through **EKS Nodes** to the **Frontend** for user display.

### Diagram:

<p align="center">
  <img src="Component_diagram.drawio.png" alt="Component Diagram">
</p>


## 4. **Code Diagram**

The **Code Diagram** focuses on the detailed communication and data flow, emphasizing the interaction of services at the code and deployment level. It includes key infrastructure components like **Amazon CloudFront**, **Internal Gateway**, **ALB (Application Load Balancer)**, and how they distribute traffic across the system.

### **Interaction Flow:**
 
1. **Users** interact with the **Frontend**, which is served via **Amazon CloudFront** for improved performance.
2. The **Frontend** sends requests through the **Internal Gateway** to the **EKS Node (Backend)** for business logic processing.
3. **EKS Node (Backend)** communicates with **RDS** to retrieve/store data and uses **Cognito** for user authentication.
4. **AWS Lambda** may be triggered to handle background tasks (e.g., notifications, data processing).
5. **AWS SES** sends transactional emails based on backend events (e.g., password resets).
6. **Application Load Balancer (ALB)** distributes incoming traffic across the backend services for improved availability and scalability.
7. Responses from the backend are sent back through the **Internal Gateway** and **Frontend** for user display.

### Diagram:

<p align="center">
  <img src="Code_diagram.drawio.png" alt="Code Diagram">
</p>

