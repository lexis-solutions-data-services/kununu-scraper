# Kununu Scraper

![banner](https://lexis-solutions-apify.fra1.cdn.digitaloceanspaces.com/banners/kununu.png)

This Apify actor scrapes information from [Kununu.com](https://www.kununu.com/) a website dedicated to gathering information about company jobs.

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/VyDn0C1lgX16e13a4/bA3QU3mzupfceprmJ-27df0abe-7d33-44cc-8e87-77341d31edfd_1_661d10b911edf.png" alt="Kununu.com Companies Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/kununu-scraper" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


## Table of Contents

- [Kununu Scraper](#kununu-scraper)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Input](#input)
  - [Output](#output)
  - [Usage](#usage)
  - [Limitations](#limitations)
  - [Need to scrape companies data?](#need-to-scrape-companies-data)


## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.1.8` |
| **Last Update** | Dec 1, 2025 |

---



## 💻 Integration Examples

This repository includes example code showing how to integrate the `kununu-scraper` actor into your projects.

You can find example implementations in the [`examples/`](./examples) folder:
- **TypeScript/JavaScript**: See [`examples/typescript/`](./examples/typescript) for a complete TypeScript example
- **Python**: See [`examples/python/`](./examples/python) for a complete Python example

Each example includes:
- Ready-to-use code templates
- Setup instructions
- Documentation links

---


## Features

- Scrapes detailed company information including companyTitle, companyLogo, companyWebsite, location, kununuScore, openJobsCount, reviewCount, percentHappyWithWage and companyDescription.
- Handles pagination to gather data from multiple pages.
- Outputs data in JSON format for easy integration with other tools.

## Input

The actor accepts the following input parameters in JSON format:

- `startUrls` (array): List of URLs to start the scraping process from. It can be a search or company detail url.

  ```json
  {
    "startUrls": [
      {
        "url": "https://www.kununu.com/de/search?q=berlin&country=de"
      }
    ]
  }
  ```

- `maxItems` (integer): Maximum number of items to scrape.

- `proxyConfiguration` (object): Proxy settings for the scraping process.

## Output

The actor produces output in JSON format with the following structure:

```json
{
  "companyTitle": "Berlin Brands Group",
  "companyLogo": "https://assets.kununu.com/media/prod/profiles/logos/447c6daa-436f-4404-8a1f-5de6ea529ec7_1_63c1621744d36.gif",
  "companyDescription": "Wir kreieren, entwickeln...",
  "kununuScore": 4.5,
  "location": "Berlin und weitere",
  "reviewCount": 572,
  "openJobsCount": 0,
  "percentHappyWithWage": 51,
  "companyWebsite": "https://www.berlin-brands-group.com/"
}
```

## Usage

1. Create a new task: In the Apify console, create a new task for the Kununu Scraper actor.

2. Configure input: Provide the necessary input parameters as described above.

3. Run the task: Start the task to begin scraping data.

4. Retrieve output: Once the task is complete, download the output in JSON format.

## Limitations

- The scraper is subject to the limitations and restrictions of Kununu.com, including potential rate limits and CAPTCHAs.
- The actor's performance may vary based on the website's response times and structure changes.

## Need to scrape companies data?

- UK 🇬🇧

  - [TotalJobs Scraper](https://apify.com/lexis-solutions/totaljobs-scraper)

- France 🇫🇷

  - [HelloWork Scraper](https://apify.com/lexis-solutions/hellowork-scraper)

- Germany 🇩🇪

  - [Arbeitsagentur Scraper](https://apify.com/lexis-solutions/bundesagentur-fur-arbeit-arbeitsagentur-scraper)

- Netherlands 🇳🇱

  - [Werk.nl Scraper](https://apify.com/lexis-solutions/werk-nl-scraper)

- Sweden 🇸🇪

  - [Arbetsformedlingen Scraper](https://apify.com/lexis-solutions/arbetsformedlingen-se-scraper)
  
  
---

👀 p.s.

Got feedback or need an extension?

Lexis Solutions is a [certified Apify Partner](https://apify.com/partners/find). We can help you with custom solutions or data extraction projects.

Contact us on our [website](https://www.lexis.solutions/?ref=apify-profile), [Email](mailto:scraping@lexis.solutions), or [LinkedIn](https://www.linkedin.com/company/lexis-solutions).
