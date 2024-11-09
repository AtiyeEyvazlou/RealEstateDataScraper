# Real Estate Data Scraper

This project scrapes real estate data from `melketabriz.ir` using unique property codes and compiles the extracted information into a structured CSV file. This tool can be useful for users who want to collect detailed data on multiple properties from the website for further analysis or reference.

## Features

- **Data Extraction**: Extracts key property details like code, region, neighborhood, area, total price, floor, room count, and additional attributes directly from the website.
- **CSV Storage**: Consolidates all extracted data into a CSV file, `combined_property_info.csv`, for easy access and further processing.
- **Error Handling**: Skips invalid codes and handles missing data by filling in blank fields as needed.

## Prerequisites

Ensure you have the following installed:

- **Python 3.x**
- **Requests**: `pip install requests`
- **BeautifulSoup4**: `pip install beautifulsoup4`
- **Pandas**: `pip install pandas`

## How to Use

### Step 1: Set Up the Project

1. Clone this repository or download the code files.
2. Make sure `combined_property_info.csv` exists in the same directory as the script.

### Step 2: Run the Script

#### Extracting Data for a Single Property Code

To fetch data for a specific property code, use the `extract_data_of_given_code()` function. For example:

```python
df = extract_data_of_given_code(25923)
add_to_excel(df)
```
#### Adding Data to CSV
Each time you run the `add_to_excel()` function with a DataFrame, the extracted data will be appended to `combined_property_info.csv`.
### Code Explanation
- `extract_data_of_given_code(given_code)`: This function generates a URL using the provided `given_code`, then fetches and parses the data. If the code is invalid, it returns `None`.
- `add_to_excel(df)`: Appends the given DataFrame `df` to `combined_property_info.csv`.
- 
### Example Usage
```python
# Specify a valid property code
property_code = 25923

# Extract data and append to CSV
df = extract_data_of_given_code(property_code)
if df is not None:
    add_to_excel(df)
```
### Notes
- The scraper is designed to work only with `melketabriz.ir` and may not function correctly if the website structure changes.
- The code assumes UTF-8 encoding for Persian (Farsi) text. Ensure your environment supports UTF-8 to avoid encoding issues.
- 
### Future Improvements
- Support for extracting data from multiple property codes at once.
- Enhanced error handling and logging.









