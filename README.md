# CodeAlpha_StockPortfolio
Python_programming_task_2
# Python_programming_task_2
def track_portfolio():
    stock_prices = {
        "AAPL": 180.0,
        "TSLA": 250.0,
        "GOOGL": 140.0,
        "AMZN": 130.0,
        "MSFT": 330.0
    }
    print("Welcome to the Stock Portfolio Tracker!")
    print("Available stocks:", ", ".join(stock_prices.keys()))
    total_investment = 0.0
    # Main input loop
    while True:
        stock_name = input("\nEnter the stock ticker (or type 'done' to finish): ").upper().strip()
        if stock_name == 'DONE':
            break 
        if stock_name not in stock_prices:
            print("Invalid stock. Please choose from the available list.")
            continue
        try:
            quantity = int(input(f"How many shares of {stock_name} did you buy? "))
            if quantity < 0:
                print("Please enter a positive number.")
                continue
        except ValueError:
            print("Invalid input. Please enter a whole number.")
            continue
        cost = stock_prices[stock_name] * quantity
        total_investment += cost
        print(f"Added {quantity} shares of {stock_name} for ${cost:.2f}.")
    print(f"\n--- Portfolio Summary ---")
    print(f"Your total investment value is: ${total_investment:.2f}")
# Output loop
if __name__ == "__main__":
    track_portfolio()