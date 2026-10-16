# Data Visualisation with Python and AI

**Code first. Prompt second. Think throughout.**

Workshop materials for learning to choose, build, and interpret data visualisations with Python, using AI tools to explain code, improve charts, and explore alternatives. The exercises use the TMDB Movies dataset and combine hands-on Python practice with questions, AI prompts, and reflection.

## Workshop details

| | Details |
| --- | --- |
| Event | [\[Python Series\] Data Visualisation with Python and AI](https://smu-sg.libcal.com/event/5913604) |
| Presenter | Janna Xu Cong, Senior Research Data Curator, Research & Data Services, SMU Libraries |
| Date | 9 September 2026 |
| Time | 4:00–5:30 pm Singapore time (UTC+8) |
| Venue | The Hive, Li Ka Shing Library, Level 2, Singapore Management University |
| Audience | SMU undergraduates, postgraduates, and researchers |
| Event level | Intermediate to Advanced |

## Materials

| File | What it contains |
| --- | --- |
| [Workshop notebook](Data_Visualisation_with_Python_and_AI_Workshop.ipynb) | Python examples, dataset preparation, AI prompts, interpretation questions, and a student challenge. |
| [Workshop slides](Teaching_Focused_Data_Visualisation_Python_AI_Slides.pptx) | Teaching slides covering chart selection, visualisation methods, AI-assisted learning, and human judgement. Download to view in PowerPoint or another compatible presentation application. |

[Open the notebook in Google Colab](https://colab.research.google.com/github/xusmallfat/data-visualisation-python-ai-workshop/blob/main/Data_Visualisation_with_Python_and_AI_Workshop.ipynb)

## Learning objectives

By working through the materials, you will practise how to:

- Choose a chart that answers a specific data question.
- Read and adapt Python visualisation code using Matplotlib, Seaborn, and Plotly.
- Use AI to explain, recreate, improve, and extend that code.
- Compare outputs and check assumptions, labels, and data handling.
- Interpret patterns carefully and communicate one insight alongside one caution.

The learning loop is: **ask a question → study the code → run and interpret → prompt AI → compare → reflect**.

## Topics covered

The notebook includes:

- Data loading and preparation with pandas and NumPy.
- Histograms and density curves for distributions.
- Bar charts and box plots for comparisons across genres.
- Scatter plots and correlation heatmaps for relationships.
- Line charts for changes over time.
- Interactive Plotly scatter plots and bubble charts.
- Hexbin plots for crowded data and 3D scatter plots for exploration.
- A final activity: build a chart, improve it with AI, and share an insight and a caution.

The slide deck also introduces treemaps and word clouds; those examples are not implemented in this version of the notebook.

## Getting started in Google Colab

1. Open the notebook using the Colab link above and save a copy to your Google Drive if you want to retain your edits.
2. Run **Section 0: Setup** to import the libraries. If a package is missing, add a code cell and run:

   ```python
   %pip install pandas numpy matplotlib seaborn scipy plotly
   ```

3. Obtain `tmdb_5000_movies.csv` from the [TMDB 5000 Movie Dataset on Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata).
4. In **Section 1**, use **Option A** to upload that CSV. Skip the Option B cells when using Option A.
5. Continue from **Section 2** in order. Run each chart, consider the interpretation questions, and then try the associated AI prompt.

The notebook provides prompts for tools such as ChatGPT, Gemini, and Claude. These are used separately from the notebook; the Python exercises do not require an AI API key.

### Alternative: load the data with KaggleHub

If you prefer Option B, first install KaggleHub in a notebook cell:

```python
%pip install kagglehub
```

Run the first Option B cell, which downloads the dataset and creates the `movies` and `credits` DataFrames. After it succeeds, add and run:

```python
df = movies.copy()
```

Then skip the subsequent optional `dataset_load` cell and continue to Section 2. The later exercises expect a DataFrame named `df`; the first Option B cell does not assign that name. If the download fails, use the CSV upload route instead.

### Run locally with Jupyter

Use a Python 3 environment and install the notebook tools and libraries:

```bash
python -m pip install jupyterlab pandas numpy matplotlib seaborn scipy plotly nbformat
python -m jupyter lab
```

Download the notebook and put `tmdb_5000_movies.csv` in the same folder. Open the notebook, run Section 0, and replace the Colab-only upload cell with:

```python
df = pd.read_csv("tmdb_5000_movies.csv")
df.head()
```

Skip the other dataset-loading cells and continue from Section 2.

## About the data and interpretation

The dataset is downloaded separately and is not included in this repository. It contains movie metadata such as titles, genres, release dates, budgets, revenue, ratings, and vote counts. Consult the dataset source for its terms and attribution information.

The notebook derives a primary genre from the first listed genre, extracts release years, treats zero budget/revenue/runtime values as missing, and retains movies with more than 50 votes and a non-missing rating. Charts therefore describe this prepared subset, rather than all movies.

Check sample sizes, missing values, and the effect of these choices when interpreting results. Correlation does not establish causation, and a visually impressive chart is not always the clearest way to communicate a finding.

## Workshop approach

Python builds the chart. AI supports the learning. Humans decide what is meaningful, clear, and responsible.

For the original event description and logistics, see the [SMU Libraries workshop page](https://smu-sg.libcal.com/event/5913604).
