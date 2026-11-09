# Understanding Access Modifiers in TypeScript OOP

## Introduction

OOP (Object-Oriented Programming) is a programming paradigm and design pattern. In OOP, objects are the building blocks of an application. Applications contain multiple objects that work together. They control how class properties and methods can
be accessed from different parts of a program. TypeScript provides four
commonly used modifiers: `public`, `private` and
`readonly`.

## Detailed Explanation

**1. Public:**

The `public` modifier allows properties and methods to be accessed from
anywhere. It is the default access modifier in TypeScript.

**2. Private:**

The `private` modifier restricts access to a property or method within
the same class. It cannot be accessed directly outside the class or from
a subclass.

**3. Readonly:**

The `readonly` modifier prevents a property from being reassigned after
its initial assignment. It can be initialized when declared or inside
the constructor.

### Code Example

``` typescript
class Account {
  public owner: string;
  readonly id: number;
  private _balance: number;
  protected accountType: string;

  constructor(
    id: number,
    owner: string,
    balance: number,
    accountType: string
  ) {
    this.id = id;
    this.owner = owner;
    this._balance = balance;
    this.accountType = accountType;
  }

  public deposit(amount: number): void {
    this._balance += amount;
  }

  public getBalance(): number {
    return this._balance;
  }
}
const account = new Account(1, "Ashik" , 0)
console.log(account)
```

In this example, owner is publicly accessible, while _balance is private. The accountType property is accessible inside the child class. The id property cannot be reassigned after initialization

## Conclusion

Access modifiers help developers write secure, organized, and
maintainable code. Using the correct modifier protects sensitive data
and controls how different classes interact with each other.