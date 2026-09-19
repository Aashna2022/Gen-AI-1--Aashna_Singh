# Python Collections Practice

This practice covers the basic usage of **Lists, Tuples, Sets, and Dictionaries** in Python.

## 1. Create a Products List

Create a list named `products` containing at least 6 product names.

```python
products = ["Laptop", "Fruit", "Headphones", "Pants", "Camera", "Smartwatch"]
```

---

## 2. Create a Product Tuple

Create a tuple named `sample_product` containing the **product name, price, and category** of one product.

```python
sample_product = ("Laptop", 999, "Electronics")
```

The tuple contains:

* Product name → `Laptop`
* Price → `999`
* Category → `Electronics`

---

## 3. Create a Category Set

Create a set containing the unique product categories.

```python
categories = [
    "Electronics",
    "Edible",
    "Electronics",
    "Wearables",
    "Photography",
    "Wearables"
]

category_set = set(categories)

print(category_set)
```

Since a set stores only unique values, duplicate categories such as `Electronics` and `Wearables` are automatically ignored.

---

## 4. Add a New Category and Demonstrate Duplicates

Use the `add()` method to add a new category.

```python
category_set.add("Accessories")

print(category_set)
```

Now try adding an existing category:

```python
category_set.add("Electronics")

print(category_set)
```

`Electronics` will not be added again because **sets do not allow duplicate values**.

---

## 5. Check Whether a Category Exists

The `in` operator can be used to check whether a category exists in a set.

```python
if "Electronics" in category_set:
    print("Category exists")
else:
    print("Category does not exist")
```

You can also directly check:

```python
print("Electronics" in category_set)   # True
print("Accessories" in category_set)   # True
print("Food" in category_set)          # False
```

---

## 6. Create a Price Dictionary

Create a dictionary containing the price of each product.

```python
price_dict = {
    "Laptop": 999,
    "Smartphone": 699,
    "Headphones": 199,
    "Smartwatch": 299,
    "Tablet": 499,
    "Camera": 799
}
```

The dictionary uses the **product name as the key** and the **price as the value**.

---

## 7. Create the Product Catalog

Using the `products` list and `price_dict`, create a list of tuples named `catalog`.

Each tuple should contain:

```text
(product name, price, category)
```

```python
categories = {
    "Laptop": "Electronics",
    "Fruit": "Edible",
    "Headphones": "Electronics",
    "Pants": "Wearables",
    "Camera": "Photography",
    "Smartwatch": "Wearables"
}

catalog = [
    (product, price_dict[product], categories[product])
    for product in products
    if product in price_dict
]

print(catalog)
```

### Output

```text
[
    ("Laptop", 999, "Electronics"),
    ("Headphones", 199, "Electronics"),
    ("Camera", 799, "Photography"),
    ("Smartwatch", 299, "Wearables")
]
```

`Fruit` and `Pants` are not included in the catalog because they do not have corresponding prices in `price_dict`.

---

## Concepts Practiced

Through these tasks, the following Python concepts were practiced:

* **List** — storing multiple product names
* **Tuple** — storing fixed product information
* **Set** — storing unique categories
* **Dictionary** — mapping products to prices
* **`add()`** — adding elements to a set
* **`in` operator** — checking membership
* **List comprehension** — creating the product catalog
* **Dictionary lookup** — retrieving product prices and categories
* **Duplicate handling** — understanding how sets ignore duplicates
