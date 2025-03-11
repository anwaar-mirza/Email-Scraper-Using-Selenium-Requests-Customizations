# Email Scraper Using Selenium & Requests

This project is a Python-based email scraper that extracts email addresses from websites using Selenium, undetected_chromedriver, and Requests. It also attempts to retrieve email addresses from Facebook pages associated with the target websites.

## Features
- Scrapes emails directly from website HTML content using Requests.
- Extracts emails from Facebook pages if available.
- Uses Selenium with undetected_chromedriver to bypass bot detection.
- Supports multithreading for faster email extraction.
- Saves results in CSV format.

## Prerequisites
Ensure you have the following installed:

- Python 3.x
- Google Chrome
- ChromeDriver (managed by `webdriver_manager`)
- Required Python libraries:

```sh
pip install undetected-chromedriver selenium webdriver-manager requests pandas
```

## Usage

1. Save Facebook session cookies in `facebook_cookies.pkl` before running the script.
2. Place your target URLs in a CSV file under the `csv/` directory.
3. Run the script:

```sh
python your_script.py
```

### Multithreading Example
To run multiple scraping tasks concurrently:

```python
th1 = Thread(target=multithreading_implementation, args=['file1'])
th2 = Thread(target=multithreading_implementation, args=['file2'])
th1.start()
th2.start()
th1.join()
th2.join()
```

## File Structure
```
/your_project
│── /csv                 # Input CSV files
│── /results             # Output CSV files
│── facebook_cookies.pkl # Facebook session cookies
│── your_script.py       # Main script
│── README.md            # Documentation
```

## How It Works
1. **Initialize Selenium Driver**: Loads Facebook cookies for authentication.
2. **Extract Emails from HTML**: Uses regex to find email addresses.
3. **Extract Emails from Facebook**: If a Facebook link is found on the website, it attempts to scrape email addresses from the page.
4. **Multithreading Implementation**: Runs the scraping process for multiple CSV files concurrently.
5. **Results Storage**: Saves extracted emails into CSV files in the `results/` folder.

## Troubleshooting
- If the script fails to load Facebook, ensure cookies are valid.
- Some websites may block bot traffic; use a VPN or proxies if needed.
- Make sure Chrome and ChromeDriver versions are compatible.

## License
This project is open-source and available under the MIT License.

---
Made with ❤️ by Anwaar Mirza
