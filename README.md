# JavaScript Translation Repository

## Table of Contents

1. [Introduction](#introduction)
2. [Usage](#usage)
3. [Contributing](#contributing)
4. [Credits](#credits)
5. [new.target](#newtarget)
6. [Translation](#translation)

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

JavaScript is a realm of wonders and mysteries, filled with hidden gems that await discovery. One such gem is the new.target property, a special and enchanting feature that allows us to unravel the secrets of constructors and their derived classes. In this epic article, we embark on a journey through the realm of new.target, with a touch of humor and whimsical variable names that will make you chuckle.

### The Mysterious new.target Property:

Let us introduce you to our first hero, new.target. It is a property that is automatically defined within the scope of a constructor function or method when it is invoked with the new keyword. This magical property holds a reference to the constructor or class that was directly invoked, enabling us to understand the true origins of an instance.

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

In the above example, when we create an instance using new Animal(), the new.target property within the constructor will refer to the Animal constructor itself. However, if we create an instance using a derived class, such as new Dog(), the new.target property will point to the derived class instead.

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

When we create a new instance of Dog using new Dog(), the constructor is executed. As a result, both the Animal and Dog constructors are invoked in a cascading manner. With the help of new.target, we can differentiate between instances of Animal and Dog, unraveling the secret behind their creation.

The Mighty Summoner:
But wait, there's more! The power of new.target extends beyond constructors. It can also be utilized within static methods and non-constructor functions:


## Translation

This is also available in other languages:

```js

function summonAnimal() {
  if (new.target) {
    console.log('An Animal is being summoned!');
  } else {
    console.log('An Animal is appearing through unknown means!');
  }
}
```
In this peculiar function, when we call summonAnimal() directly, new.target will be undefined. However, if we use new summonAnimal(), new.target will refer to the function itself, indicating that it was invoked as a constructor.

Conclusion:
We have embarked on a thrilling adventure into the realm of new.target, discovering its magical powers and unraveling the mysteries of constructors and derived classes. With a touch of whimsy and amusing variable names, we hope this journey has brought a smile to your face.

Remember, as developers, it's not just about unraveling complexities but also embracing the joy and humor that can be found in our code. So go forth, explore, and let your code be a reflection of your imagination and wit!

Happy coding, adventurers!

**[⬆ back to top](#table-of-contents)**

- ![az](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Azerbaijan.png) **Azerbaijan**: [javidselimov/jsworldjs](https://github.com/javidselimov/jsworldjs)

**[⬆ back to top](#table-of-contents)**


