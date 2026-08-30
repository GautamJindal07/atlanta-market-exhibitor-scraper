# Atlanta Market Exhibitor Data Scraper

A Python-based Selenium web scraper designed to extract exhibitor information from dynamically rendered Atlanta Market pages.

## Overview

This project automates the extraction of information from Atlanta Market exhibitor and line pages.

The scraper reads a list of URLs from a CSV file, opens each page using Selenium, waits for dynamically loaded content, extracts exhibitor-card information, and saves the results to a CSV file.

## Workflow

**CSV URLs → Selenium + Chrome → Dynamic Content Loading → Data Extraction → CSV Output**

## Technologies Used

- Python
- Pandas
- Selenium
- Chrome WebDriver
- WebDriver Manager

## Key Features

- Reads URLs from a CSV file
- Removes duplicate URLs before processing
- Automates Chrome using Selenium
- Handles dynamically rendered content
- Triggers lazy-loaded content through scrolling
- Uses explicit waits
- Includes retry logic
- Uses a fallback XPath selector
- Exports extracted data to CSV

## Input

The scraper expects a CSV file containing a column named:

```text
url

Example:

url
https://www.atlantamarket.com/exhibitor/example
https://www.atlantamarket.com/exhibitor/example2

A sample input file is included in this repository as sample_input_links.csv.

Output

The scraper generates a CSV containing:

Source URL
Extracted exhibitor information

Example output structure:

url,booth_numbers
https://www.example.com/exhibitor/123,Example Exhibitor
https://www.example.com/exhibitor/456,Another Exhibitor

If no matching information is found, the scraper returns:

NOT FOUND

When multiple values are extracted from a page, they are combined using:

|||
Scraping Approach

The target pages contain dynamically rendered content, so the scraper uses Selenium and Chrome WebDriver.

The process is:

Read unique URLs from the input CSV.
Open each URL in Chrome.
Scroll the page to trigger lazy-loaded content.
Wait for exhibitor-card elements to appear.
Extract the visible text.
Retry the extraction when content is not immediately available.
Use a fallback XPath selector if the primary CSS selector fails.
Combine multiple extracted values using |||.
Save the results to a CSV file.
Project Structure
atlanta-market-exhibitor-scraper/
│
├── scraper.ipynb
├── sample_input_links.csv
├── requirements.txt
├── .gitignore
└── README.md
Installation

Install the required Python libraries:

pip install -r requirements.txt
Usage

Open scraper.ipynb using Jupyter Notebook, JupyterLab, or VS Code with the Jupyter extension.

Place the input CSV in the same directory as the notebook.

Run the notebook cells to perform the extraction.

The results are saved as:

final_output.csv
Notes

Website structures and HTML selectors can change over time. This project demonstrates browser automation and dynamic web data extraction techniques and should be used responsibly and in accordance with applicable website terms and policies.


### Important

When you paste it into GitHub, **do not include** the first:

```text
```markdown

or the final:


Those are only there in my message to show you the boundaries.

Your GitHub editor should start directly with:

**`# Atlanta Market Exhibitor Data Scraper`**

Then click **Commit changes** with:

```text
Improve project documentation
