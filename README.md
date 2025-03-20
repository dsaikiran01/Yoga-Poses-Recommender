# Yoga Pose Recommender

A Flask web application that demonstrates how to perform vector search on a Yoga Poses database stored in Firestore. This project integrates technologies such as Firestore, Vector Search, LangChain, and Gemini to create a contextual Yoga Pose recommender system.

> **This project was developed as part of Google Cloud's Code Vipassana Season 9**  

## Overview

This application showcases the following steps:

1. **Dataset Preparation**: Utilize an existing Hugging Face Dataset of Yoga poses in JSON format.
2. **Data Enhancement**: Enhance the dataset by adding a `description` field for each pose using Gemini in Vertex AI.
3. **Firestore Integration**: Use LangChain to create documents and leverage Firestore's integration to store the collection.
4. **Vector Search Setup**: Create a composite index in Firestore to enable vector search capabilities.
5. **Flask Application**: Develop a Flask application that integrates all components to provide a seamless user experience.

## Technologies Used

- **Backend**:
  - Python
  - Flask Framework
  - Firestore (Google Cloud)
  - Gemini (Vertex AI)
  - LangChain Python framework

- **Frontend**:
  - HTML
  - CSS
  - JavaScript

- **Deployment**:
  - Google Cloud Run

## Setup Instructions

To set up and deploy this project on Google Cloud, follow these steps:

### Prerequisites

- Ensure you have a Google Cloud account and the Google Cloud SDK installed.
- Set up a Firestore database in your Google Cloud project.
- Enable the Vertex AI API for access to Gemini.

### Local Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/dsaikiran01/Yoga-Poses-Recommender.git
   cd yoga-pose-recommender
   ```

2. **Create a Virtual Environment**:
   ```bash
   python3 -m venv env
   source env/bin/activate
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up Environment Variables**:
   Edit the `config.yaml` file and add your Google Cloud project credentials and other necessary configurations.

5. **Run the Application Locally**:
   ```bash
   python main.py
   ```

### Deployment on Google Cloud

1. **Authenticate with Google Cloud**:
   ```bash
   gcloud auth login
   gcloud config set project <<YOUR_PROJECT_ID>>
   ```

2. **Build and Submit the Application to Cloud Run**:
   ```bash
   gcloud builds submit --tag gcr.io/<<YOUR_PROJECT_ID>>/yoga-pose-recommender
   ```

3. **Deploy to Cloud Run**:
   ```bash
    gcloud run deploy yogaposes --source . \
        --port=8080 \
        --allow-unauthenticated \
        --region=us-central1 \
        --platform=managed  \
        --project=<<YOUR_PROJECT_ID>> \
        --env-vars-file=config.yaml
   ```

   Replace `your-project-id` and `your-region` with your Google Cloud project ID and preferred region.

4. **Access the Deployed Application**:
   After deployment, you'll receive a URL where the application is hosted. Visit this URL to access the Yoga Pose Recommender.

## Resources

- **Codelab Guide**: For detailed step-by-step instructions, refer to the [codelab](https://codelabs.developers.google.com/yoga-pose-firestore-vectorsearch-python?hl=en).

- **YouTube Tutorial**: Watch the comprehensive tutorial on setting up this project [here](https://www.youtube.com/watch?v=i-mLqfttaJ8).

## Project Demonstration

- **Deployment Video**: 

  https://github.com/user-attachments/assets/c43da786-fb62-46bc-9007-c3d982b6041c

- **Deployment Screenshot**:

  ![Deployment Screenshot](https://github.com/user-attachments/assets/3fa5a96c-3e77-47cc-be04-48741760033f)

## Acknowledgments

This project is based on the Google Codelab: "Build a contextual Yoga Poses recommender app with Firestore, Vector Search, LangChain, and Gemini (Python version)". Special thanks to the authors and contributors of the codelab for providing detailed instructions and resources.
