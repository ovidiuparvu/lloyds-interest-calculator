# Lloyds bank interest calculator

This repository contains prototype improperly tested code.

## How to download statement summary for a year?

Steps:
1. Log into your Lloyds internet banking account.
2. Click the "View statement" button to the right of the relevant bank account.
3. Hover the mouse over the "Statement options" dropdown.
4. Click the "Export transactions (CSV,QIF)" button.
5. Choose the desired date range.
6. From the "Format" dropdown select the "Internet banking text/spreadsheet" option.
7. Click the "Export" button.
8. Run the following against the exported file in order to determine the interest for your bank account for different days.
```bash
echo "Source,Amount (GBP),Date" >interest.csv
cat "47160360_20240113_0121.csv" | grep INTEREST | awk -F, '{ print "Bank Account XYZ,"$7","$1 }' >>interest.csv
```
