#program to calculate personal income task 
status = int(input("Enter filing status (0-Single, 1-Married Joint, 2-Married Separate, 3-Head): "))
income = float(input("Enter taxable income: "))

tax = 0

if status == 0:  # Single 
    if income <= 8350:
        tax = income * 0.10
    elif income <= 33950:
        tax = 8350 * 0.10 + (income - 8350) * 0.15
    elif income <= 82250:
        tax = 8350 * 0.10 + 25600 * 0.15 + (income - 33950) * 0.25
    else:
        tax = 8350 * 0.10 + 25600 * 0.15 + 48300 * 0.25 + (income - 82250) * 0.28

elif status == 1:  # Married filing jointly/qualifying widow(er)
    if income <= 16700:
        tax = income * 0.10
    elif income <= 67900:
        tax = 16700 * 0.10 + (income - 16700) * 0.15
    elif income <= 137050:
        tax = 16700 * 0.10 + 51200 * 0.15 + (income - 67900) * 0.25
    else:
        tax = 16700 * 0.10 + 51200 * 0.15 + 69150 * 0.25 + (income - 137050) * 0.28

elif status == 2:  # Married filing separately
    if income <= 8350:
        tax = income * 0.10
    elif income <= 33950:
        tax = 8350 * 0.10 + (income - 8350) * 0.15
    elif income <= 68625:
        tax = 8350 * 0.10 + 25600 * 0.15 + (income - 33950) * 0.25
    else:
        tax = 8350 * 0.10 + 25600 * 0.15 + 34675 * 0.25 + (income - 68625) * 0.28

elif status == 3:  # Head of household
    if income <= 11950:
        tax = income * 0.10
    elif income <= 45500:
        tax = 11950 * 0.10 + (income - 11950) * 0.15
    elif income <= 117450:
        tax = 11950 * 0.10 + 33550 * 0.15 + (income - 45500) * 0.25
    else:
        tax = 11950 * 0.10 + 33550 * 0.15 + 71950 * 0.25 + (income - 117450) * 0.28

else:
    print("Invalid filing status")
    exit()

print("Total tax is: $", round(tax, 2))
