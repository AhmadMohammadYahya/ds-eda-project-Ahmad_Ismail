# King County Housing — Exploratory Data Analysis & Client Recommendation

An exploratory data analysis of the King County housing market (Seattle area, USA), built to answer a concrete question for a fictional client: **can Thomas Hansen — a buyer with five kids and a tight budget — find the right home, without overpaying?**

The project walks through cleaning and exploring 21,420 home sales, tests three hypotheses about what drives price (size, neighborhood quality, and timing), and turns the findings into a plain-language recommendation for a non-technical audience.

## Repository Contents

| File / Folder | Description |
| --- | --- |
| [**04_eda.ipynb**](04_eda.ipynb) | The full analysis: data cleaning, exploration, hypothesis testing, and client-facing commentary. Start here for the technical detail. |
| [**presentation.html**](presentation.html) | The client presentation as a self-contained, interactive HTML slide deck (39 slides). Open directly in any browser — arrow keys or the left/right edges navigate. Includes two embedded interactive dashboards. |
| [**presentation.pdf**](presentation.pdf) | A static, one-slide-per-page PDF export of the same deck, for quick reference or printing. |
| [**plots_Export_2/**](plots_Export_2/) | Every chart used in the notebook and the presentation, exported as standalone PNGs. |
| [**html_exports/**](html_exports/) | The two interactive Plotly dashboards embedded in the presentation (a price/feature map of King County, and a combined strategy dashboard) — open these directly for a full-window view. |
| [**column_names.md**](column_names.md) | Data dictionary describing every column in the King County housing dataset. |
| [**03_fetching_the_data_eda.ipynb**](03_fetching_the_data_eda.ipynb) | Connects to the project's PostgreSQL database and pulls the raw dataset into a CSV. |
| [**data/**](data/) | Local data folder (raw + cleaned CSVs). Not tracked in git — see [Setup](#setup) to regenerate it. |
| [**01_assignment.md**](01_assignment.md) | The original project brief: goals, deliverables, and the list of fictional clients. |
| [**02_workflow.md**](02_workflow.md) | The recommended EDA workflow this project followed. |

## Project Summary

- **Dataset:** King County Housing Data — 21,420 single-family home sales, May 2014 – May 2015.
- **Client:** Thomas Hansen (buyer). Assumptions are stated explicitly in both the notebook and the presentation, since the client brief is fictional.
- **Three hypotheses tested:**
  1. Does a bigger house always cost more?
  2. Does a nicer neighborhood cost more?
  3. Is there a best time of year to buy?
- **Headline findings:**
  - A *smart layout* (4–5 bedrooms, 1,800–2,400 sq ft) costs **$415K**, versus **$715K** for a sprawling luxury layout with the same bedroom count — a **42% saving**.
  - "Above Average" build-quality zip codes (construction grade 7.3–8.0) sit at a median of **$442K** — a well-kept neighborhood without the premium-tier markup.
  - **February** has both the lowest average price of the year (~$508K) and the fewest sales — the best window for the least competition.

## Viewing the Presentation

- **HTML (recommended):** open [`presentation.html`](presentation.html) in any browser. It's fully self-contained — no server needed — and includes two live, interactive charts you can zoom and hover over.
- **PDF:** open [`presentation.pdf`](presentation.pdf) for a static, printable version (one slide per page).

## Methodology

The notebook follows a standard EDA workflow (see [02_workflow.md](02_workflow.md)):

1. **Fetch** the data from the project database ([03_fetching_the_data_eda.ipynb](03_fetching_the_data_eda.ipynb)).
2. **Clean** it — duplicate checks, missing values, type fixes ([04_eda.ipynb](04_eda.ipynb)).
3. **Explore** price, size, age, renovation status, and geography.
4. **Test three hypotheses**, each backed by its own charts and plain-language conclusions.
5. **Recommend** a concrete plan, tying every finding back to the client's stated needs.

## Setup

> [!NOTE]
> Angle-bracket placeholders like `<repo-name>` should be replaced with your own values.

1. **Clone the repository**
   ```bash
   git clone git@github.com:AhmadMohammadYahya/ds-eda-project-Ahmad_Ismail.git
   cd ds-eda-project-Ahmad_Ismail
   ```

2. **Install dependencies** (creates a `.venv/` via [uv](https://docs.astral.sh/uv/))
   ```bash
   uv sync
   ```

3. **Set up database credentials** (only needed to re-fetch raw data)
   ```bash
   cp .env.example .env
   ```
   Fill in `.env` with the King County housing database credentials. This file is gitignored and must never be committed.

4. **Open the notebooks** in VS Code (or Jupyter) from the project root, selecting the environment created by `uv sync`.

## References

- [House Sales in King County dataset](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction) — the source dataset.
- [Pandas user guide](https://pandas.pydata.org/docs/user_guide/index.html)
- [Seaborn tutorial](https://seaborn.pydata.org/tutorial.html)
- [Plotly Python documentation](https://plotly.com/python/)

## License

See [LICENSE](LICENSE).
