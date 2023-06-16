# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

    > | let, var, and const

02. What is the definition of a function?

    > | A subprogram to preform a particular task.

03. What are the `SOLID` principles?

    > | Single responsibility principle
    Open-closed principle
    Liskov Substitution Principle
    Interface Segregation Principle
    Dependency Inversion Principle 

04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    > | console.log(fruit[2]);

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    > | use the .push() method.

06. Give an example of a JavaScript `Conditional`:

    > | if and else are the most commonly used conditionals.

if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are not an adult.");
}

07. What is the main difference between `parameters` and `arguments`?

    > | Parameters are used to define a function and arguments receive their value from the parameters in a function.

08. Instead of writing everything to the console, what is a better way to debug your code?

    > | Try to write your code so that as you go along it will automatically test some of your code without you having to manually, TDD (Test Driven Development)

09. What is the difference between a `primitive` value and a `reference` value?

    > Primitive values cannot be changed once they are created and reference value is just being compared by seeing if they have the same memory location. 

10. Demonstrate a loop that prints the numbers between -100 and 100?

    > for (let i = -100; i <= 100; i++) {
  console.log(i);
}

