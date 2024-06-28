# Software Engineering

## Coding Standards

*This specification describes standard practices designed to eliminate or mitigate pitfalls inherent in the C language.*

|Rationale|Guideline|
|-|-|
|1.|Meets project requirements.|
|2.|Is testable.|
|3.|Can be maintained by various developers.|
|4.|Is easy for new programmers to learn.|


|Key points|Uniformity in coding is crucial|
|-|-|
|1.|Adhere to coding standards for consistency.|
|2.|Consistent code reduces the learning curve and maintenance effort.|
|3.|Tools will be developed to ensure consistency in protocols and drivers.|
|4.|Junior engineers benefit from reading and understanding uniform code.|
|5.|Deviations from standards require valid reasons and stakeholder approval.|

|Scope|Coding standards Guideline|
|-|-|
|1.|File structure and formats|
|2.|C language rules and guidelines|
|3.|Naming conventions|
|4.|Documentation practices|
|5.|Commenting rules|
|6.|Doxygen usage|

||Software Design Principles Summary|
|-|-|
|Accessibility|Design for the widest possible audience, including those with diverse backgrounds and abilities.|
|Alignment|Align elements to reduce disorder and improve understanding.|
|Chunking|Group information into manageable chunks to aid memory.|
|Confirmation|Use confirmations for critical actions to prevent errors but avoid overuse.|
|Consistency|Maintain consistency in design and coding to enhance usability and learnability without compromising clarity.|
|Maintainability|Make systems self-explanatory and easy to maintain.|
|Extensibility|Design for easy enhancement without disrupting the system.|
|Forgiveness|Help users avoid and recover from errors with features like reversibility and safety nets.|
|High Fan-In|Utilize shared routines efficiently.|
|Horror Vacui|Avoid cluttering designs with unnecessary elements.|
|Intellectual Manageability|Ensure systems are easy to understand and maintain.|
|Interference Effects|Avoid conflicts in cognitive processes to maintain efficiency and accuracy.|
|Leanness|Design systems with only necessary parts to reduce development and maintenance overhead.|
|Low Complexity|Keep systems simple for better manageability.|
|Minimal Connectedness|Limit interconnections among subprograms to simplify maintenance.|
|Minimize Code Size|Keep code compact, especially in resource-constrained environments.|
|Portability|Design systems to be easily transferable across different environments.|
|Reusability|Create components that can be reused in other systems.|
|Standard Techniques|Use common approaches to make systems familiar and easier to understand.|
|Stratified Design|Layer system design for consistent and clear views at different levels.|

||Principles for Software Maintenance Summary|
|-|-|
|Understand the Problem|Fully understand issues before attempting to fix them.|
|Understand the Program|Know the context in which problems occur.|
|Fix Symptoms and Underlying Problems|Address both immediate issues and root causes.|
|Change for Good Reason|Make changes confidently, not randomly.|
|Systematic Debugging|Approach debugging methodically and take responsibility for the code.|
|Avoid Blaming Others' Code|Systematically identify root causes without blaming unfamiliar code.|
|Use Source Control Wisely|Do not rely on version control for debugging.|
|Verify Fixes|Test fixes thoroughly and seek peer reviews.|
|Check for Similar Errors|Ensure similar mistakes are not present elsewhere in the code.|
|Update Comments and Documentation|Keep comments and documentation accurate and up-to-date.|

||Additional Recommendations Summary|
|-|-|
|1.|Seek assistance if debugging is challenging.|
|2.|Learn debugging techniques from experienced programmers.|
|3.|Focus on improving your debugging skills, not just fixing bugs.|
|4.|Avoid over-reliance on others' debugging expertise to develop your own skills.|

|QUICK REFERENCE|||
|-|-|-|
|Naming|Clarity and Uniqueness|Names must clearly represent their purpose and not be similar to existing concepts or standard header symbols.|
||No Overloading|Avoid overloading function or type names.|
||Abbreviations and Acronyms|Use standard abbreviations and industry-standard acronyms. Define any nonstandard ones in the file header.|
||Length and Capitalization|Names should be 10-30 characters long. Acronyms should not be fully capitalized (e.g., MyPciAddress).|
||Global and Module Variables|Prefix global variables with 'g' (e.g., gMyGuid) and module variables with 'm' (e.g., mMyGuid).|
|Formatting|General Rules|Indentation: Use two spaces for indentation, no tabs.|
|||Line Endings: Lines must end with CRLF (0x0D 0x0A).|
||Vertical Spacing|Grouping and Single Statements: Use blank lines to group code, with one statement or declaration per line. Braces for functions and multi-line predicates must be on their own lines.|
||Horizontal Spacing|Operator and Comma Spacing: Space around binary operators, after commas and semicolons, and before opening parentheses (except in macros). No spaces around structure and pointer operators or before array brackets.|
|Files|General Rules|Include Guards and File Types: Use #ifndef guards in header files, which should have a .h extension. Include files must not contain code-generating statements.|
|||Macros:Minimize functional macros and use parentheses for clarity.|
||Code Files|Data Types and Definitions: Avoid #define and typedef statements in code files.|
|||Structures and Enums: Structures should use typedef. Enums must have defined minimum and maximum elements.|
|||Function Definitions:Follow strict formatting rules for functions and control statements.|
||Vertical Spacing|Single Statements and Block Formatting: One statement per line, with braces aligned according to specific rules.|
|Documentation|Commenting|Explanation and Style: Comments should explain the purpose of the code, using C++ style // for local comments. Every file and function must have a formatted header.|
||Doxygen|Documentation: Use Doxygen comments for global and file-scope documentation. Common commands include @file, @param, @retval, @sa, and @test.|


