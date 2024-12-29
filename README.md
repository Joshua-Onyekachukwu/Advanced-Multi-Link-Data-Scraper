# Advanced-Multi-Link-Data-Scraper

Web Scraper with Keyword Search Documentation

Overview

This project is a web scraper with the functionality to scrape multiple pages and search for specified keywords within the content of the pages. The scraper supports both static pages (using requests) and dynamic pages (using Selenium). The results of the keyword search are displayed in the GUI and can be saved to a text file. Features

Scrapes both static and dynamic websites.
Supports multiple URLs for bulk scraping.
Allows users to input multiple keywords for searching.
Displays progress of the scraping process.
Saves the results to a text file.

Installation Requirements

To run this project, you need the following Python libraries:

tkinter for the GUI interface (usually comes with Python).
requests for sending HTTP requests.
beautifulsoup4 for parsing HTML content.
selenium for dynamic content scraping.
webdriver_manager for managing ChromeDriver (only required if Selenium is used).

Install Required Libraries

You can install the required libraries using pip:

pip install requests beautifulsoup4 selenium webdriver-manager

Setup and Running the Code

    Clone the Repository (if applicable)

git clone https://github.com/yourusername/web-scraper.git cd web-scraper

    Run the Script

Run the script using Python:

python scraper.py

Using the Application

When you run the script, a GUI window will open. Inputs

URLs: Enter a comma-separated list of URLs you want to scrape.
Keywords: Enter a comma-separated list of keywords to search for in the page content.

Actions

Start Scraping: Click the "Start Scraping" button to begin the scraping process. The scraper will go through each URL, scrape the page content, search for the specified keywords, and show the results in the GUI.
Save Results: After scraping is complete, click the "Save Results" button to save the results to a text file (scraping_results.txt).

Progress Bar

The progress bar at the bottom of the window will update as the scraper processes each URL. Functions get_random_user_agent()

Returns a random User-Agent string to mimic different browsers and avoid detection. scrape_page(url)

Uses the requests library to scrape a static page and return its HTML content. scrape_with_selenium(url)

Uses the Selenium WebDriver to scrape dynamic pages. This function runs the browser in headless mode (background) and fetches the page source. search_keywords(content, keywords)

Searches for specified keywords within the page content and counts their occurrences. scrape_and_search()

Handles the scraping process for multiple URLs, checks for dynamic or static content, scrapes the pages, searches for keywords, and updates the GUI with the results. save_results()

Saves the scraped and keyword search results to a text file (scraping_results.txt). start_scraping_thread()

Runs the scraping process in a separate thread to keep the GUI responsive. Example Usage

URLs:
https://example.com, https://anotherexample.com

Keywords:
Python, web scraper, scraping

The scraper will go through both URLs, search for the keywords "Python", "web scraper", and "scraping" in the page content, and show the number of times each keyword appears in the results. Logging

The scraper logs information about the scraping process into a file scraper.log. This includes successful scrapes, errors, and other relevant details. Notes

The scraper uses Selenium for pages with JavaScript content. If you encounter issues with Selenium not working, make sure you have the correct version of the ChromeDriver installed. You can also uncomment the webdriver_manager line to automatically handle driver installations.
The code includes a random sleep interval between requests to prevent being blocked by websites for making too many requests in a short time.

Troubleshooting

Selenium Issues: If Selenium is unable to find the ChromeDriver, make sure it's installed or use the webdriver_manager package to automatically manage it.
Page Loading Time: For dynamic pages, the scraper waits for 2 seconds to allow the page to load. If the page needs more time, adjust the time.sleep(2) to a higher value.
Invalid URLs: Make sure the URLs entered are valid and accessible.

Future Improvements

Allow saving results in different formats (e.g., CSV, JSON).
Implement a more sophisticated error-handling mechanism.
Add functionality for user authentication if required for certain websites.

