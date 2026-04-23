# Sistema de Pedidos de Restaurante 🍽️

Este proyecto modela un sistema básico de facturación en un restaurante utilizando Programación Orientada a Objetos en Python.

## Descripción

El sistema permite crear elementos del menú, agregarlos a una orden y calcular el total a pagar. Incluye un descuento básico según la cantidad de productos.

## Clases

### MenuItem (Clase base)
Atributos:
- name
- price

Método:
- calculate_price()

### Subclases

#### Beverage
- size

#### Appetizer
- is_shareable

#### MainCourse
- calories

### Order
Atributos:
- items

Métodos:
- add_item(item)
- calculate_total()

## Lógica

Cada elemento tiene un precio individual.  
La orden suma todos los elementos agregados.  
Si la orden tiene 3 o más elementos, se aplica un descuento del 10%.

## Menú

Bebidas:
- Coke
- Juice
- Coffee

Entradas:
- Nachos
- Fries
- Onion Rings

Platos principales:
- Burger
- Pizza
- Pasta
- Steak

## Diagrama UML

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
