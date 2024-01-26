# Car Wash Price Wizard 🚗💦

Welcome to the Car Wash Price Wizard, a simple yet powerful tool designed to calculate car wash prices based on the type of car and selected services. This wizard-like pricing model supports individual and multiple cars, applying discounts for various service combinations and even offering rewards based on total spending.

## Table of Contents

1. [Introduction](#introduction)
2. [Usage](#usage)
3. [Functions](#functions)
    - [calculate_price](#calculate_price)
    - [calculate_total_price](#calculate_total_price)
    - [calculate_total_price_in_ghs](#calculate_total_price_in_ghs)
    - [calculate_discounted_price](#calculate_discounted_price)
4. [Reward System](#reward-system)
5. [Examples](#examples)

## Introduction

The Car Wash Price Wizard is a Python-based tool that enables users to input the type of car and selected services, providing instant calculations for the total price. Whether you have a single car or a fleet, this wizard has you covered, even offering exciting rewards for loyal customers.

## Usage

To use the Car Wash Price Wizard, simply run the Python script and follow the prompts for entering the type of car and selected services. The wizard will efficiently calculate and display the total price, including any applicable discounts or rewards.

## Functions

### calculate_price

This function takes the car type and a selected service as input and calculates the price for the service. If the car type or service is not found in the pricing dictionary, it returns `None`.

```python
def calculate_price(car_type, service_type):
    try:
        return prices[car_type.lower()][service_type.lower()]
    except KeyError:
        return None  # Handle cases where car_type or service_type is not found.
```

### calculate_total_price
This function calculates the total price for a car based on the selected services. It takes the car type and a list of selected services as input and returns the total price.
If the car type or service is not found in the pricing dictionary, it returns None

```python
def calculate_total_price(car_type, selected_services):
    try:
        total_price = sum(prices[car_type.lower()][service.lower()] for service in selected_services)
        return total_price
    except KeyError:
        return None  # Handle cases where car_type or service_type is not found
```
### calculate_total_price_in_ghs
This function calculates the total price in Ghanaian Cedis (GHS) for a car based on the selected services. It takes the car type and a list of selected services as input and returns the total price in GHS.
If the car type or service is not found in the pricing dictionary, it returns None.
```python
def calculate_total_price_in_ghs(car_type, selected_services):
    try:
        total_price_ghs = sum(prices_ghs[car_type.lower()][service.lower()] for service in selected_services)
        return total_price_ghs
    except KeyError:
        return None  # Handle cases where car_type or service_type is not found
```


calculate_discounted_price
This function calculates the discounted price based on the total price and a discount percentage. It takes the total price and discount percentage as input and returns the discounted price.

```python
def calculate_discounted_price(total_price, discount_percentage):
    discount_amount = (discount_percentage / 100) * total_price
    discounted_price = total_price - discount_amount
    return discounted_price
```

## Reward System

The car pricing model includes a reward system based on the total amount spent on cleaning services. Customers may be eligible for various rewards depending on their total spending:

- If the grand total exceeds $300, the customer wins a fuel coupon.
- If the grand total exceeds $200, the customer wins a pendrive.
- For total spending below $200, no additional rewards are provided.

The reward system is implemented to encourage customer loyalty and provide additional value for choosing our services.


## Examples
The provided examples demonstrate the usage of the Car Wash Price Wizard, including handling individual services, multiple services for a single car, and managing multiple cars with rewards based on the grand total.

Feel free to explore and adapt the code to meet your specific requirements. If you have any questions or suggestions, please reach out to me at osbornekwetey@gmail.com .

Happy pricing with the Car Wash Price Wizard! 🌟💰
