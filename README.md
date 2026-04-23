# Restaurant Order System 🍽️

This project models a simple restaurant billing system using Object-Oriented Programming in Python.

## 📌 Description

The system allows creating menu items, adding them to an order, and calculating the total bill. It also includes a basic discount depending on the number of items.

---

## 🧱 Classes

### MenuItem (Base Class)
- Attributes:
  - name
  - price
- Method:
  - calculate_price()

### Subclasses

#### Beverage
- Extra attribute: size

#### Appetizer
- Extra attribute: is_shareable

#### MainCourse
- Extra attribute: calories

### Order
- Stores a list of MenuItem objects
- Methods:
  - add_item(item)
  - calculate_total()

---

## ⚙️ Logic

- Each item has a price
- The order sums all items
- If the order has 3 or more items → **10% discount applied**

---

## 🍔 Menu (10 items)

**Beverages:**
- Coke
- Juice
- Coffee

**Appetizers:**
- Nachos
- Fries
- Onion Rings

**Main Courses:**
- Burger
- Pizza
- Pasta
- Steak

---

## 📊 UML Diagram

```mermaid
classDiagram

class MenuItem {
    -name: str
    -price: float
    +calculate_price(): float
}

class Beverage {
    -size: str
}

class Appetizer {
    -is_shareable: bool
}

class MainCourse {
    -calories: int
}

class Order {
    -items: list
    +add_item(item: MenuItem)
    +calculate_total(): float
}

MenuItem <|-- Beverage
MenuItem <|-- Appetizer
MenuItem <|-- MainCourse
Order "1" --> "*" MenuItem
