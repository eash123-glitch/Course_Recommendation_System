

---

# Course Recommendation System

This project implements a content-based and collaborative filtering course recommendation system, designed to assist students in finding courses that match their interests. The system uses natural language processing (NLP) and machine learning techniques to analyze course descriptions and suggest relevant courses from various e-learning platforms.

## Table of Contents
- [Introduction](#introduction)
- [Methodology](#methodology)
  - [1. Content-Based Recommendation](#1-content-based-recommendation)
  - [2. Collaborative Filtering](#2-collaborative-filtering)
  - [3. Hybrid Recommendation Model](#3-hybrid-recommendation-model)
- [Workflow](#workflow)
- [Data Collection](#data-collection)
- [Data Preprocessing](#data-preprocessing)
- [Modeling](#modeling)
- [Deployment](#deployment)
- [Conclusion](#conclusion)

## Introduction
With the rapid growth of e-learning platforms offering a wide variety of courses, students face the challenge of finding the right course that aligns with their academic goals. This project addresses that problem by creating a **Course Recommendation System** that provides personalized suggestions using advanced algorithms such as **content-based filtering** and **collaborative filtering**.

## Methodology

### 1. Content-Based Recommendation
The system generates course recommendations by analyzing course descriptions and extracting important features such as keywords, course topics, and metadata. The main steps include:
- **Item Representation**: Courses are represented by features such as keywords, descriptions, and metadata.
- **User Profile**: User preferences and history are used to generate relevant course suggestions.
- **Recommendation Generation**: Similarity between courses is calculated, and the most relevant courses are recommended.

### 2. Collaborative Filtering
Collaborative filtering generates recommendations based on the preferences of similar users. This approach analyzes the user's interactions and ratings with courses and compares them with other users.
- **User-Item Matrix**: A matrix representing the ratings users have given to courses.
- **Similarity Calculation**: The system calculates similarity between users based on their course ratings.
- **Recommendation Generation**: The system predicts course preferences based on similar users' ratings.

### 3. Hybrid Recommendation Model
A hybrid recommendation model combines both **content-based filtering** and **collaborative filtering** to improve accuracy and handle diverse user preferences. The system uses a weighted approach, assigning different weights to the results of both models.

## Workflow

The overall process of building the Course Recommendation System follows this workflow:

1. **Data Collection**: Web scraping from platforms like NPTEL, MIT OpenCourseWare, Coursera, and Udemy.
2. **Data Cleaning and Preprocessing**: Removing null values, duplicates, and irrelevant words, followed by applying techniques like stemming and lemmatization.
3. **Modeling**: Using `CountVectorizer` for feature extraction and cosine similarity for calculating similarities between courses.
4. **Deployment**: A Flask-based web application that allows users to input course names and receive recommendations.

![Workflow Diagram](assets/workflow_diagram.png)

## Data Collection
Data was collected using web scraping techniques from platforms such as NPTEL, MIT OpenCourseWare, Coursera, and Udemy. Selenium was primarily used due to the dynamic nature of these websites. The scraped data included course names, descriptions, instructors, and other relevant attributes.

## Data Preprocessing
The collected data was cleaned and preprocessed using NLP techniques:
- **Stopwords Removal**: Common words that don’t contribute to the recommendation process were removed.
- **Stemming and Lemmatization**: Words were converted to their root forms to reduce redundancy in course descriptions.
- **Feature Extraction**: Keywords were extracted from course descriptions to form feature vectors.

## Modeling
The model uses a combination of **content-based filtering** and **collaborative filtering** to provide recommendations:
- **CountVectorizer** was used to convert course keywords into feature vectors.
- **Cosine Similarity** was applied to calculate similarity between courses.
- Recommendations were generated based on the highest similarity scores.

## Deployment
The system is deployed as a Flask web application that provides recommendations based on user input. The application loads course data from a CSV file and uses cosine similarity to generate recommendations. The Flask app is served on port 5000 and provides an interface for users to enter a course name and receive a list of recommended courses.

## Conclusion
This Course Recommendation System addresses the need for personalized course suggestions in the vast online education landscape. By leveraging NLP, machine learning, and web development, the system provides accurate recommendations tailored to users' academic interests.

---

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/course-recommendation-system.git
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Flask application:
   ```bash
   python app.py
   ```

### License
This project is licensed under the MIT License.

---
