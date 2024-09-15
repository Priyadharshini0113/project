# Customer Support Chatbot for Retail Analytics

# Project Overview
The Customer Support Chatbot for Retail Analytics helps retail businesses quickly respond to customer queries about sales, inventory, and product information. It combines a user-friendly interface, natural language understanding via an open-source Large Language Model (LLM), and structured data retrieval from a SQL database.

# Features

1. **Frontend**:
   - A responsive and user-friendly web interface.
   - **Chat History**: Displays previous conversations to maintain context.
   - **Typing Indicators**: Shows when the bot is processing a query.
   - **Minimalistic Design**: Focuses on user experience with easy navigation and clear visuals.
   - **Real-time Chat Interface**: Customers can ask questions and receive responses instantly.
   
2. **Backend**:
   - **Request Handling**: Handles user queries and processes data requests.
   - **LLM Communication**: Communicates with the LLM to interpret natural language inputs.
   - **SQL Query Execution**: Fetches relevant sales, product, and inventory data based on user queries.
   - **Error Handling**: Includes error handling, logging, and monitoring for robust operation.

3. **SQL Database**:
   - **Data Storage**: Stores sales, product, and customer query data.
   - **Optimized Retrieval**: Optimized to handle quick data retrieval.

4. **REST API**:
   - **Secure Endpoints**: Provides secure and scalable endpoints for the frontend to query sales data, retrieve chat history, and interact with the LLM.

5. **LLM Integration**:
   - **Open-Source LLM**: Uses an open-source Large Language Model (LLM) Gemini-API.
   - **Natural Language Understanding**: Interprets user inputs, generates responses, and forwards queries to the backend for data retrieval.

## Tech Stack

### Frontend
- **React**: A JavaScript library for building user interfaces.
- **HTML/CSS**: For structuring and styling the web application.
- **JavaScript**: Adds dynamic functionality and interactivity.
- **Material-UI**: Provides UI components and ensures design consistency.

### Backend
- **Node.js**: A JavaScript runtime for building scalable network applications.
- **Express.js**: A web application framework for Node.js that handles server-side logic and routing.

### Database
- **MySQL**: A relational database system for storing and managing customer and sales data.

### Integration with Open-Source LLM
- **Gemini API**: Used for integrating language model capabilities into the application.
 
# Chatbot System Workflow

1. **User Interaction**:
   - **Query Entry**: Users input queries or requests in the chatbot interface on the frontend.

2. **Frontend to Backend**:
   - **Query Transmission**: The frontend sends the user query to the backend using RESTful APIs.

3. **Backend Processing**:
   - **Initial Processing**: The backend receives the query and determines if further interpretation is required.
   - **LLM Communication**: For queries needing interpretation, the backend forwards them to the Large Language Model (LLM).

4. **LLM Query Handling**:
   - **Query Interpretation**: The LLM processes the query, generates a structured request if necessary, and determines if additional data is needed.

5. **LLM to SQL Database**:
   - **Database Query**: If required, the LLM sends a structured query to the SQL database to fetch relevant data.

6. **SQL Database Query**:
   - **Data Retrieval**: The SQL database processes the query, retrieves the relevant information, and returns it to the backend.

7. **Backend Response Handling**:
   - **Response Integration**: The backend integrates the data from the SQL database with the LLM's response, formats it appropriately, and prepares it for sending.

8. **Backend to Frontend**:
   - **Response Transmission**: The backend sends the formatted response back to the frontend via RESTful APIs.

9. **Frontend Display**:
   - **User Display**: The frontend displays the final response to the user, completing the interaction.

This structure outlines the flow from user interaction through to the final display of responses, detailing each component’s role in the system.


# Process Workflow Architecture

