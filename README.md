# Tokyo 2020 Olympics – Data Analysis

Exploratory and statistical analysis of the Tokyo 2020 Olympic Games in a single Jupyter notebook ([`OI_project.ipynb`](OI_project.ipynb)): data cleaning and merging of six datasets, the relation between GDP and medals, regression and classification of national success, a hypothesis test on gender balance, a time-series analysis of 120 years of Olympic history, a retrieval-augmented question-answering assistant (Gemini) and a quiz built from web-scraped facts.

**Stack:** Python · pandas · NumPy · scikit-learn · SciPy · Matplotlib · seaborn · BeautifulSoup · Google Gen AI SDK (Gemini) · Google Colab

---

## Key results

| Question | Method | Result |
|---|---|---|
| Do richer countries win more medals? | Pearson correlation, GDP vs. total medals (78 countries) | r = 0.77, strong positive relation |
| Can the medal count be predicted? | Multiple linear regression (GDP, number of athletes) | R² = 0.93 on the test set; team size carries almost all the predictive power |
| Can countries be classified by success? | Logistic regression, four classes by medal quartiles | Weak: the model mostly predicts "Very High" (31 % precision, 100 % recall for that class) |
| Were men over-represented per discipline? | Welch's t-test, male vs. female entries | t = 0.29, p = 0.77, no significant difference |
| How did participation change since 1896? | Time series, `athlete_events.csv` | Steady growth of female participation; average age rose from under 24 to over 26 years since the 1980s |

## Notebook contents

1. **Loading and cleaning:** missing values per dataset, GDP interpolation across years, duplicates.
2. **Merging:** Athletes–Teams on NOC, Medals–GDP on country name.
3. **Analysis:** GDP vs. medals, medal distribution (top 10), athletes per team and discipline.
4. **Regression and classification** of national success from GDP and team size.
5. **Hypothesis test:** gender balance of entries per discipline.
6. **Time series 1896–2016:** female participation and average athlete age.
7. **LLM question answering (RAG):** medal-table rows of the countries mentioned in a question are retrieved from the data and added to the Gemini prompt.
8. **Web scraping quiz:** true/false questions from Olympic facts scraped from three Croatian language pages.

## Data

| File | Content | Source |
|---|---|---|
| `Athletes.xlsx`, `Coaches.xlsx`, `EntriesGender.xlsx`, `Medals.xlsx`, `Teams.xlsx` | Tokyo 2020 participants and results | [Kaggle: 2021 Olympics in Tokyo](https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo) |
| `gdp.csv` | GDP by country and year (current USD) | [World Bank: GDP (NY.GDP.MKTP.CD)](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD) |
| `athlete_events.csv` | Olympic athletes 1896–2016 | [Kaggle: 120 years of Olympic history](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results) |

The data files are not stored in the repository.

## Running

**Google Colab:** upload the notebook, put the data files into Google Drive and adjust `DATA_DIR` in the first code cell if needed. For the LLM section, add your Gemini API key as a Colab secret named `GOOGLE_API_KEY`.

**Locally:**

```bash
pip install pandas numpy scikit-learn scipy matplotlib seaborn openpyxl requests beautifulsoup4 google-genai jupyter
mkdir data   # put the data files here
export GOOGLE_API_KEY=...   # only for the LLM section
jupyter notebook OI_project.ipynb
```

## Limitations

- Medals and GDP are merged on country names, so countries with different names in the two sources (e.g. *United States of America* vs *United States*) are missing from the GDP analysis.
- The regression and classification test sets contain only about 16 countries.
- A paired test would be more appropriate than Welch's t-test for the gender comparison, because both counts come from the same disciplines.
- LLM answers without retrieved data come from the model's own knowledge and can be wrong.

## Author

Antonela Ković – [GitHub](https://github.com/antonela-kovic)
