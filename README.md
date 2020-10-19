# Obbligato
Obbligato (Italian pronunciation: [obbliˈɡaːto], also spelled obligato) usually describes a musical line that is in some way indispensable in performance such as piano accompaniment. As a code generator, it generates ADO.NET style C#/API source codes. The Obbligato framework wrapping SQL stored procedure into easy use and easy to debug Object Oriented Model, all we need is to generate code then COPY-PASTE to Visual Studio. 

Before Obbligato, when SQL server stored procedure changes parameters, the client program would even know until runtime, it is dangerous and error prone. Obbligato brings parameter check from runtime to compiling time, this would significant improves code qualitity. Let C# compiler check paramter for you, what can be wrong? 

Enjoy ~ 

## How to use Obbligato to generate ADO.NET based C# source code?
* First download latest Obbligato and run.
* Create an Obbligato project and connect to SQL Server.
* Add stored procedures to project.
* Generate C# code or ASP.NET WEB API model and codes.

## Add Obbligato header to stored procedure.
An Obbligato header is a comment block that write before first line of stored procedure. 
<pre><code>    /* 
      OODA_REMARK: The intent of stored procedure that will show in Visual Studio Intelligent Insight.
      OODA_RESULT: VOID
    */
    CREATE PROCEDURE sp_add
      @name     nvarchar(50),
      @age      int
    AS 
      INSERT INTO Student (name, age) VALUES (@name, @age)
</pre></code>
To execute sp_add in Obbligato way would be: 
<pre><code>    var p = new sp_add.Param() { "Mahler Chou", 29 };
    sp_add.execute(p);
</pre></code>
## Obbligato result type - OODA_RESULT
Obbligato defines three types of stored-procedure based on its executed result. 
### VOID type
When set "OODA_RESULT: VOID" means the stored procedure has no return. The execute() method in Obbligato framework would be void return type, too.
### SCALAR type
When set "OODA_RESULT: SCALAR" means that stored procedure return exact single value (single column and single row regrards it column name).
### RECORDSET type
When set "OODA_RESULT: RECORDSET" means that stored procedure would return result set after execution. As you adding recordset type stored procedure to Obbligato project, the stored procedure will be executed once for retriving column names from result set.
