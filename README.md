# Financial Audit Data Extraction Script

This script is designed to extract current year amounts from annual reports in PDF format and generate a CSV file with the extracted data.

## Prerequisites

- Python 3.x installed on your system.
- `PyMuPDF` library (`fitz`) for handling PDF files. Install it using:
  ```bash
  pip install pymupdf
  ```

## Usage

1. Place the PDF files you want to extract data from in a directory specified by the `inputfolder` variable in the script.
2. Run the script using Python:
   ```bash
   python financial-data-extract.py
   ```
3. The extracted data will be saved in a CSV file named `output file path.csv`.

## Script Details

The script performs the following steps:

1. **Imports**: Imports necessary libraries such as `fitz` for PDF handling, `re` for regular expressions, `os` for file operations, and `csv` for writing to CSV files.
2. **Configuration**: Specifies the input folder containing PDF files and the output CSV file path.
3. **Functions**:
   - `string_to_integer_or_float`: Converts a string to an integer or float.
   - `find_tables`: Extracts tables from the text using regular expressions.
4. **Line Items**: Defines line items for balance sheets, profit and loss statements, and cash flow statements with their corresponding regex patterns.
5. **PDF Processing**:
   - Loops through all PDF files in the input folder.
   - Extracts fund names from file names.
   - Reads text from each PDF page and concatenates it.
   - Extracts tables using regular expressions.
6. **Data Extraction**:
   - Iterates through defined line items to extract corresponding amounts from the extracted tables.
7. **Output Generation**: Writes the extracted data to a CSV file.

## Improvements

- **Error Handling**: Add error handling for missing PDF files or read errors.
- **Logging**: Implement logging to track execution progress and issues.
- **Configuration Management**: Use a configuration file (e.g., JSON) for settings.
- **Code Comments**: Add more comments for better readability.
- **Unit Testing**: Write unit tests to ensure the script functions correctly.

## Contributing

Contributions are welcome! Please fork the repository, make your changes, and submit a pull request.