![C5I (2)](https://github.com/user-attachments/assets/53181487-4cdd-4122-ae85-844146488f50)


# Version Control Setup

### 1. Clone the Repository
1. **Git Installation**
   -Check whether Git is present or not,if not install it

2. **Clone the Repository**:
   - Open a terminal (or Command Prompt on Windows).
   - Clone the repository with:
     ```sh
     git clone https://github.com/Priyadharshini0113/C5I-ASSIGNMENT.git
     ```

3. **Navigate to the Project Directory**:
   - Change to the project directory using:
     ```sh
     cd C5I-ASSIGNMENT
     ```

### 2. Create and Manage Branches

1. **Create a New Branch**:
   - Create and switch to a new branch with:
     ```sh
     git checkout -b your-branch-name
     ```
   - The `your-branch-name` which is created here are ( frontend , backend , database )

2. **Start Working**:
   - Make your changes or additions in the project files.
   - Use `git status` to check the status of your changes.

3. **Stage and Commit Changes**:
   - Stage your changes using:
     ```sh
     git add .
     ```
   - Commit your changes with a descriptive message:
     ```sh
     git commit -m "Your commit message"
     ```

4. **Push Your Branch to Remote**:
   - Push your branch to the remote repository with:
     ```sh
     git push origin your-branch-name
     ```
  

### 3. Merging Branches

1. **Switch to the Main Branch**:
   - Before merging, switch to the branch you want to merge into, usually `main` or `master`:
     ```sh
     git checkout main
     ```
   - Ensure you have the latest changes from the remote repository:
     ```sh
     git pull origin main
     ```

2. **Merge Your Branch**:
   - Merge the branch you’ve been working on into the main branch:
     ```sh
     git merge your-branch-name
     ```
   - Resolve any merge conflicts if they arise. Git will prompt you with instructions on how to resolve conflicts.

3. **Push the Merged Changes**:
   - After successfully merging, push the updated main branch to the remote repository:
     ```sh
     git push origin main
     ```
# Database Schema for Retail Support

This provides an overview of the database schema for the `retail_support` database. The schema includes tables for customers, products, sales, sales products, and queries, which are essential for managing customer interactions, sales transactions, and support queries.

### Customers Table

Stores information about customers.

| Column     | Type         | Description                             |
|------------|--------------|-----------------------------------------|
| `CustomerID` | `INT`        | Primary key, auto-incremented ID         |
| `FirstName`  | `VARCHAR(50)`| Customer's first name                    |
| `LastName`   | `VARCHAR(50)`| Customer's last name                     |
| `Email`      | `VARCHAR(100)`| Customer's email address                |
| `Phone`      | `VARCHAR(15)`| Customer's phone number                  |
| `Address`    | `TEXT`       | Customer's address                       |
| `City`       | `VARCHAR(50)`| City of the customer                     |
| `State`      | `VARCHAR(50)`| State of the customer                    |
| `ZipCode`    | `VARCHAR(10)`| ZIP code of the customer                 |

### Products Table

Stores information about products available for sale.

| Column        | Type           | Description                              |
|---------------|----------------|------------------------------------------|
| `ProductID`   | `INT`          | Primary key, auto-incremented ID          |
| `ProductName` | `VARCHAR(100)` | Name of the product                      |
| `Category`    | `VARCHAR(50)`  | Category of the product                  |
| `Price`       | `DECIMAL(10, 2)`| Price of the product                     |
| `StockQuantity`| `INT`         | Quantity of the product in stock         |

### Sales Table

Records sales transactions.

| Column       | Type          | Description                              |
|--------------|---------------|------------------------------------------|
| `SaleID`     | `INT`         | Primary key, auto-incremented ID          |
| `CustomerID` | `INT`         | Foreign key to `Customers.CustomerID`     |
| `SaleDate`   | `DATE`        | Date of the sale                          |
| `TotalAmount`| `DECIMAL(10, 2)`| Total amount of the sale                 |

### Sales_Products Table

Associates products with sales.

| Column      | Type       | Description                                  |
|-------------|------------|----------------------------------------------|
| `SaleID`    | `INT`      | Foreign key to `Sales.SaleID`                 |
| `ProductID` | `INT`      | Foreign key to `Products.ProductID`           |
| `Quantity`  | `INT`      | Quantity of the product sold                 |
| Primary Key  | (`SaleID`, `ProductID`) | Composite primary key              |

### Queries Table

Stores customer queries and their responses.

| Column        | Type         | Description                               |
|---------------|--------------|-------------------------------------------|
| `QueryID`     | `INT`        | Primary key, auto-incremented ID           |
| `CustomerID`  | `INT`        | Foreign key to `Customers.CustomerID`      |
| `QueryDate`   | `DATE`       | Date of the query                         |
| `QueryText`   | `TEXT`       | Text of the query                         |
| `ResponseText`| `TEXT`       | Response to the query                     |


