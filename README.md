📝 Employee Directory App Documentation
=======================================

📂 Overview
-----------

This is a **Next.js** application with **Apollo Client** integration for managing employees.Features include:

*   Viewing all employees.
    
*   Filtering employees by department.
    
*   Adding new employees.
    
*   Viewing individual employee details.
    

It uses:

*   **GraphQL Queries & Mutations**.
    
*   **Zod** for form validation.
    
*   **Tailwind CSS** (via utility classes) for styling.
    
*   **TypeScript types** for strong typing.
    

🏠 Home Page (HomePage)
-----------------------

Displays a list of employees in a table, with:

*   Department filter dropdown.
    
*   "Add New Employee" button.
    
*   Clicking a row navigates to the employee detail page.
    

**GraphQL:**

*   GET\_ALL\_EMPLOYEES\_AND\_FLOORS:
    
    *   Fetches all employees.
        
    *   Fetches departments and their floors.
        

**Logic:**

*   Creates a mapping of department → floor.
    
*   Allows filtering employees by department.
    

➕ Add Employee Page (AddEmployeePage)
-------------------------------------

Provides a form to create a new employee.

**Form Fields:**

*   Name (text)
    
*   Position (text)
    
*   Department (dropdown: Engineering, Design, HR)
    
*   Salary (number)
    

**Validation:**

*   Uses Zod schema (EmployeeSchema) to ensure:
    
    *   All fields are filled.
        
    *   Salary is a non-negative number.
        
    *   Department is one of the predefined enums.
        

**On Submit:**

*   Validates inputs.
    
*   Calls ADD\_EMPLOYEE mutation.
    
*   Refetches the employee list.
    
*   Redirects to Home Page.
    

**Error Handling:**

*   Displays validation errors per field.
    
*   Shows mutation errors in the console.
    

👤 Employee Detail Page (EmployeeDetailPage)
--------------------------------------------

Displays details of a single employee in a styled card with:

*   Name
    
*   Position
    
*   Department
    
*   Salary
    

**GraphQL:**

*   GET\_EMPLOYEE\_DETAILS: Fetches data for a specific employee by id.
    

🛠 GraphQL Operations
---------------------

### Queries

*   **GET\_ALL\_EMPLOYEES\_AND\_FLOORS**
    
    *   Returns all employees and departments with floor info.
        
*   **GET\_EMPLOYEE\_DETAILS**
    
    *   Returns detailed info for a single employee.
        

### Mutation

*   **ADD\_EMPLOYEE**
    
    *   Adds a new employee with provided data.
        

🧩 Components Summary
---------------------

ComponentPurpose**HomePage**Show all employees, filter, and navigate to detail pages.**AddEmployeePage**Add a new employee with validation.**EmployeeDetailPage**Display details of an employee.

🎨 Styling
----------

*   Dark mode support.
    
*   Tailwind CSS classes for:
    
    *   Input styling.
        
    *   Button styling.
        
    *   Hover & focus transitions.
        

💡 How to Use
-------------

1.  **Run the app** with npm run dev.
    
2.  Visit / to see all employees.
    
3.  Click + Add New Employee to add a new record.
    
4.  Click on any employee row to see their details.
    
5.  Use the department filter to narrow the list.