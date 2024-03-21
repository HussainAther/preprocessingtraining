# Preprocessing and Training Data Development for Art Recommendations with Microsoft HoloLens

A brief description of what this project is about and its purpose.

## Overview

This part of the project documentation outlines the preprocessing and training data development necessary for creating an art recommendation system for the Microsoft HoloLens. Utilizing data from The Metropolitan Museum of Art (The MET) Collection API, this guide provides the necessary steps to prepare the dataset for model development.


## Dataset

The dataset, metdata_cleaned.csv, was sourced from The MET Collection API. It contains a variety of features related to the museum's artworks, such as artist information, creation dates, and artwork dimensions. The dataset includes both numeric and categorical data, making it versatile for creating an art recommendation system.

### Features

- **Numeric Features**: Include `accessionYear`, `artistBeginDate`, `artistEndDate`, `objectBeginDate`, `objectEndDate`, and others. These features have a wide range of values and require standardization for some model types.
- **Categorical Features**: Include `department`, `objectName`, `culture`, `artistRole`, and more. These are suitable for conversion into dummy or indicator variables for modeling purposes.

## Preprocessing Steps

1. **Loading the Dataset**: The dataset is loaded into a DataFrame for analysis and manipulation.
2. **Creating Dummy Variables**: Categorical variables such as `department`, `objectName`, and `culture` are processed for dummy encoding to enable their use in models.
3. **Standardizing Numeric Features**: Numeric features like `accessionYear`, `objectBeginDate`, and `objectEndDate` are standardized to have a mean of 0 and a standard deviation of 1, addressing the wide range of values.
4. **Splitting the Data**: The dataset is split into training and testing sets, with placeholders included for selecting the features and the target variable based on the specific modeling goal.

## Installation

Instructions on setting up the project environment: 

```bash
pip install -r requirements.txt
```

Include any additional steps necessary to obtain the dataset or to set up the environment.

## Usage

A quick start guide to running the preprocessing steps:

```python
python preprocessing_script.py
```

Adjust the script name and command as necessary.

## Contributing

Information on how others can contribute to the project. Guidelines for submitting pull requests, reporting bugs, or suggesting enhancements.

## License

State the license (if any) under which this project is available.

## Acknowledgments

- Mention any individuals, organizations, or datasets that require acknowledgment.

Based on the analysis of my dataset:

### Categorical Data:
My dataset contains several categorical columns, such as:
- `department`, `objectName`, `culture`, `artistRole`, `artistPrefix`, `artistDisplayName`, `artistGender`, and many more related to geographical location, object details, and artist information.

These columns are suitable for converting into dummy or indicator variables if they are to be included in my model, especially if they provide meaningful information for prediction.

### Numeric Features Range:
For numeric features, the ranges vary significantly:
- **Accession Year** ranges from 1883 to 2023, indicating the year an item was acquired.
- **Artist Begin and End Dates** have a wide range (1607 to 9999 for end dates, likely due to placeholders or errors for some entries).
- **Object Begin and End Dates** range from the early 1600s to the mid-1900s, reflecting the creation dates of objects.

The `GalleryNumber` seems to be an identifier with a narrower range (512 to 774).

Given this variety, scaling or normalization might be necessary, especially for features with large ranges or significant differences in scale compared to others. Features that already range from 0 to 1 are not common in this dataset, but those ranging from 0 to 100 or beyond are present (e.g., year-based features).

This analysis helps in understanding the preprocessing needs of my dataset, especially in choosing the right scaling techniques and identifying which categorical variables to convert into dummy variables.
