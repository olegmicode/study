### What's the output?

```
    for (var i = 0; i < 3; i++) {
      setTimeout(() => console.log(i), 0);
    }

    for (let i = 0; i < 3; i++) {
      setTimeout(() => console.log(i), 0);
    }

```

```
    function sayHi() {
      console.log(name);
      console.log(age);
      var name = 'Lydia';
      let age = 21;
    }

    sayHi();
```

```
    const shape = {
      radius: 10,
      diameter() {
        return this.radius * 2;
      },
      perimeter: () => 2 * Math.PI * this.radius,
    };

    console.log(shape.diameter());
    console.log(shape.perimeter());
```

```
    +true;
    !'Lydia';
```

```
    let c = { greeting: 'Hey!' };
    let d;

    d = c;
    c.greeting = 'Hello';
    console.log(d.greeting);
```

```
    class Chameleon {
      static colorChange(newColor) {
        this.newColor = newColor;
        return this.newColor;
      }

      constructor({ newColor = 'green' } = {}) {
        this.newColor = newColor;
      }
    }

    const freddie = new Chameleon({ newColor: 'purple' });
    console.log(Chameleon.colorChange('orange'));
    console.log(freddie.newColor);
    console.log(freddie.colorChange('green'));
    console.log(freddie.newColor);
```

```
    function bark() {
      console.log('Woof!');
    }

    bark.animal = 'dog';
```

```
    function Person(firstName, lastName) {
      this.firstName = firstName;
      this.lastName = lastName;
    }

    const member = new Person('Lydia', 'Hallie');
    Person.getFullName = function() {
      return `${this.firstName} ${this.lastName}`;
    };

    console.log(member.getFullName());
```

```
    function sum(a, b) {
      return a + b;
    }

    sum(1, '2');
```

```
    function tag(strings, ...expressions) {
      console.log(strings)
      console.log(expressions)
    }

    tag`This ${true} and ${false} and ${100} interpolated inside.`
```

```
    function checkAge(data) {
      if (data === { age: 18 }) {
        console.log('You are an adult!');
      } else if (data == { age: 18 }) {
        console.log('You are still an adult.');
      } else {
        console.log(`Hmm.. You don't have an age I guess`);
      }
    }

    checkAge({ age: 18 });
```

```
    function getAge(...args) {
      console.log(typeof args);
    }

    getAge(21);
```

```
    const obj = { 1: 'a', 2: 'b', 3: 'c' };
    const set = new Set([1, 2, 3, 4, 5]);

    obj.hasOwnProperty('1');
    obj.hasOwnProperty(1);
    set.has('1');
    set.has(1);
```

```
    const a = {};
    const b = { key: 'b' };
    const c = { key: 'c' };

    a[b] = 123;
    a[c] = 456;

    console.log(a[b]);
```

```
    <div onclick="console.log('div')">
      <p onclick="console.log('p')">
        Click here!
      </p>
    </div>
```

```
    const numbers = [1, 2, 3];
    numbers[10] = 11;
    console.log(numbers.length);
```

```
    (() => {
      let x, y;
      try {
        throw new Error();
      } catch (x) {
        (x = 1), (y = 2);
        console.log(x);
      }
      console.log(x);
      console.log(y);
    })();
```

```
    parseInt('7*6', 10)
```

```
    function Car() {
      this.make = 'Lamborghini';
      return { make: 'Maserati' };
    }

    const myCar = new Car();
    console.log(myCar.make);
```

```
    const person = { name: 'Lydia' };

    Object.defineProperty(person, 'age', { value: 21 });

    console.log(person);
    console.log(Object.keys(person));
```

```
    const settings = {
      username: 'lydiahallie',
      level: 19,
      health: 90,
    };

    const data = JSON.stringify(settings, ['level', 'health']);
```

```
    [1, 2, 3, 4].reduce((x, y) => console.log(x, y));
```

```
    // index.js
    console.log('running index.js');
    import { sum } from './sum.js';
    console.log(sum(1, 2));

    // sum.js
    console.log('running sum.js');
    export const sum = (a, b) => a + b;
