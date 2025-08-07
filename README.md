Smart Shoe Recommender System

AnalogDots Machine Learning Engineer / Data Scientist Competency Assessment
Project Overview

This project implements a personalized shoe recommendation system along with user-specific service logic, designed to mimic a real-world shoe retail environment. The system uses synthetic user interaction data and shoe attributes to provide content-based recommendations and personalized service notifications such as shoe care reminders and replacement suggestions.

The goal is to demonstrate proficiency in designing recommendation algorithms, generating synthetic data, analyzing user behavior, and designing a relational database schema to store and manage the information efficiently.
Repository Structure

text
smart-shoe-recommender/
├── data/                       # Synthetic dataset CSV files
│   ├── shoe_catalog.csv        # Shoe attributes dataset
│   ├── user_profiles.csv       # User demographic and profile data
│   └── user_interactions.csv   # User interaction history
├── src/                        # Source code scripts
│   ├── data_prep.py            # Dataset generation script
│   ├── recommend.py            # Recommendation algorithm implementation
│   └── personalize.py          # Personalized shoe care and replacement logic
├── notebooks/                  # Jupyter notebooks for data exploration (optional)
│   └── eda.ipynb
├── schema.sql                  # PostgreSQL database schema for data storage
├── requirements.txt            # Python dependencies list
└── README.md                   # Project documentation (this file)

Dataset Description

    shoe_catalog.csv: Contains shoe attributes such as brand, model, type, material, color, size, and care requirements.

    user_profiles.csv: Simulated user demographic data including user ID, age, gender, and typical shoe usage patterns.

    user_interactions.csv: Records of user actions such as viewed, purchased, wishlisted, and shoe care events with timestamps.

The datasets are synthetically generated to mimic realistic user behavior and product diversity, enabling the demonstration of model functionality without real user data.
Recommendation Algorithm
Approach

The project uses a content-based filtering approach that:

    Encodes shoe features (brand, type, material, color, care requirements) using one-hot encoding.

    Builds a user profile vector based on average features of shoes the user has interacted with (viewed or purchased).

    Computes cosine similarity between this user profile and all other shoes.

    Recommends the top-N most similar shoes that the user hasn't interacted with yet.

Why Content-Based Filtering?

    Handles personalized recommendations based on user preferences.

    Does not require large amounts of user interaction data (useful for cold start).

    Simple to implement and interpret for this assessment.

Running the Recommendation

Run the following in your terminal:

bash
python src/recommend.py

This prints recommended shoe IDs for the given test user (user_1 by default).
Personalized Service Logic

This module analyzes each user’s interaction patterns to provide two key personalized services:

    Proactive Shoe Care Notifications

        Notifies users to care for shoes frequently worn but not maintained for a threshold period.

    Shoe Replacement Suggestions

        Suggests replacement when estimated wear (based on frequency and duration of use) exceeds a threshold.

Run personalized logic with:

bash
python src/personalize.py

The output lists care reminders and replacement suggestions for the test user.
Database Schema Design

The schema.sql file contains the PostgreSQL schema, comprising the following tables:

    users: Stores user profiles.

    shoes: Catalog of shoe attributes.

    user_interactions: Logs user behavior (views, purchases, care events).

    recommendations_log: (Optional) Logs generated recommendations for historical analysis.

Schema design focuses on:

    Data integrity with primary and foreign keys.

    Efficient querying for recommendations and personalized service delivery.

    Scalability for growing user and product bases.

Setup Instructions

    Clone the repository

text
git clone https://github.com/your-username/smart-shoe-recommender.git
cd smart-shoe-recommender

    Install dependencies

Use pip:

text
pip install -r requirements.txt

    Generate synthetic data

text
python src/data_prep.py

    Run recommendation system

text
python src/recommend.py

    Run personalized services logic

text
python src/personalize.py

Dependencies

Listed in the requirements.txt file, major libraries include:

    pandas for data manipulation

    scikit-learn for feature encoding and similarity calculations

    numpy for numerical operations

Notes

    The project currently uses content-based filtering; enhancements like collaborative or hybrid filtering are left for future improvements.

    Dataset is synthetic and designed to emulate realistic scenarios.

    Database schema is provided but not linked with a live database in this repo; you can use it to set up your PostgreSQL instance if desired.

Demonstration

A screen recording with voice narration accompanies this repository (link/shared separately), showcasing:

    Data generation

    Recommendation outputs for sample users

    Personalized service messages

    Schema overview and rationale

Contact

For any queries or guidance on this project, please feel free to contact me.

Feel free to copy this base README.md content into your project and adjust it according to your preferences. If you want, I can prepare a ready-to-use markdown file for you as well! Just ask.# smart-shoe-recommender
Shoe recommendation and personalized care system for AnalogDots assessment
