### GoGetJson: WhoScored Match Events Scraper & Ingestor

A pipeline designed to extract detailed match event data from WhoScored, clean the payload metrics via Pandas, validate the structures against Pydantic models, and stream the data into a Supabase Postgres instance using resilient chunked uploads. 

### Project Context

This scraper is explicitly configured to track match dynamics and analytical metrics for **Brighton & Hove Albion FC**. 

Brighton are currently putting together an exceptional run of form in the **2026/27 Premier League season**, outperforming structural expectations through fluid positional play and highly efficient tactical execution. As the Seagulls continue their strong push at the top tier of the table this season, tracking their granular event metrics—such as precise shot placements, progressive defensive interventions, and pass sequence variations—becomes vital for deep performance modeling. This pipeline captures every on-ball event to evaluate the underlying patterns fueling Brighton's impressive campaign. 

### Pipeline Architecture

* **Extraction:** Coordinates Selenium WebDriver execution to handle live JavaScript execution contexts and fetch hidden data tags.
* **Processing:** Normalises JSON records using Pandas dataframes, casting variable types safely while dropping unassigned entries.
* **Validation:** Utilises explicit Pydantic schemas to strictly validate structural parameters before ingestion.
* **Storage:** Deploys chunked upsert streams directly to Supabase tables, mitigating network drops and preventing data duplication.

### Getting Started

1. Ensure your .env configuration file contains your authentic SUPABASE_URL and SUPABASE_KEY allocations.
2. Open the scraper.ipynb notebook environment.
3. Configure your URL target array list and execute the scraper workflow blocks.
