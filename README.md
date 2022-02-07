[![Open in colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gprzy/electoral-donations-brazil/blob/main/electoral_donations_brazil.ipynb)

# Electoral Donations Brazil

This repository is a test to assume the position of Data Engineer. In order to answer some questions and extract some insights about the Brazil electoral dataset
donations, transformations and data summarizations were performed, as well as the creation of a loading pipeline.

Data source: https://www.kaggle.com/felipeleiteantunes/electoral-donations-brazil2014

# Questions to be answered

- [X] Which 10 candidates received the most donations?

- [X] For the post (`cat_political_office`) of "Federal Representative" what amount each candidate received, the average amount of donations and the relationship between the two, order by the candidates with the most relative donations.

- [X] List all candidates, their donation amount, the average amount of donations for the position corresponding to that of the candidate, and the relationship between the Received by the candidate and the average of the applied position.

- [X] Create a table based on the previous result, filtering only candidates who received more than 0.1% of their total job average.

# Proposed solution

Initially, the data was read using `pandas`, and later it was processed and saved in `parquet` format, so that some questions were answered by `pandas` itself. Furthermore, additional questions were answered using SQL, and for that, pandas was used to read the data, as well as `sqlalchemy` with `sqlite` for loading.
