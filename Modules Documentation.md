# CS Modules

**TimePeriods_CS**
This service type module stores information on everything that concerns the accounting of possible time periods for bookings in the system. Also, this module stores information of the mapping table of the period for which the booing is done, the project, the person for whom this time was planned. 
The table is a standard mapping table that uses the foreign_key to link the possible booing period and data regarding that booing.

**Projects_CS**
This service type module stores information in the database on what projects were created. The table includes such information about the project, as belonging to a department, project details (budget, terms), and a table of grades.
The database part of this module covers all the information about the projects that is available in the application.
The Logic part of this module contains the CRUD for working with the projects table. 

**Handbooks_CS**
This module stores several entities that describe the reference tables used in the project. 
This module is responsible for the following entities: Clients, Departments, Grade, Statis Handbooks(Currency, FTE, Status of Project, Sex, ProjectTypes).
Static data from Static Handbooks is used throughout the project to generate optional selection items.

In terms of logic, this module does not contain Actions.

**Users_CS**
This module stores consolidated information about the users in the tenant. The module is responsible for storing information about the personal information of logged in employees, the mapping of an employee's account and his record in the OutSystems Users monitoring system. It also stores information about the mapping of the user and the department he belongs to. This is done by using the table of departments from Handbooks_CS.
Also, this module stores pictures of users in URL format.

The logic block contains CRUD methods for interacting with the user database.

**Reports_CS**
This module does not store information, but only a few reference modules to collect inofrmation for reports.
Part of the logic stores in itself the necessary methods to perform the construction of the structure of the survey, which then will be visualized in the module Reports_CW.

**CommonActions_CS**
This module stores only methods that are reused on almost every screen of the application. These are the methods from the analysis section of the user status and downloaded local information.


# CW Modules

**Availability_CW**
This module contains reusable components and screens that describe the load planning functionality and its display.
Screens:
ProjectWeeks - The page that opens when you fail a week. Shows the occupancy of users (rows) relative to projects (columns).
ProjectWeeksDetails - User time scheduling page for the project. This is a wizard with the ability to track the progress of booing and the final result. 
Timesheet - Home page which shows user load by weeks in the form of sliders in the table cells. You can fall into the weeks.

**Projects_CW**
This module contains reusable components and screens that describe the functionality of creating and accounting projects that are available for this department.
Screens:
Projects - List of projects, which is presented in the form of a table displaying information about its status, type, name and other.
ProjectDetail - A page for project configuration.

**Clients_CW**
This module contains reusable components and screens that describe the functionality of creating and accounting clients that are available for this department.
Screens:
Clients - list of created clients and their descriptions.
ClientDetail - screen for editing or creating a new client for this tenant.

**Grades_CW**
This module contains reusable components and screens that describe the functionality for creating and accounting grades that are available for a system or department.
Screens:
Grade - A list of the grades that are currently created in the system
GradeDetail - A screen for creating or editing grade information.

**Departments_CW**
This module contains reusable components and screens that describe the functionality for creating and accounting departments that are available for the current Tenant.
Screens:
Department - A list of all departments available in Tenant and the number of users in them.
DepartmentDetail - A screen for editing department(s) and their details.

**Users_CW**
This module contains reusable components and screens that describe the functionality of creating and accounting users that are available by department.
Screens:
Employees - list of users that belong to the selected in the header department
EmployeeDetail - screen for editing user data and uploading his photo. 

**Reports_CW**
This module contains reusable components and screens that describe the functionality of the demonstration reports in 2 different categories.
Screens:
EmployeesUtilization - A report that shows the total percentage of employee utilization for the selected period. It is displayed in the hard/soft booking format and in the percentage of the total employment of an employee for the period.
ProjectsRevenue - the report that shows revenue regarding projects for the period. The amount is formed on the basis of the project settings (grade rates) 

# LIB Modules

**CommonWidgets_LIB**
This model contains visual widgets or layouts that are used in the project.
Among these are: application header, page layouts, button elements, drop-down lists.
This module should not store database data because it is responsible only for the visual.

# SVC Modules

**ClientData_SVC**
This module stores client variables and provides an interface to manipulate these variables.