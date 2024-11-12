PROJECT OVERVIEW
This is a console-based CRUD application to track coding sessions, built with C#, Dapper, SQLite, and Spectre.Console. The application allows users to log, view, update, and manage coding sessions while tracking progress toward coding goals. With features like detailed reporting and an intuitive Spectre Console-based UI, it provides an organized, user-friendly way to monitor productivity.
!!!
Note: To run this project locally, update the database path in the App.config file to a path on your machine. This configuration ensures that the application can access the database for all CRUD operations.
!!!

REQUIREMENTS:
- To show the data on the console, you should use the "Spectre.Console" library.
- You're required to have separate classes in different files (ex. UserInput.cs, Validation.cs, CodingController.cs)
- You should tell the user the specific format you want the date and time to be logged and not allow any other format.
- You'll need to create a configuration file that you'll contain your database path and connection strings.
- You'll need to create a "CodingSession" class in a separate file. It will contain the properties of your coding session: Id, StartTime, EndTime, Duration
- The user shouldn't input the duration of the session. It should be calculated based on the Start and End times, in a separate "CalculateDuration" method.
- The user should be able to input the start and end times manually.
- You need to use Dapper ORM for the data access 
- When reading from the database, you can't use an anonymous object, you have to read your table into a List of Coding Sessions.
- Follow the DRY Principle, and avoid code repetition.

CHALLENGES - COMPLETE:
- Add the possibility of tracking the coding time via a stopwatch so the user can track the session as it happens.
- Let the users filter their coding records per period (weeks, days, years) and/or order ascending or descending.
- Create reports where the users can see their total and average coding session per period.
- Create the ability to set coding goals and show how far the users are from reaching their goal, along with how many hours a day they would have to code to reach their goal. You can do it via SQL queries or with C#.

FEATURES:
Program Initialization
When the application starts, it establishes an SQL connection and checks for the existence of the necessary table.
If the database or table doesn't exist, they are created automatically, and the table is seeded with 10 random rows of data.

Console UI
The application uses Spectre Console to provide a more pleasant, user-friendly menu and navigation.
Users can easily cycle between menu options using the keyboard arrows.

CRUD Functions
The application uses the Dapper Micro-ORM to perform full CRUD operations with the database. 
Users can add new sessions by entering start and end times in the format yyyy-MM-dd, while the duration is automatically calculated and cannot be manually modified. 
All records are displayed in a clean, table-like format using the TableVisualisation class, powered by Spectre.Console.

Basic Reporting
The app includes simple report generation, displayed in an easy-to-read table format using TableVisualisation class utilisng the Spectre Console.
Reports show stats like average daily coding hours and total amount of sessions which can be filtered by days, weeks or months.

Goals
The Goals Feature allows users to set coding goals with ease. Upon setting a new goal, the application automatically assigns the current date as the start date, then prompts the user to specify the goal's end date and the total hours they aim to complete within this timeframe.
This feature includes full CRUD functionality, allowing users to create, view, update, and delete individual goals. Additionally, there’s an option to delete all goals if needed, making goal management simple and flexible.
Users can also generate a detailed report based on each goal, which provides insights into their progress. The report displays the number of days remaining until the goal end date and calculates the average daily coding hours required to meet the target. 

Key Classes and Their Roles:
Utilities Class:
The Utilities class centralizes commonly-used helper functions, making the codebase cleaner and adhering to the DRY principle.
This class includes functions for formatting dates and times consistently, performing calculations, handling errors, and logging actions or errors as needed.
By placing these utilities in one class, the application remains modular, with reusable logic accessible throughout the project.

DateValidator Class: This class verifies that the entered end date is always after the start date, ensuring logical consistency in date inputs and returns a boolean input.

DIFFICULITIES
- Being new to Dapper, I had to learn its basics and how it handles database operations in C#, alongside exploring other ORMs.
- Formatting and parsing select query results for clear presentation to users required careful planning and experimentation to ensure a user-friendly display.
- Crafting SQL queries, especially those involving date functions for reports, was challenging and required learning specific SQL date functions to get accurate results.

AREAS TO IMPROVE:
- Applying the DRY principle more rigorously by refactoring repetitive code could streamline functionality and reduce redundancy.
- Organizing classes by category within respective folders would enhance readability and make the codebase easier to maintain.
- Improving my SQL skills, especially with more complex queries, will be beneficial for future data-heavy features.
- Leveraging more OOP principles like inheritance and abstraction could make the codebase more robust and scalable.
