---
title: "TypeScript : Classes vs Interfaces"
date: 2020-11-30
categories:
  - blog
tags: 
  - TypeScript
  - classes
  - interfaces
  - english
---

As part of my web developer career path, I have just started to learn TypeScript. One of the first issues I have encountered was to differentiate classes from interfaces and understand the advantage of using them together. 


Here I share with you my understanding of it and a short example I came across to illustrate my answer. 


# Classes vs Interfaces

## Classes

​In JavaScript classes have been introduced with ECMAScript 2015 and enable programmers to develop using the object-oriented approach - JavaScript initially following a prototypal approach. 


A class is a blueprint or a plan that contains properties and methods to create an object. This object will share the same set of properties and methods. 


In TypeScript, we can use these object-oriented class-based techniques.

### Basic example

See the example below where the class `Pet` will create objects containing 2 properties (`species` and `color`) and one method `display()`.

```ts
// Pet.ts
​
class Pet {
  constructor (public species: string, public color: string) {
    this.species = species;
    this.color = color;
  };
​
  display(): string {
    return `I have a ${this.color} ${this.species}.`
  };
};
```
​
We can create an object `cat` that will share the same configuration as `Pet` with the values `species = cat` and `color = white` and whose method `display()` will return `I have a white cat.`

```ts
const cat = new Pet('cat', 'white');
console.log(cat.display()); // I have a white cat.
```

### Inheritance

As stated above, in TypeScript, we can use object-oriented patterns such as being able to extend existing classes to create new classes. We can use the inheritance feature. 

​
If we go back to our example, we are going to instantiate the class `Pet` by creating a class `Cat` that will inherit from `Pet` (parent) but also have its own methods. 

​
`super()` will call the parent constructor. 

​
Our `Cat` will be a special `Pet` that will always be from the cat species and will have access to the `display()` method. We will also give our `Cat` his own method `meow()` which is not available into `Pet`. 

```ts
// Cat.ts
class Cat extends Pet {
  constructor(public color: string) {
    super(color, 'Cat');
  }
  meow(): string {
    return 'meow! meow!';
  }
}
```
​
Now to create a cat we just need to specify the color.
​
```ts
const blackCat = new Cat('black');
console.log(blackCat.display()); // I have a black Cat
console.log(blackCat.meow()); // 'meow! meow!'
```

## Interfaces

In TypeScript, we use an interface to define the shape of an entity. It acts like a contract that states the requirements the entity should follow (what properties and methods are expected and their type).
​

### Defining the shape of an entity

In this first case, the interface will ensure that the data type or the shape of a variable matches the value assigned to it. 

​
In the example below, we have created a function `myPet()` whose arguments must comply with the properties and types defined in the interface `Pet`. 

​
Thus when we call the function `myPet()` to create a variable `myCat`, we have to provide an object that will contain 2 attributes `species` and `color` of type `string`. Otherwise, TypeScript compiler will return an error. 
​
```ts
// MyPet.ts
interface Pet {
  species: string;
  color: string;
}
const myPet = (pet: Pet): string => {
  return `I have a ${pet.color} ${pet.species}.`;
};
const myCat = myPet({ species: 'cat', color: 'black' });
console.log(myCat); // I have a black cat.

const myCat = myPet({ species: 1, color: 2 }); // Typescript error
```

### Using Class with Interface

An interface provides a standard structure that a class implements. It defines properties and methods but does not describe the implementation of them. It is like a contract that specifies the basic list of what needs to be done but not how to do it. 

​
The advantage, I understand, of using classes that implement interfaces is mainly to be able to use the same code (methods and/or properties) on objects from different classes. Let's see the example below. 

​
First, we create 2 interfaces `Animal` and `Pet`.

```ts
interface Animal {
  species: string;
  color: string;
  display(): string;
}
interface Pet {
  address: string;
  pet(): string;
}
```

We then create a class `Cat` that implements `Animal` and `Pet`. Thus it must contain at least the properties `species`, `color` and `address` and the methods `display()` and `pet()`. But it can also contain its own properties and methods such as the `meow()` method.
​
```ts
class Cat implements Animal, Pet {
  species: string;
  constructor(public color: string, public address: string) {
    this.species = 'cat';
    this.color = color;
  }
  display(): string {
    return `I am a ${this.color} ${this.species}. I am an animal and more precisly a pet.`;
  }
  pet(): string {
    return 'Please pet me!';
  }
  meow(): string {
    return 'meow! meow!';
  }
}
```

In addition, we create another class `Tiger` that only implements `Animal`. Since a tiger is not a pet, we don't need to define the `address` property and `pet()` method.  

```ts
class Tiger implements Animal {
  species: string;
  constructor(public color: string) {
    this.species = 'tiger';
    this.color = color;
  }
  display(): string {
    return `I am a ${this.color} ${this.species}. I am an animal but not a Pet so you can't pet me.`;
  }
}
```

Let's create two variables `myCat` and `whiteTiger` from the classes defined above. These variables are respectively instances of the classes `Cat` and `Tiger` and as such: 
​

- `myCat` complies with the interfaces `Animal` and `Pet`
- `whiteTiger` complies with the interface `Animal`

```ts
const myCat = new Cat('black', 'appartment');
const whiteTiger = new Tiger('white');
```

Now, we can create a function `petThePet()` to return the `pet()` method. We tell TypeScript that the arguments of this function must be of `Pet` type. As such, we can access the `pet()` method defined above. 

​
Thus, when we call this function with `myCat` as parameter, the function will successfully return `Please pet me!`. 

​
However, if we call the function with `whiteTiger` as parameter, as `whiteTiger` is an instance of the class `Tiger` which only implements `Animal`, the TypeScript compiler will return an error.
​

```ts
const petThePet = (pet: Pet) => {
  return pet.pet();
};
petThePet(myCat); // Please pet me!
petThePet(whiteTiger); // Argument of type 'Tiger' is not assignable to parameter of type 'Pet'. Type 'Tiger' is missing the following properties from type 'Pet': address, pet
```

​
Alternatively, we can create a function `describeAnimal()` that will expect a parameter of type `Animal` and return the result of the `display()` method. 

​
If we call this function with `myCat` and `whiteTiger`, which are both instances of classes that implement `Animal`, we can access the `display()` method and successfully return the expected string.
​

```ts
const describeAnimal = (animal: Animal) => {
  return animal.display();
};
describeAnimal(myCat); // I am a black cat. I am an animal and more precisly a pet.
describeAnimal(tiger); // I am a white tiger. I am an animal but not a Pet so you can't pet me.
```

## Conclusion

To summarize, an interface is a way to define the specifications of an entity. It can be used to define the *shape* of a variable of any primitive data (string, number etc.) or structural (object, function) type. It can be implemented by classes and functions. It will only define what needs to be done. 

​
A class, however, is a plan that contains properties and methods that enables to create an object that will share the same set of attributes. Comparing to the interface, the class will define what needs to be done **and** describe how to do it. 

​
The combined usage of interfaces and classes enable to code in an effective way. It allows to mutualize functions and variables between objects from different classes but that share some common specificities. 

## Resources

- [The TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [Ultimate Courses - Classes vs Interfaces](https://ultimatecourses.com/blog/classes-vs-interfaces-in-typescript)
- [Medium article - Typescript : class vs interface](https://medium.com/front-end-weekly/typescript-class-vs-interface-99c0ae1c2136) 


Claire