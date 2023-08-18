# CSharp and SQL Fundamentals
01. What is the purpose of a `namespace`?

  > | provides a scope to the identifiers (the names of types, functions, variables, etc) inside it

02. What is the difference between a `class` and an `interface`?

  > | You can create objects in a class and cannot in an interface

03. What is the method that returns an instance of a class, yet it has no return type?

  > |VOID

05. In the Car example what is the access modifier of the `Start()` method?

  ```c#
  abstract class Car
  {
    public string Start()
    {

      return "Vroooom";

    }
  }
  ```

  > | public

06. In the Car example what is `string` an indication of?

  > | The type of data we declare it

07. In the Car example what is `abstract` preventing?

  > | allows you to make classes that are incomplete.

08. In a SQL table, what is the difference between information in a row and information in a column?

  > | Columns are vertical, with values, and rows are horizontal with elements

09. Demonstrate the necessary SQL for creating a table called `characters` with the values `name, age, description` as strings, and an `int` id.

  > | CREATE TABLE characters( id INT NOT NULL AUTO_INCREMENT PRIMARY KEY, name VARCHAR(50) NOT NULL, age DOUBLE NOT NULL DEFAULT 1, description VARCHAR(1000) )

10. In SQL how can you query more than a single table? Provide an example.

  > | SELECT table1.column1, table2.column2 FROM table1, table2 WHERE table1.column1 = table2.column1;