## Practices for Writing Readable and Maintainable Code

| **Best Practice (C)**                     | **Description**                                                                                                   | **Bad Example**                                                                                                    | **Good Example**                                                                                                             |
|---------------------------------------|-------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| Avoid Abbreviations, Use Meaningful Names | Use complete and descriptive names for variables and functions to enhance readability.                             | `int e = 10;`                                                                                                      | `int employeeCount = 10;`                                                                                                    |
| Limit the Number of Function Parameters | Group multiple parameters into a struct for better readability and flexibility.                                   | `void createUser(char* name, int age, char* email, char* address) {}`                                              | `typedef struct { char* name; int age; char* email; char* address; } User; void createUser(User user) {}`                    |
| Simplify Conditional Statements       | Avoid lengthy conditionals by expressing conditions concisely.                                                     | `if (age >= 18) { if (hasLicense) { return 1; } } return 0;`                                                       | `return (age >= 18 && hasLicense);`                                                                                          |
| Limit Variable Scope                  | Use appropriate variable scope to prevent global variable pollution.                                               | `int globalVar = 1;`                                                                                               | `void exampleFunction() { int localVar = 1; const int constantVar = 2; }`                                                    |
| Each Function Should Do One Thing     | Ensure each function is responsible for a single functionality, improving testability and maintainability.         | `void processOrder(int* items, int itemCount, char* email) { int total = 0; for(int i = 0; i < itemCount; i++) { total += items[i]; } sendEmail(email, total); }` | `int calculateTotal(int* items, int itemCount) { int total = 0; for(int i = 0; i < itemCount; i++) { total += items[i]; } return total; } void sendEmail(char* email, int total) {}` |
| Use Early Return                      | Reduce nested if-else structures by using early return to make the code more concise.                              | `if (isPaid) { if (itemsInStock) { if (addressValid) { // Process order } else { return "Invalid address"; } } else { return "Items out of stock"; } } else { return "Payment not received"; }` | `if (!isPaid) { return "Payment not received"; } if (!itemsInStock) { return "Items out of stock"; } if (!addressValid) { return "Invalid address"; } // Process order` |


| **Best Practice (JavaScript)**                     | **Description**                                                                                                   | **Bad Example**                                                                                                    | **Good Example**                                                                                                             |
|---------------------------------------|-------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| Avoid Abbreviations, Use Meaningful Names | Use complete and descriptive names for variables and functions to enhance readability.                             | `let e = "example@example.com";`                                                                                   | `let email_address = "example@example.com";`                                                                                 |
| Limit the Number of Function Parameters | Group multiple parameters into an object for better readability and flexibility.                                   | `function createUser(name, age, email, address) {}`                                                                | `function createUser(user) { const { name, age, email_address, address } = user; }`                                          |
| Simplify Conditional Statements       | Avoid lengthy conditionals by expressing conditions concisely.                                                     | `if (person.age >= 18) { if (person.hasRiderLicense) { return true; } } return false;`                             | `return person.age >= 18 && person.hasRiderLicense;`                                                                         |
| Limit Variable Scope                  | Use `let` or `const` to limit the scope of variables, preventing global scope pollution.                           | `var globalVar = "I am global";`                                                                                   | `let localVar = "I am local"; const constantVar = "I am constant";`                                                          |
| Each Function Should Do One Thing     | Ensure each function is responsible for a single functionality, improving testability and maintainability.         | `function calculateOrderTotalAndSendEmail(order) { let total = 0; for (let item of order.items) { total += item.price * item.quantity; } sendEmail(order.customerEmail, total); return total; }` | `function calculateOrderTotal(order) { let total = 0; for (let item of order.items) { total += item.price * item.quantity; } return total; } function sendEmail(recipient, message) {}` |
| Use Early Return                      | Reduce nested if-else structures by using early return to make the code more concise.                              | `if (order.isPaid) { if (order.itemsInStock) { if (order.addressIsValid) { // Process order } else { return "Invalid address"; } } else { return "Items out of stock"; } } else { return "Payment not received"; }` | `if (!order.isPaid) { return "Payment not received"; } if (!order.itemsInStock) { return "Items out of stock"; } if (!order.addressIsValid) { return "Invalid address"; } // Process order` |

