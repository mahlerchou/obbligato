# Obbligato
Code generator for wrapping SQL Server strored procedure into OO-like pure ado.net code and RESTful API services.

## How to use Obbligato to generate ADO.NET based C# source code?
* First download latest Obbligato and run.
* Create an Obbligato project and connect to SQL Server.
* Add stored procedures to project.
* Generate C# code or ASP.NET WEB API model and codes.

## Add Obbligato header to stored procedure.
An Obbligato header is a comment block that write before first line of stored procedure. 
    /* 
      OODA_REMARK: The intent of stored procedure that will show in Visual Studio Intelligent Insight.
      OODA_RESULT: VOID
    */
    CREATE PROCEDURE 
        
## Obbligato result type - OODA_RESULT
Obbligato defines three types of stored-procedure based on its executed result. 
### VOID type
When set "OODA_RESULT: VOID" means the stored procedure has no return. The execute() method in Obbligato framework would be void return type, too.
### SCALAR type
When set "OODA_RESULT: SCALAR" means that stored procedure return exact single value (single column and single row regrards it column name).
### RECORDSET type
When set "OODA_RESULT: RECORDSET" means that stored procedure would return result set after execution. As you adding recordset type stored procedure to Obbligato project, the stored procedure will be executed once for retriving column names from result set.
