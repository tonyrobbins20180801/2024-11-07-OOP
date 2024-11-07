# 2024-11-07-OOP

OOP stands of **Object Oriented Programming **

OOP revolves around creating structures called objects
These objects are called instances of classes and a class is "blueprint" that defines the properties and methods of each objects.

The OOP is very common structure.  THere are programming language that are completely OOP-dependant, like JAVA or C#. In those languages everything needs to be a class.

In JS that's not the case and we can create code wherever we would like to. but in order to make developers of say C# happy, we can create and use classes in JS as well.

Support for classes came with ES6.

Class syntax looks like this. 

```js
class Animal {
    constructor (name, species) {
        this.name = name;
        this.species = species
    }
    speak ( ) {
        console.log ( ` The animal, ${this.name} makes a sound `);
    }
}
```

Explanation of above:

- **class**: reserved keyword in JS, only to be used when creating classes.

- **Animal**: the name of the class, convention is to use PascalCase. Capital letter in the beginning and on every "new" word.

-**constructor**: is the start method that is invoked when create a new instance of the class. The constructur usually takes some paramneeter but this is not mandatory. It all depends on how the class is defined.  But if the class has some propertied that need values, they must be passed in to the constructor.

-**properties**: in this case, the name and the soecies are propertoies on the class. They can be mandatory 

-**speak**: this is a method that exists on the class. it's a method that is shared by all the instances of the class.

```js
class Animal {
    constructor (name, species) {
        this.name = name;
        this.species = species
    }
    speak ( ) {
        console.log ( ` The animal, ${this.name} makes a sound `);
    }
}

const myDog = new Animal("Fido", "Labrador");
const myOtherDock = new Animal ("Sigge", "Tax");
const myCat = new Animal( "Mozart", "Russian Blue");

console.log(myDog.name); // Fido
console.log(myOtherDock.name); // Sigge
console.log(myCat.name); // Mozart


```

### Encapsulation

Encapsulation refers to hiding the internal representation of an instance of a class while (if we want ) providing controlled access through methods. This can be done with something called getters, setters or public methods.
Things that are private in JS classes uses a prefix #.


```js
class Animal {

    #name; // The # indicates a private property
    #species; // The # indicates a private property
    constructor (name, species) {
        this.#name = name; 
        this.#species = species 
    }
    speak ( ) {
        console.log ( `The animal, ${this.name} makes a sound `);
    }
}

const myDog = new Animal ("Fido", "Labrador");

console.log (myDog.getName());
myDog.speak();


```