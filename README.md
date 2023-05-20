# Amazon Product Scraper

This script is used to scrape product details from Amazon using Selenium. It reads a CSV file containing product information and URLs, visits each product page, and extracts the title, image URL, price, and details of the product. The scraped data is then stored in a JSON file.

## Prerequisites

- Python 3.x
- Selenium library (`pip install selenium`)
- Chrome web driver compatible with your Chrome browser version

## Usage

1. Clone this repository or download the `scrape_amazon.py` script.
2. Install the required dependencies by running the following command:

   ```
   pip install selenium
   ```

3. Download the Chrome web driver that matches your Chrome browser version from the [ChromeDriver Downloads](https://sites.google.com/a/chromium.org/chromedriver/downloads) page. Make sure to place the web driver executable in a directory listed in your system's `PATH` environment variable.

4. Create a CSV file named `amazon_products.csv` and populate it with product information. The CSV file should have the following structure:

   ```
   product_name,product_id,product_url,country_code
   ```
   - `product_name`: The name of the product (can be left blank).
   - `product_id`: The unique identifier or ASIN of the product.
   - `product_url`: The Amazon product URL.
   - `country_code`: The two-letter country code of the Amazon website you want to scrape (e.g., `com` for amazon.com, `co.uk` for amazon.co.uk).

5. Run the script using the following command:

   ```
   python scrape_amazon.py
   ```

6. The script will start scraping the product details from the provided URLs. The progress will be displayed in the console, indicating the number of products scraped. Additionally, it will print a message when every 100 products have been scraped.

7. Once the scraping is complete, the script will generate a `product_details.json` file containing the scraped data. Each product will be represented as a JSON object with the following properties:

   - `title`: The title of the product.
   - `image_url`: The URL of the product image.
   - `price`: The price of the product.
   - `details`: Additional details about the product.

   ```
   [
       {
           "title": "Product 1",
           "image_url": "https://example.com/product1.jpg",
           "price": "$99.99",
           "details": "Lorem ipsum dolor sit amet, consectetur adipiscing elit."
       },
       {
           "title": "Product 2",
           "image_url": "https://example.com/product2.jpg",
           "price": "$49.99",
           "details": "Nulla commodo dapibus nibh quis iaculis."
       },
       ...
   ]
   ```

8. You can now use the `product_details.json` file for further analysis or processing.

## Notes

- It's important to note that web scraping can be against the terms of service of some websites. Make sure to review the website's terms of service before scraping any data.
- The script uses Selenium with the Chrome web driver. If you prefer using a different browser, you can modify the script accordingly.
- The script includes a delay of 1 second between visiting each product URL to avoid overloading the website. You can adjust this delay if needed.
- In case a product URL is not available or cannot be scraped, the script will print a message indicating the issue.
