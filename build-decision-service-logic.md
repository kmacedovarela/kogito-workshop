# 4.  Build Decision Service Logic

In this lab you are going to create a new decision logic from scratch.
The main goal is to learn how to build a decision logic taking advantage of the powerful DMN notation.

Before proceeding, you should review the following tutorial to get a first introduction to the DMN basis:

https://learn-dmn-in-15-minutes.com/

> **Warning:** This hands on is not going to give you a step by step guidance on how to craft the DMN, it's structured as a **puzzle** that you have to solve with some hints.

### Challenge description

> A **Cart** contains multiple items, an item is defined by a _category_ and a _price_. The outcome of the decision is the **Final Price** of the cart. A first discount is evaluated on every item in the cart depending on the category: for the _food_ category, the discount is 5% if the price is more than 19 otherwise 2%; for all other categories the discount is 10% if the price is more than 15. Finally, if the overall amount of the cart (after the item discount) is more than 70 then apply an extra discount of 10%. 

Start creating the file: `discount.dmn` inside the project created in the previous hands on.

**TIP:** The folder for DMN and BPMN artefacts is: `src/main/resources/`.

## 4.1. Hints

### 4.1.1. Create the Data Types

Add:

- The type for the item: `tItem` with `category` and `price`
- The type for the list of item: `tItemList`
- The type for the list of numbers 

### 4.1.2. Create the Decision Requirement Graph

- The input is the **Cart** which is a list of item.
- The output is a decision called **Final Price** which is a number.
- Create a Business Knowledge Model called **Discount**, which goal is to compute the discount for an item.

### 4.1.3. Implement the Decision Nodes

Open the **Discount** BKM:

- the input parameter is `item` typed `tItem`
- the output is a `number`
- the core of the BKM can be implemented as a decision table:
  
  1. Input clause `item.category` (string)
  2. Input clause `item.price` (number)
  3. Output clause `Discount` (number)

Open the **Final Price** decision node:

- Select `context` as logic type
- Implement the following entries:
  - `discounted prices` the list with the discounted prices
  - `discounted total` the sum of the discounted prices

#### FEEL syntax reminder:

A BKM is function, the syntax is: `Discount(item)`

The **for** loop expression iterates over lists of elements or ranges of numbers. The general syntax is:

```
for i 1 in ic return e
```

where `ic` stands for iteration context and can be:

- a list
- a range e.g. `1..10`

The function `sum` return sum of numbers:

~~~
list = [1,2,3]
sum(list) -> 6
~~~

## 4.2. Run locally the Decision Service

Start quarkus in dev mode:

~~~
mvn quarkus:dev
~~~

Create the file: `src/test/resources/dmn-test.http` with the following content:

~~~
POST http://localhost:8080/discount
Accept: application/json
Content-Type: application/json

{
  "Cart": [
    {
      "category": "electronics",
      "price": 80
    },
    {
      "category": "food",
      "price": 20
    }
  ]
}
~~~

Click on the `Send request` link to probe the DMN service.

In the result page you should spot: `"Final Price": 81.9`

**TIP:** If you haven't installed the _Rest Client_ plug-in, you can probe the DMN service through the _Swagger UI_: `http://localhost:8080/q/swagger-ui/`

## 4.3. Create a Test Scenario

## Appendix: a possible solution

> **DON'T READ THIS SECTION** try before to solve the challenge with hints provided above.
It's not important if your solution does not work as expected or it's different from the following: the philosophy of this hands on is that you can learn more from a failed attempt than from a "guided" success.

### Data types

![]({%  image_path/dmn-solution-dt.png %}){:width="600px"}

### Decision Requirement Graph

![]({%  image_path/dmn-solution-drd.png %})

### Decision Nodes

![]({%  image_path/dmn-solution-bkm.png %})

![]({%  image_path/dmn-solution-decision.png %})