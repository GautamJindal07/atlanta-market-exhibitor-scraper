# Atlanta Market Exhibitor Data Scraper

A Python-based Selenium web scraper designed to extract exhibitor information from dynamically rendered Atlanta Market pages.

## Overview

This project automates the extraction of information from Atlanta Market exhibitor and line pages.

The scraper reads a list of URLs from a CSV file, opens each page using Selenium, waits for dynamically loaded content, extracts exhibitor-card information, and saves the results to a CSV file.

## Workflow

CSV URLs  
↓  
Selenium + Chrome  
↓  
Open Web Page  
↓  
Trigger Lazy-Loaded Content  
↓  
Wait for Dynamic Elements  
↓  
Extract Exhibitor Information  
↓  
Retry / Fallback  
↓  
CSV Output

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

A sample input file is included in this repository:

sample_input_links.csv

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

The process:

Reads unique URLs from the input CSV.
Opens each URL in Chrome.
Scrolls the page to trigger lazy-loaded content.
Waits for exhibitor-card elements to appear.
Extracts the visible text.
Retries the extraction when content is not immediately available.
Uses a fallback XPath selector if the primary CSS selector fails.
Combines multiple extracted values using |||.
Saves the results to a CSV file.
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


### Commit message

At the bottom, use:

```text
Improve project documentation

Then click Commit changes.

After committing

Your repository should now have:

📁 atlanta-market-exhibitor-scraper

├── .gitignore
├── README.md
├── requirements.txt
├── sample_input_links.csv
└── scraper.ipynb

And the README should look much more substantial when you view the repository homepage.

After you've committed this, send me a screenshot of the repository homepage. I'll do a final check of Project 1, and then we'll move on to your next scraping script.

give me a single paste product

Sure — here is the entire README as one single paste. Just copy everything inside the box and paste it into README.md on GitHub:

# Atlanta Market Exhibitor Data Scraper

A Python-based Selenium web scraper designed to extract exhibitor information from dynamically rendered Atlanta Market pages.

## Overview

This project automates the extraction of information from Atlanta Market exhibitor and line pages.

The scraper reads a list of URLs from a CSV file, opens each page using Selenium, waits for dynamically loaded content, extracts exhibitor-card information, and saves the results to a CSV file.

## Workflow

CSV URLs  
↓  
Selenium + Chrome  
↓  
Open Web Page  
↓  
Trigger Lazy-Loaded Content  
↓  
Wait for Dynamic Elements  
↓  
Extract Exhibitor Information  
↓  
Retry / Fallback  
↓  
CSV Output

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

A sample input file is included in this repository:

sample_input_links.csv

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

The process:

Reads unique URLs from the input CSV.
Opens each URL in Chrome.
Scrolls the page to trigger lazy-loaded content.
Waits for exhibitor-card elements to appear.
Extracts the visible text.
Retries the extraction when content is not immediately available.
Uses a fallback XPath selector if the primary CSS selector fails.
Combines multiple extracted values using |||.
Saves the results to a CSV file.
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


**Commit message:**

```text
Improve project documentation
