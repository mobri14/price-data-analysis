# price-data-analysis
price-data-analysis

# Price Data Analysis

This project calculates the Simple Moving Average (SMA) and Exponential Moving Average (EMA) for given price data and outputs the results in an HTML table format.



### Explanations for the Python Code (`main.py`)

```python
import pandas as pd

# Assume your price data is in a DataFrame with a column named 'Close'
data = {
    'Close': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
}
df = pd.DataFrame(data)

# Calculate SMA and EMA
# SMA (Simple Moving Average) with a window of 3
# EMA (Exponential Moving Average) with a window of 3
df['SMA'] = df['Close'].rolling(window=3).mean()  # Calculate SMA
df['EMA'] = df['Close'].ewm(span=3, adjust=False).mean()  # Calculate EMA

# Convert DataFrame to HTML
html_table = df.to_html(index=False)

# Write HTML to file
with open("data_table.html", "w") as f:
    f.write(f"""
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Data Table</title>
        <style>
            table {{
                width: 50%;
                border-collapse: collapse;
                margin: 20px auto;
            }}
            th, td {{
                border: 1px solid #ddd;
                padding: 8px;
                text-align: center;
            }}
            th {{
                background-color: #f2f2f2;
            }}
        </style>
    </head>
    <body>
        <h2 style="text-align:center;">Price Data and Technical Calculations</h2>
        {html_table}
    </body>
    </html>
    """)

print("HTML file has been successfully created.")
```

#### Explanations:
- **Importing Library:** First, we import `pandas` for data manipulation.
- **Creating DataFrame:** Price data is stored in a dictionary and converted into a DataFrame.
- **Calculating SMA and EMA:** Simple Moving Average (SMA) and Exponential Moving Average (EMA) are calculated using `rolling` and `ewm` functions.
- **Converting to HTML:** The DataFrame is converted into HTML format for display in a web page.
- **Writing to HTML File:** The generated HTML content is written to a file named `data_table.html`.
- **Success Message:** Finally, a success message is printed to the console.

---

### Explanations for the HTML Code (Part of `main.py`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Data Table</title>
    <style>
        table {
            width: 50%;
            border-collapse: collapse;
            margin: 20px auto;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <h2 style="text-align:center;">Price Data and Technical Calculations</h2>
    {html_table}
</body>
</html>
```

#### Explanations:
- **HTML Definition:** The overall structure of the HTML page includes `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>` tags.
- **Meta Data:** Includes metadata for character encoding and viewport settings for responsiveness.
- **Page Title:** The title of the page that appears in the browser's title bar.
- **Styles:** CSS styles for the table, including width, borders, and background colors for headers.
- **Table Title:** A title for the data table that is centered on the page.
- **Table Content:** A placeholder for the HTML content of the table created from the DataFrame.

---

### Adding Explanations to `README.md`

You can also create a `README.md` file that includes an overview of the project and instructions on how to use it. For example:

```markdown
# Price Data Analysis

This project calculates the Simple Moving Average (SMA) and Exponential Moving Average (EMA) for given price data and outputs the results in an HTML table format.

## Requirements

- Python 3.x
- pandas

## How to Run

1. Clone the repository.
2. Navigate to the project directory.
3. (Optional) Create a virtual environment:
   ```bash
   python -m venv env
   ```
4. Install the required packages:
   ```bash
   pip install pandas
   ```
5. Run the script:
   ```bash
   python main.py
   ```

The HTML file `data_table.html` will be generated in the project directory.
```

### Notes

