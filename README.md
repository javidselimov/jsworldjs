# JavaScript Translation Repository

## Table of Contents

1. [Introduction](#introduction)
2. [Usage](#usage)
3. [Contributing](#contributing)
4. [Credits](#credits)
5. [new.target](#newtarget)
6. [Dependency Injection](#dependency-injection)
7. [Memoization](#memoization)
8. [Translation](#translation)

## Introduction

Welcome to the **JavaScript Translation Repository**! This repository serves as a collection of translations of my Medium articles about JavaScript. Here, you'll find a treasure trove of knowledge and insights into the fascinating world of JavaScript, all presented in various languages.

## About the Repository

This repository is a compilation of my translated articles from Medium, where I share my thoughts, tutorials, and discoveries related to JavaScript. Each translation aims to make the content accessible to a wider audience by bringing it into different languages.

## Usage

Feel free to explore the repository and browse through the available translations. You can navigate through the folders to find articles in specific languages. Each translated article is stored as a separate file, allowing for easy access and reference.

To make the most of this repository, simply choose the language you prefer and dive into the articles. Whether you're a beginner or an experienced developer, you'll find a wealth of information and insights to expand your understanding of JavaScript.

## Contributing

Contributions to this repository are welcome! If you're interested in translating one of my articles into another language, or if you'd like to suggest improvements to existing translations, please follow these steps:

1. Fork this repository to your GitHub account.
2. Create a new branch for your translation or changes.
3. Make your modifications, ensuring accuracy and clarity in the translation.
4. Commit your changes and push them to your forked repository.
5. Submit a pull request, explaining the changes you've made and the language you've translated into.

Your contributions will help make JavaScript knowledge more accessible to people around the world.

## Credits

I would like to express my gratitude to all the contributors who have dedicated their time and effort to translate my articles. Your contributions are invaluable in spreading knowledge and bridging language barriers.

## Contact

If you have any questions, suggestions, or feedback regarding this repository or the translations, please feel free to reach out to me. You can contact me through GitHub or find my contact information on my Medium profile.

Thank you for your interest in my translated JavaScript articles! Together, let's empower developers worldwide with the knowledge they need to excel in their JavaScript journey.

Happy coding and happy translating!

## Newtarget

### Introduction:

JavaScript is a realm of wonders and mysteries, filled with hidden gems that await discovery. One such gem is the `new.target` property, a special and enchanting feature that allows us to unravel the secrets of constructors and their derived classes. In this epic article, we embark on a journey through the realm of new.target, with a touch of humor and whimsical variable names that will make you chuckle.

### The Mysterious new.target Property:

Let us introduce you to our first hero, `new.target`. It is a property that is automatically defined within the scope of a constructor function or method when it is invoked with the `new` keyword. This magical property holds a reference to the constructor or class that was directly invoked, enabling us to understand the true origins of an instance.

### The Great Constructor Quest:

Imagine we have a fantastical land of creatures known as “Animals,” each with their unique abilities and characteristics. Our constructors are named in a rather whimsical fashion, adding a touch of mirth to our tale. Let’s meet our heroes:

```js

class Animal {
  constructor() {
    if (new.target === Animal) {
      this.species = 'Mysterious';
      console.log('A new Animal has been created!');
    } else {
      console.log('A new Animal has been summoned from another dimension!');
    }
  }
}
```

In the above example, when we create an instance using `new Animal()`, the `new.target` property within the constructor will refer to the Animal constructor itself. However, if we create an instance using a derived class, such as `new Dog()`, the `new.target` property will point to the derived class instead.

Deriving Marvelous Creatures:
Now, let's introduce a derived class named Dog that inherits from our beloved Animal:

```js

class Dog extends Animal {
  constructor() {
    super();
    console.log('A new Dog has entered the scene!');
  }
}
```

When we create a new instance of Dog using `new Dog()`, the constructor is executed. As a result, both the Animal and Dog constructors are invoked in a cascading manner. With the help of `new.target`, we can differentiate between instances of Animal and Dog, unraveling the secret behind their creation.

```js

function summonAnimal() {
  if (new.target) {
    console.log('An Animal is being summoned!');
  } else {
    console.log('An Animal is appearing through unknown means!');
  }
}
```
In this peculiar function, when we call summonAnimal() directly, `new.target` will be undefined. However, if we use new summonAnimal(), new.target will refer to the function itself, indicating that it was invoked as a constructor.

Conclusion:
We have embarked on a thrilling adventure into the realm of new.target, discovering its magical powers and unraveling the mysteries of constructors and derived classes. With a touch of whimsy and amusing variable names, we hope this journey has brought a smile to your face.

Remember, as developers, it's not just about unraveling complexities but also embracing the joy and humor that can be found in our code. So go forth, explore, and let your code be a reflection of your imagination and wit!

Happy coding, adventurers!



**[⬆ back to top](#table-of-contents)**

## Dependency Injection

In modern software development, managing dependencies efficiently is crucial for building robust and maintainable applications. One technique that aids in achieving this is dependency injection (DI). In this article, we will explore the concept of dependency injection, delve into advanced examples in JavaScript, and touch upon its alternative implementation in TypeScript.

Understanding Dependency Injection:
Dependency injection is a design pattern that promotes loose coupling by externalizing the creation and management of dependencies. Rather than a class instantiating its dependencies internally, the dependencies are provided externally, allowing for better flexibility, testability, and scalability.

Let's dive into a few advanced examples of dependency injection in JavaScript:

Constructor Injection:
Constructor injection involves passing dependencies to a class through its constructor. Here's an example:

```javascript
class UserService {
  constructor(database) {
    this.database = database;
  }

  // Class methods...
}

const database = new Database();
const userService = new UserService(database);
```

Property Injection:
In property injection, dependencies are assigned to class properties. This approach is useful when dealing with optional dependencies. Consider the following example:

```javascript

class Logger {
  setAnalytics(analytics) {
    this.analytics = analytics;
  }

  // Class methods...
}

const logger = new Logger();
const analytics = new Analytics();
logger.setAnalytics(analytics);
```
Method Injection:
Method injection involves passing dependencies as arguments to class methods. This approach enables selective injection of dependencies. Here's an example:

```javascript

class EmailService {
  sendEmail(message, notificationService) {
    // Send email using the notification service
  }

  // Class methods...
}

const emailService = new EmailService();
const notificationService = new NotificationService();
emailService.sendEmail("Hello, world!", notificationService);

```

Alternative Implementation in TypeScript:
TypeScript provides additional features for dependency injection through its support for decorators and interfaces. Let's explore an alternative approach using TypeScript:

```typescript

interface IDatabase {
  // Database methods...
}

@injectable()
class Database implements IDatabase {
  // Implement database methods...
}

@injectable()
class UserService {
  constructor(@inject("Database") private database: IDatabase) {}

  // Class methods...
}

const container = new Container();
container.bind<IDatabase>("Database").to(Database);
container.bind<UserService>(UserService);

const userService = container.get<UserService>(UserService);

```

more accurate example

```js
import { injectable, inject, Container } from "inversify";

// Define an interface for the database
interface IDatabase {
  // Database methods...
}

// Implement the database using the IDatabase interface
@injectable()
class Database implements IDatabase {
  // Implement database methods...
}

// Define the UserService class with dependency injection
@injectable()
class UserService {
  constructor(@inject("Database") private database: IDatabase) {
    // The database dependency is automatically injected via constructor
  }

  // Class methods...
}

// Create an instance of the container
const container = new Container();

// Bind the IDatabase interface to the Database implementation
container.bind<IDatabase>("Database").to(Database);

// Bind the UserService class
container.bind<UserService>(UserService);

// Resolve the UserService instance from the container
const userService = container.get<UserService>(UserService);
```

We import the necessary decorators and classes from the inversify library.

We define the IDatabase interface that specifies the methods expected from a database.

The Database class implements the IDatabase interface.

We use the @injectable() decorator to mark the Database class as injectable. This decorator allows the container to recognize it as a dependency that can be resolved and injected.

The UserService class is marked as injectable using the @injectable() decorator. The class has a constructor that accepts a parameter named database of type IDatabase.

We use the @inject() decorator on the database parameter to specify that it should be resolved using the binding named "Database". This decorator tells the container to inject the Database instance when creating an instance of UserService.

We create an instance of the Container class from the inversify library, which acts as the container for managing and resolving dependencies.

Using the bind() method of the container, we associate the IDatabase interface with the Database implementation. This binding tells the container how to resolve the IDatabase dependency when it's requested.

Similarly, we bind the UserService class to the container.

Finally, we use the get() method of the container to resolve an instance of UserService. The container automatically resolves the dependencies, in this case, the Database instance, and injects it into the UserService constructor.


The inversify library does indeed exist and is commonly used for dependency injection in TypeScript projects. It is a popular and widely adopted library for managing dependencies and performing inversion of control in TypeScript.

To use the inversify library, you will need to install it via npm or yarn. You can do so by running the following command in your project directory:

```
npm install inversify reflect-metadata
```
Once installed, you can import the necessary decorators and classes from the library, as shown in the example code.

```ts

import { injectable, inject, Container } from "inversify";

// Rest of the code remains the same...

```


Dependency injection is a powerful technique for managing dependencies in JavaScript and TypeScript applications. By externalizing dependency creation and management, we can achieve greater flexibility, testability, and maintainability. In JavaScript, we explored advanced examples of dependency injection, including constructor injection, property injection, and method injection. Additionally, we discussed an alternative implementation in TypeScript using decorators and interfaces. Leveraging these techniques can significantly improve the architecture and quality of your codebase.

Remember, embracing dependency injection enables clean and modular designs that foster code reusability and ease of maintenance, leading to more robust and scalable applications.

**[⬆ back to top](#table-of-contents)**

## Memoization

In the world of JavaScript interviews, the concept of memoization often makes an appearance, challenging developers to demonstrate their problem-solving skills. With the potential to consume around 7-8 minutes of interview time, solving a memoization problem efficiently can be a strong indicator of a developer's proficiency, particularly at the intermediate level. While memoization was a technique that was once implemented manually, modern frameworks and libraries, like React, have introduced their own hooks and mechanisms to tackle this issue effortlessly. However, in this discussion, we will focus solely on the native JavaScript implementation of this powerful technique. Get ready to delve into the world of memoization and learn how to optimize performance like a pro.

```js

// First creting a counter to see the result of cashing
let counter = 0;
//  Creating Memo function which accepts a callback

function Memo(callback) {
  //  creating a variable to kepp on unique key the value of the callback function but first this will assign to emty object
  const cash = {};
  // this function must return a new function which will take arguments ...args

  return (...args) => {
    const key = args.join("-"); //  alternatively we can use JSON.stringify(...args)

    if (key in cash) {
      return cash[key];
    }

    cash[key] = callback(...args);
    //  ading counter ühen not calling from cash
    counter += 1;
    return cash[key];
  };
}

const memoizedFunc = Memo((a, b) => a + b);

console.log(memoizedFunc(3, 5));
console.log(memoizedFunc(3, 5));
console.log(memoizedFunc(3, 5));
console.log(memoizedFunc(3, 5));
console.log(memoizedFunc(3, 5));
console.log(memoizedFunc(5, 5));
console.log(memoizedFunc(5, 5));

console.log(counter);

```

The code i provided demonstrates the implementation of a memoization function using a custom key generation approach. Here's an explanation of the code:

A counter variable is initialized to keep track of the number of times the memoized function is called.

The Memo function is defined, which takes a callback function as its argument.

Inside the Memo function, a cash object is created to store the cached results. This object will hold the unique key-value pairs for the cached values.

The Memo function returns a new function, which accepts any number of arguments using the spread operator ...args.

Within the returned function, the key is generated by joining the arguments with a hyphen - using the args.join('-') method.

The function checks if the key already exists in the cash object. If it does, it returns the cached value associated with that key.

If the key is not found in the cash object, it invokes the original callback function with the provided arguments using callback(...args). The result is assigned to the cash object with the key.

The counter variable is incremented every time the original callback function is called.

Finally, the cached result corresponding to the key is returned.

The provided example demonstrates multiple calls to the memoized function with the same arguments. The function retrieves the cached result for duplicate calls, avoiding redundant computations. The counter variable is also used to track the number of times the original function is called, illustrating the benefits of memoization in reducing function invocations.

Please note that this implementation assumes that the arguments passed to the memoized function are serializable and can be joined using a hyphen or converted into a string without any issues.


**[⬆ back to top](#table-of-contents)**

## Translation

This is also available in other languages:

- ![az](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Azerbaijan.png) **Azerbaijan**: [javidselimov/jsworldjs/tree/az-translate](https://github.com/javidselimov/jsworldjs/tree/az-translate)

**[⬆ back to top](#table-of-contents)**



