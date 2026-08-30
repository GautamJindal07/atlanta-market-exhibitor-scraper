<h1>Atlanta Market Exhibitor Data Scraper</h1>

<p>
A Python-based Selenium web scraper designed to extract exhibitor information
from dynamically rendered Atlanta Market pages.
</p>

<h2>Overview</h2>

<p>
This project automates the extraction of information from Atlanta Market
exhibitor and line pages.
</p>

<p>
The scraper reads a list of URLs from a CSV file, opens each page using
Selenium, waits for dynamically loaded content, extracts exhibitor-card
information, and saves the results to a CSV file.
</p>

<h2>Workflow</h2>

<p>
<strong>CSV URLs</strong> → 
<strong>Selenium + Chrome</strong> → 
<strong>Dynamic Content Loading</strong> → 
<strong>Data Extraction</strong> → 
<strong>CSV Output</strong>
</p>

<h2>Technologies Used</h2>

<ul>
<li>Python</li>
<li>Pandas</li>
<li>Selenium</li>
<li>Chrome WebDriver</li>
<li>WebDriver Manager</li>
</ul>

<h2>Key Features</h2>

<ul>
<li>Reads URLs from a CSV file</li>
<li>Removes duplicate URLs before processing</li>
<li>Automates Chrome using Selenium</li>
<li>Handles dynamically rendered content</li>
<li>Triggers lazy-loaded content through scrolling</li>
<li>Uses explicit waits</li>
<li>Includes retry logic</li>
<li>Uses a fallback XPath selector</li>
<li>Exports extracted data to CSV</li>
</ul>

<h2>Input</h2>

<p>
The scraper expects a CSV file containing a column named:
<strong>url</strong>
</p>

<p><strong>Example:</strong></p>

<pre>
url
https://www.atlantamarket.com/exhibitor/example
https://www.atlantamarket.com/exhibitor/example2
</pre>

<p>
A sample input file is included in this repository as
<strong>sample_input_links.csv</strong>.
</p>

<h2>Output</h2>

<p>
The scraper generates a CSV containing:
</p>

<ul>
<li>Source URL</li>
<li>Extracted exhibitor information</li>
</ul>

<p><strong>Example output structure:</strong></p>

<pre>
url,booth_numbers
https://www.example.com/exhibitor/123,Example Exhibitor
https://www.example.com/exhibitor/456,Another Exhibitor
</pre>

<p>
If no matching information is found, the scraper returns:
</p>

<pre>NOT FOUND</pre>

<p>
When multiple values are extracted from a page, they are combined using:
</p>

<pre>|||</pre>

<h2>Scraping Approach</h2>

<p>
The target pages contain dynamically rendered content, so the scraper uses
Selenium and Chrome WebDriver.
</p>

<p><strong>The process is:</strong></p>

<ol>
<li>Read unique URLs from the input CSV.</li>
<li>Open each URL in Chrome.</li>
<li>Scroll the page to trigger lazy-loaded content.</li>
<li>Wait for exhibitor-card elements to appear.</li>
<li>Extract the visible text.</li>
<li>Retry the extraction when content is not immediately available.</li>
<li>Use a fallback XPath selector if the primary CSS selector fails.</li>
<li>Combine multiple extracted values using <strong>|||</strong>.</li>
<li>Save the results to a CSV file.</li>
</ol>

<h2>Project Structure</h2>

<pre>
atlanta-market-exhibitor-scraper/
│
├── scraper.ipynb
├── sample_input_links.csv
├── requirements.txt
├── .gitignore
└── README.md
</pre>

<h2>Installation</h2>

<p>Install the required Python libraries:</p>

<pre>pip install -r requirements.txt</pre>

<h2>Usage</h2>

<p>
Open <strong>scraper.ipynb</strong> using Jupyter Notebook, JupyterLab,
or VS Code with the Jupyter extension.
</p>

<p>
Place the input CSV in the same directory as the notebook.
</p>

<p>
Run the notebook cells to perform the extraction.
</p>

<p>
The results are saved as:
</p>

<pre>final_output.csv</pre>

<h2>Notes</h2>

<p>
Website structures and HTML selectors can change over time.
This project demonstrates browser automation and dynamic web data
extraction techniques and should be used responsibly and in accordance
with applicable website terms and policies.
</p>
