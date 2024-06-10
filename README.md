
# Web Scraper Project

This project is a web scraping tool designed to extract and process information from various websites. The tool utilizes several Python libraries such as `requests`, `BeautifulSoup`, `spacy`, and `re` for data extraction and processing. Additionally, it leverages Google's Generative AI for text processing and data extraction.

## Authors

Credits 

[Hirak Desai](https://www.github.com/hirak214)

[Yashvi Agrawal](https://github.com/yashviagrawal)

## Features

- **Single Page Scraping**: Extracts and processes data from single-page websites.
- **Multi-Page Scraping**: Handles data extraction from multi-page websites using Google's Generative AI for processing large text data.
- **Data Cleaning**: Removes unwanted elements like headers and footers from web pages to clean the extracted text.
- **Custom Prompts**: Uses customized prompts for Generative AI to extract structured data like names, emails, phone numbers, and research fields.

## Requirements

- Python 3.x
- `fuzzywuzzy`
- `google-generativeai`
- `bs4`
- `requests`
- `spacy`
- `re`

## Installation

Install the required libraries using pip:

```bash
pip install fuzzywuzzy google-generativeai bs4 requests spacy
```

## Usage

1. **Single Page Scraping**: Modify the `url` variable with the desired website URL. Run the script to extract and clean the data.
   
2. **Multi-Page Scraping**: Modify the `url` and set up the Google Generative AI configuration with your API key. Use the provided functions to extract and process data.

## Example

```python
# Single Page Scraping Example
url = "https://example.com"
response = requests.get(url)
html_content = response.text

soup = BeautifulSoup(html_content, 'html.parser')
header_selector = 'header'
footer_selector = 'footer'

# Remove headers and footers
header_elements = soup.select(header_selector)
for element in header_elements:
    element.extract()

footer_elements = soup.select(footer_selector)
for element in footer_elements:
    element.extract()

# Extract and clean text
combined_content = soup.get_text()
cleaned_text = re.sub(r'\s+', ' ', combined_content)
print(cleaned_text)
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Google Generative AI](https://ai.google/)
- [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/)
- [Spacy](https://spacy.io/)
