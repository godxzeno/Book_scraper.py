# Book Store Scraper

A Python script that scrapes book listings from [books.toscrape.com](https://books.toscrape.com) — a site built for scraping practice — and exports the data to a clean CSV file.

## What it does

- Visits multiple pages automatically (pagination handled — no manual page-by-page work)
- Extracts for each book:
  - Title
  - Price (GBP)
  - Stock availability
  - Star rating (1–5)
- Saves everything into `books_data.csv`
- Includes basic error handling so the script doesn't crash if a page fails to load

## How to run it

1. Install the required libraries:
   ```
   pip install requests beautifulsoup4
   ```
2. Run the script:
   ```
   python book_scraper.py
   ```
3. Check the generated `books_data.csv` file in the same folder.

## Sample output

| title                              | price_gbp | availability | rating_out_of_5 |
|-------------------------------------|-----------|--------------|------------------|
| A Light in the Attic                | 51.77     | In stock     | 3                |
| Tipping the Velvet                  | 53.74     | In stock     | 1                |
| Soumission                          | 50.10     | In stock     | 1                |

## Notes

- `max_pages` in the script controls how many pages get scraped (default: 5). Change it to scrape more or fewer pages.
- A 1-second delay is added between requests to avoid overloading the target server — good practice for any scraping project.
- This project can be adapted to scrape other e-commerce or listing sites by updating the HTML tags/classes in `extract_books()`.
- 
