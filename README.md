Context-Aware Phishing Detection using Machine Learning and Sender Behavior Analysis

Live Demo:
https://phishing-project-fgkpte5dtgxspldaqkhh8e.streamlit.app/

Overview

This project presents a context-aware phishing detection system that enhances traditional approaches by combining email content analysis with sender behavioral profiling.

Conventional phishing detection systems rely heavily on textual features, making them vulnerable to modern phishing emails that are often well-crafted and linguistically convincing. This project addresses that limitation by incorporating who the sender is and how they have behaved historically, resulting in a more robust, accurate, and explainable detection mechanism.

Core Concept

The system is built upon two fundamental dimensions:

Content Analysis → What the email communicates
Behavioral Analysis → Who the sender is and their historical trust pattern

Email content is transformed into numerical representations using TF-IDF vectorization, while structural and behavioral features are extracted to provide deeper context.

These combined features enable the model to make more informed and context-rich predictions, significantly improving phishing detection performance.

System Architecture

The detection pipeline consists of the following stages:

1. Text Vectorization

The email body is converted into feature vectors using a pre-trained TF-IDF vectorizer, capturing important linguistic patterns.

2. Structural Feature Extraction

The system derives multiple risk indicators from the email, including:

Number of URLs
Number of unique domains
Presence of IP-based links
Suspicious top-level domains (TLDs)
Frequency of exclamation marks
Uppercase character ratio
Presence of urgency-driven keywords
3. Sender Trust Modeling

A dynamic sender trust score is computed using historical data:

Known senders → Assigned trust based on past behavior
Unknown senders → Assigned a global prior (cold-start handling)
4. Feature Fusion

Textual and numerical features are combined into a unified feature vector after appropriate scaling.

5. Classification

A trained machine learning model predicts:

Phishing probability
Final classification (Phishing / Legitimate)
6. Explainability Layer

The system enhances transparency through:

Risk level indicators
Phishing probability score
Sender trust level
Detailed reasoning behind classification
Structural feature radar visualization

Technologies Used
Python
Streamlit
Scikit-learn
NumPy
SciPy
Matplotlib
Joblib

Project Structure
app.py                      # Main Streamlit application  
model_context_aware.pkl    # Trained ML model  
tfidf_vectorizer.pkl       # TF-IDF vectorizer  
sender_scaler.pkl          # Feature scaler  
sender_trust_scores.pkl    # Sender trust database  
requirements.txt           # Dependencies  

How to Run Locally
Clone the repository
Install dependencies:
pip install -r requirements.txt
Run the application:
streamlit run app.py

The application will launch in your browser, enabling real-time email analysis.

Deployment

The project is deployed using Streamlit Cloud.
All required model artifacts are included in the repository. Ensure .pkl files remain in the root directory for proper execution.

Key Features
Context-aware phishing detection
Integration of sender behavioral profiling
Cold-start problem handling
Structural and linguistic risk analysis
Interactive visualization dashboard
Real-time prediction with probability scoring

Limitations
Sender trust scores depend on historical data availability
No integration with live email servers
Model performance is dataset-dependent
Limited capability against zero-day phishing attacks

Future Enhancements
Integration with live sender reputation APIs
Advanced explainability using SHAP/LIME
Adaptive threshold tuning for improved accuracy
Real-time monitoring and alert systems
Enterprise-grade logging and audit mechanisms

Conclusion

This project demonstrates the effectiveness of combining linguistic analysis, structural indicators, and sender behavior modeling to build a more intelligent and explainable phishing detection system.

By moving beyond traditional text-only approaches, it highlights a practical direction for next-generation email security solutions powered by machine learning.
