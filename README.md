def calculate_discount(price, discount_percent):
    """
    Calculate the final price after applying a discount.
    Applies the discount only if it is 20% or higher.

    Parameters:
    - price (float): The original price of the item.
    - discount_percent (float): The discount percentage.

    Returns:
    - float: The final price after discount (if applied), or the original price.
    """
    if discount_percent >= 20:
        discount_amount = price * (discount_percent / 100)
        return price - discount_amount
    else:
        return price

# Prompt the user for input
try:
    price = float(input("Enter the original price of the item: "))
    discount_percent = float(input("Enter the discount percentage: "))

    final_price = calculate_discount(price, discount_percent)

    if discount_percent >= 20:
        print(f"Discount applied. The final price is: ${final_price:.2f}")
    else:
        print(f"No discount applied. The price remains: ${final_price:.2f}")
except ValueError:
    print("Invalid input. Please enter numeric values for price and discount percentage.")