```

```
    function getItems(fruitList, ...args, favoriteFruit) {
      return [...fruitList, ...args, favoriteFruit]
    }

    getItems(["banana", "apple"], "pear", "orange")
```

```
    function nums(a, b) {
      if (a > b) console.log('a is bigger');
      else console.log('b is bigger');
      return
      a + b;
    }

    console.log(nums(4, 2));
    console.log(nums(1, 2));
```

```
    const output = `${[] && 'Im'}possible!
    You should${'' && `n't`} see a therapist after so much JavaScript lol`;
    console.log(output);
```

```
    function compareMembers(person1, person2 = person) {
      if (person1 !== person2) {
        console.log('Not the same!');
      } else {
        console.log('They are the same!');
      }
    }

    const person = { name: 'Lydia' };

    compareMembers(person);
```

```
    const person = {
      name: 'Lydia',
      age: 21,
    };

    const changeAge = (x = { ...person }) => (x.age += 1);
    const changeAgeAndName = (x = { ...person }) => {
      x.age += 1;
      x.name = 'Sarah';
    };

    changeAge(person);
    changeAgeAndName();

    console.log(person);
```

```
    const randomValue = 21;

    function getInfo() {
      console.log(typeof randomValue);
      const randomValue = 'Lydia Hallie';
    }

    getInfo();
```

```
    const myPromise = Promise.resolve(Promise.resolve('Promise'));

    function funcOne() {
      setTimeout(() => console.log('Timeout 1!'), 0);
      myPromise.then(res => res).then(res => console.log(`${res} 1!`));
      console.log('Last line 1!');
    }

    async function funcTwo() {
      const res = await myPromise;
      console.log(`${res} 2!`)
      setTimeout(() => console.log('Timeout 2!'), 0);
      console.log('Last line 2!');
    }

    funcOne();
    funcTwo();
```

```
    const person = {
      name: 'Lydia Hallie',
      hobbies: ['coding'],
    };

    function addHobby(hobby, hobbies = person.hobbies) {
      hobbies.push(hobby);
      return hobbies;
    }

    addHobby('running', []);
    addHobby('dancing');
    addHobby('baking', person.hobbies);

    console.log(person.hobbies);
```

```
    const fruit = ['🍌', '🍊', '🍎']

    fruit.slice(0, 1)
    fruit.splice(0, 1)
    fruit.unshift('🍇')

    console.log(fruit)
```

```
    const animals = {};
    let dog = { emoji: '🐶' };
    let cat = { emoji: '🐈' };

    animals[dog] = { ...dog, name: "Mara" };
    animals[cat] = { ...cat, name: "Sara" };

    console.log(animals[dog])
```

```
    const user = {
      email: "my@email.com",
      updateEmail: email => {
        this.email = email
      }
    }

    user.updateEmail("new@email.com")
    console.log(user.email)
```

```
    const promise1 = Promise.resolve('First')
    const promise2 = Promise.resolve('Second')
    const promise3 = Promise.reject('Third')
    const promise4 = Promise.resolve('Fourth')

    const runPromises = async () => {
      const res1 = await Promise.all([promise1, promise2])
      const res2  = await Promise.all([promise3, promise4])
      return [res1, res2]
    }

    runPromises()
      .then(res => console.log(res))
      .catch(err => console.log(err))
```

**Explain about event propagation: capturing, bubbling, target in html dom.**

**What are the differences between sessionStorage and localStorage**

**Given a nested array, write a function to flatten the array.**
```
    function flatten(arr) {

    }

    flatten([1, 2, [3, 4, [5, 6, [7]], [8, 9]], [10, 11]])
```

**What's the difference between code blocks below? Do they have the same output?**
```
    function makeArmy() {
      let shooters = [];
      let i = 0;

      while (i < 10) {
        shooters.push(function() {
          console.log(i);
        })
        i++;
      }

      return shooters;
    }

    let army = makeArmy();
    for (const soldier of army) {
      soldier()
    }
```

```
    function makeArmy() {
      let shooters = [];

      for (let i=0;i<10;i++) {
        shooters.push(function() {
          console.log(i);
        })
      }
      
      return shooters;
    }

    let army = makeArmy();
    for (const soldier of army) {
      soldier()
    }
```