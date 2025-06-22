# Currency_converter
As part of my internship at StaxTech, I developed a mini-project titled “Currency Converter Using Python”. The aim of this project was to create a simple, functional tool that can convert amounts from one currency to another using predefined rates or live exchange data.
The project was implemented using Python, utilizing core programming concepts such as user input handling, conditional logic, and functions. In the advanced version, I integrated a public API (exchangerate.host) to fetch real-time currency exchange rates using the requests library.

# Simple Currency Converter

def convert_currency(amount, from_currency, to_currency):
    # Sample exchange rates
    rates = {
        "USD": {"INR": 83.0, "EUR": 0.92},
        "INR": {"USD": 0.012, "EUR": 0.011},
        "EUR": {"USD": 1.09, "INR": 90.0}
    }

    if from_currency in rates and to_currency in rates[from_currency]:
        converted_amount = amount * rates[from_currency][to_currency]
        return round(converted_amount, 2)
    else:
        return "Conversion not available."

# User input
print("Simple Currency Converter")
amount = float(input("Enter amount: "))
from_curr = input("From currency (USD, INR, EUR): ").upper()
to_curr = input("To currency (USD, INR, EUR): ").upper()

result = convert_currency(amount, from_curr, to_curr)

print(f"\n{amount} {from_curr} = {result} {to_curr}")
# User output
Simple Currency Converter
Enter amount: 100
From currency (USD, INR, EUR): USD
To currency (USD, INR, EUR): INR

100 USD = 8300.0 INR
