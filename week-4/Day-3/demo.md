# Week 4, Day 3, Hour 1: Testing Classes in JavaScript with Jest

As we venture further into the realm of testing with Jest, this session focuses on a key aspect of JavaScript programming—classes. Testing classes and their methods presents a unique set of challenges and opportunities for ensuring our code's reliability and functionality. This hour will introduce the basics of testing JavaScript classes using Jest, providing you with the foundation to write comprehensive tests for class methods.

## Introduction to Testing Classes

Classes in JavaScript provide a means to encapsulate and organize code. They are syntactical sugar over JavaScript's existing prototype-based inheritance and offer a way to create objects and handle inheritance more comfortably.

### Why Test Class Methods?

- **Reliability**: Ensure each method performs as expected under various conditions.
- **Maintenance**: Facilitate easier code maintenance and refactoring by catching breaks immediately.
- **Documentation**: Serve as live documentation for how class methods are supposed to work.

## Setting Up Jest for Testing Classes

Assuming you've already set up Jest in your Node.js project from previous sessions, let's proceed to write tests for a simple class. If you need to review the setup process, please refer to Hour 1 of Day 1.

## Writing Unit Tests for Class Methods

Consider a basic `Calculator` class with methods for addition, subtraction, multiplication, and division.

```js
// calculator.js
class Calculator {
  add(a, b) {
    return a + b;
  }

  subtract(a, b) {
    return a - b;
  }

  multiply(a, b) {
    return a * b;
  }

  divide(a, b) {
    if (b === 0) throw new Error('Division by zero');
    return a / b;
  }
}

module.exports = Calculator;
```

```js
// calculator.test.js
const Calculator = require('./calculator');

describe('Calculator', () => {
  let calculator;

  beforeEach(() => {
    calculator = new Calculator();
  });

  it('adds two numbers', () => {
    expect(calculator.add(1, 2)).toBe(3);
  });

  it('subtracts two numbers', () => {
    expect(calculator.subtract(5, 2)).toBe(3);
  });

  it('multiplies two numbers', () => {
    expect(calculator.multiply(2, 3)).toBe(6);
  });

  it('divides two numbers', () => {
    expect(calculator.divide(6, 2)).toBe(3);
  });

  it('throws an error when dividing by zero', () => {
    expect(() => calculator.divide(5, 0)).toThrow('Division by zero');
  });
});
```

## Introduction to Mocking API Calls with Jest

Before we dive deeper into class testing, let's explore how to test functions that perform API calls using Jest. This will be demonstrated by mocking requests to a Pokémon API.

### Setting Up for API Testing

Create `pokemonApi.js` and `pokemonApi.test.js` to demonstrate how to mock API calls with Jest.

```js
// pokemonApi.js
const axios = require('axios');

const getPokemon = async (pokemonName) => {
  try {
    const response = await axios.get(
      `https://pokeapi.co/api/v2/pokemon/${pokemonName}`,
    );
    return response.data;
  } catch (error) {
    throw error;
  }
};

module.exports = { getPokemon };
```

```js
// pokemonApi.test.js
const { getPokemon } = require('./pokemonApi');
const axios = require('axios');

jest.mock('axios');

describe('getPokemon', () => {
  test('successfully retrieves Pikachu data', async () => {
    const mockPokemon = { id: 25, name: 'pikachu' };
    axios.get.mockResolvedValue({ data: mockPokemon });

    const result = await getPokemon('pikachu');
    expect(result).toEqual(mockPokemon);
  });

  test('handles errors for network issues or Pokémon not found', async () => {
    axios.get.mockRejectedValue(new Error('Network error'));

    await expect(getPokemon('pikachu')).rejects.toThrow('Network error');
  });
});
```

## Conclusion

Testing classes in JavaScript is an essential skill for ensuring the correctness and reliability of your object-oriented code. By following the principles outlined in this session, you can write effective unit tests for your classes, ensuring each method behaves as expected under various conditions. Remember, the key to effective class testing is understanding the behavior of each method and its interactions within the class.

<!-- ! Hour 2 -->

# Week 4, Day 3, Hour 2: Building and Testing a Complex Class in JavaScript with Jest

After learning the basics of testing simple class methods, let's move on to a more complex example. This hour, we will construct a class that represents a real-world object with multiple methods and demonstrate how to comprehensively test it using Jest. Our example will be a shopping cart class that can add items, remove items, and calculate the total cost, showcasing the intricacies of testing more complex behaviors.

## Building a Complex Class

Consider a `ShoppingCart` class that includes methods for adding items, removing items, and calculating the total price. Each item in the cart will have a name, price, and quantity.

### Step 1: Define the Class

First, we create the `ShoppingCart` class:

```js
// ShoppingCart.js
class ShoppingCart {
  constructor() {
    this.items = [];
  }

  addItem(item) {
    this.items.push(item);
  }

  removeItem(itemName) {
    this.items = this.items.filter((item) => item.name !== itemName);
  }

  calculateTotal() {
    return this.items.reduce((total, item) => {
      return total + item.price * item.quantity;
    }, 0);
  }
}

module.exports = ShoppingCart;
```

### Step 2: Implement the Test Cases

Now, we'll write Jest tests for each method of the `ShoppingCart` class, ensuring each functionality is correctly implemented and interacts as expected with other parts of the class.

```js
// ShoppingCart.test.js
const ShoppingCart = require('./ShoppingCart');

describe('ShoppingCart', () => {
  let cart;

  beforeEach(() => {
    cart = new ShoppingCart();
  });

  it('adds items to the cart', () => {
    cart.addItem({ name: 'Apple', price: 1.0, quantity: 3 });
    expect(cart.items.length).toBe(1);
  });

  it('removes items from the cart', () => {
    cart.addItem({ name: 'Banana', price: 0.5, quantity: 4 });
    cart.removeItem('Banana');
    expect(cart.items.length).toBe(0);
  });

  it('calculates the total price of items in the cart', () => {
    cart.addItem({ name: 'Apple', price: 1.0, quantity: 3 });
    cart.addItem({ name: 'Banana', price: 0.5, quantity: 4 });
    expect(cart.calculateTotal()).toBe(5.0);
  });

  it('handles adding and removing multiple items', () => {
    cart.addItem({ name: 'Apple', price: 1.0, quantity: 3 });
    cart.addItem({ name: 'Banana', price: 0.5, quantity: 4 });
    cart.removeItem('Apple');
    cart.addItem({ name: 'Orange', price: 0.75, quantity: 2 });
    expect(cart.calculateTotal()).toBe(3.5);
  });
});
```

## Conclusion

This session has introduced you to the challenges and techniques involved in building and testing a complex class using Jest. By designing a `ShoppingCart` class and writing tests for its various methods, you have practiced ensuring that your classes work correctly under different scenarios and interact properly with their internal state. Remember, comprehensive testing is crucial for building reliable applications, especially as the complexity of your classes and methods increases.
