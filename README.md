# IMDb Series Scraper

This project uses Selenium to automatically scrape data about the top 250 TV series from IMDb's website. It collects information such as title, year, number of episodes, rating, popularity, and main cast.

## Prerequisites

- Python 3.6+
- Jupyter Notebook
- Chrome web browser
- ChromeDriver compatible with your Chrome version

## Dependencies

Install the required Python packages:

```bash
pip install selenium jupyter pandas dataclasses
```

## Setup

1. Download the ChromeDriver executable from [the official website](https://sites.google.com/chromium.org/driver/) matching your Chrome browser version.
2. Place the ChromeDriver in your PATH or in the project directory.

## Running the Notebook

1. Launch Jupyter Notebook:

```bash
jupyter notebook
```

2. Open the `Aula 08 - Selenium.ipynb` notebook.
3. Run all cells in sequence by clicking "Cell" > "Run All" or run individual cells with Shift+Enter.

## What the Code Does

The notebook performs the following operations:

1. Opens a Chrome browser and navigates to IMDb.
2. Opens the menu and clicks on "250 séries mais populares" (Top 250 TV Series).
3. For each series in the list, it extracts:
   - Title
   - Year of release
   - Number of episodes
   - IMDb rating
   - Link to the series page
4. For each series page, it then extracts:
   - Popularity score
   - Main cast with their character names
5. Stores all data in a structured format.
6. Saves the collected data to a JSON file named `series.json`.

## Output

The output is stored in `series.json` with the following structure for each series:

```json
{
    "titulo": "Breaking Bad",
    "ano": 2008,
    "episodios": 62,
    "classificacao": 9.5,
    "pagina": "https://www.imdb.com/...",
    "popularidade": 27.0,
    "elenco_principal": [
        "nome: Bryan Cranston | personagem: Walter White",
        "nome: Aaron Paul | personagem: Jesse Pinkman",
        ...
    ]
}
```

## Troubleshooting

- **Element not found errors**: IMDb may change their website structure occasionally. If the notebook fails to find elements, you may need to update the XPath or CSS selectors.
- **Slow execution**: The script includes waiting times to ensure proper page loading. This is normal and prevents errors.
- **ChromeDriver version mismatch**: Make sure your ChromeDriver version matches your Chrome browser version.

## Customizing the Code

- To scrape fewer series, modify the loop that iterates through `lista_atores`.
- To extract additional information, identify the relevant HTML elements and add them to the `cria_serie` or `infos_adicionais` functions.
