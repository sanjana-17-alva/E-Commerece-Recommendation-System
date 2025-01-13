# E-Commerce Recommendation System

## 1. Introduction
This report discusses the design and implementation of an e-commerce recommendation system, developed using Flask, SQLAlchemy, and machine learning techniques. The recommendation system leverages content-based filtering to suggest products to users based on the attributes of products they are interested in. The goal of this system is to enhance the shopping experience by suggesting items that are similar to what users are browsing, increasing engagement and sales.

---

## 2. System Architecture and Design
The e-commerce recommendation system is designed using the following components:
* **Backend Framework: Flask**  
  A lightweight and flexible web framework for Python that is used to build the web application, handle routes, and manage user interaction.
* **Database: MySQL (via SQLAlchemy)**  
  MySQL is used as the relational database for storing user details (e.g., Signup and Signin information), product details, and product recommendations. SQLAlchemy ORM is used to interact with the database.
* **Machine Learning Models**  
  * **Content-Based Filtering:** A machine learning technique that recommends products similar to those the user has shown interest in, based on product descriptions and tags.

---

## 3. Recommendation Techniques
The system uses content-based recommendation to suggest products to users. Here's a detailed breakdown of the recommendation process:
* **TF-IDF Vectorization:**  
  TF-IDF (Term Frequency-Inverse Document Frequency) is used to vectorize product tags or descriptions. It helps in converting textual data into numerical representations, which can then be processed for similarity analysis.
* **Cosine Similarity:**  
  After the product descriptions or tags are vectorized, cosine similarity is used to measure the similarity between products. Products with a high similarity score are considered similar and are recommended to the user.
* **Recommendation Process:**  
  1. A user selects a product they are interested in.  
  2. The system retrieves similar products using the content-based filtering algorithm.  
  3. A list of the top N similar products is displayed to the user, with their names, review counts, ratings, and images.

---

## 4. System Features and Routes
The application includes several features that enhance the user experience:
* **User Authentication:**  
  * **Signup:** Users can create an account by providing their username, email, and password.  
  * **Signin:** Users can log in to the application to access personalized recommendations and product information.  
  * User data is stored in a MySQL database (Signup and Signin tables).
* **Product Recommendations:**  
  * **Content-Based Recommendations:** Based on a product name, users can retrieve recommendations for similar products using the content-based filtering method.  
  * Products are recommended based on the product tags, and each recommendation includes the product name, review count, brand, and image URL.
* **Trending Products:**  
  A list of trending products is displayed on the homepage, showcasing popular items that might interest the users. The product information, including images and prices, is shown to the user in a visually appealing format.

---

## 5. User Interface and Experience
The system includes the following elements to improve the user experience:
* **Homepage:**  
  * Displays trending products with random images and prices.  
  * Allows users to view product details and interact with the recommendation system.
* **Signup and Signin:**  
  * Simple and intuitive forms for user registration and login.  
  * Upon successful login, the user is redirected to the homepage, where personalized recommendations can be accessed.
* **Product Recommendations:**  
  * Users can input the name of a product and the number of recommendations they wish to receive.  
  * The system then processes this request, calculates the most similar products, and displays them.

---

## 6. Technology Stack
The system was built using the following technology stack:
* **Backend:**  
  * **Flask:** A micro web framework for building the application.  
  * **SQLAlchemy:** For interacting with the MySQL database.
* **Database:**  
  * **MySQL:** A relational database used to store user data, product data, and recommendation results.
* **Machine Learning:**  
  * **Scikit-learn:** A library for performing text vectorization (TF-IDF) and calculating cosine similarity between products.
* **Frontend:**  
  * **HTML/CSS/JS:** For the user interface and product display.

---

## 7. Challenges and Solutions
1. **Data Quality:**  
   Incomplete or inconsistent product data could affect recommendation quality. The data was cleaned and preprocessed by filling missing values and standardizing column names.
2. **Scalability:**  
   As the number of products grows, generating recommendations for each product can become computationally expensive. The system could be optimized using techniques like caching or pre-computing similarity scores.
3. **Security:**  
   Passwords are stored in plain text in the database. To address this, it is recommended to use password hashing (e.g., using werkzeug.security) to secure user credentials.

---

## 8. Evaluation and Testing
To evaluate the effectiveness of the recommendation system:
* **Offline Evaluation:**  
  The recommendation algorithm is tested offline by checking the similarity between products using predefined sample data and comparing recommendations.
* **User Testing:**  
  User feedback on the recommendations can be gathered through surveys or A/B testing to improve recommendation accuracy.

---

## 9. Future Work and Improvements
Several improvements can be made to this recommendation system:
1. **Hybrid Recommendation System:**  
   A hybrid model combining collaborative filtering (user-item interactions) and content-based filtering could be implemented for more accurate and personalized recommendations.
2. **User Profiling:**  
   The system could collect user interaction data (e.g., products viewed, products purchased) and use this information to build more personalized user profiles.
3. **Real-Time Recommendations:**  
   Integrating real-time user interaction data and updating recommendations dynamically as users browse the site.
4. **Password Security:**  
   Implement password hashing and salting for better security practices in user authentication.

---

## 10. Conclusion
The e-commerce recommendation system implemented in this project offers a basic yet functional platform for product recommendations. By leveraging content-based filtering, the system successfully recommends products based on their similarity to a given product. The use of Flask and SQLAlchemy provides a lightweight and scalable backend, and with further enhancements like hybrid recommendation algorithms and user profiling, this system has the potential to significantly improve the shopping experience for users.

---
### Installation Guide

Follow these steps to run the project on your local machine.

### 1) Clone the Project:

clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/E-Commerce-Recommendation-System.git
```
### 2) Navigate to the Project Directory: 
After cloning the repository, navigate to the project directory:

```bash
cd E-Commerce-Recommendation-System
```

### 3) Create a Virtual Environment: 
Create a virtual environment for the project:

```bash
python -m venv venv
```

### 4) Activate the Virtual Environment:
* On Windows:
```bash
.\venv\Scripts\activate
```
* On macOS/Linux:
```bash
source venv/bin/activate
```

### 5) Install the Required Dependencies: 
Once the virtual environment is activated, install the dependencies required for the project:
```bash
pip install -r requirements.txt
```
### 6) Run the Flask Application: 
You are now ready to run the Flask application:
```bash
python app.py
```
The application will be accessible at http://127.0.0.1:5000.


### Future Work & Improvements
* Improve recommendation accuracy with more advanced models (e.g., deep learning-based models).
* Implement real-time recommendation updates based on user interactions.
* Expand the recommendation engine to handle more data sources (e.g., user demographics, product reviews).
### Challenges
* Handling large-scale data efficiently for real-time recommendations.
* Optimizing the recommendation algorithms to handle dynamic user behavior.

---

### Explanation of Sections:

1. **Overview**: Provides a summary of the e-commerce recommendation system and its purpose.
2. **Key Features**: Lists the main functionalities that the project offers.
3. **Tech Stack**: Details the technologies used in the project, including backend (Flask), frontend (HTML/CSS), and machine learning tools (TensorFlow, Scikit-learn).
4. **Installation Guide**: Contains step-by-step instructions for setting up the project on a local machine.
   - **Clone the Project**: Guides users to clone the GitHub repository.
   - **Navigate to the Project Directory**: Shows how to change directories after cloning the repo.
   - **Create a Virtual Environment**: Explains how to create a Python virtual environment to manage dependencies.
   - **Activate the Virtual Environment**: Provides commands for activating the environment on different OSes.
   - **Install the Required Dependencies**: Directs users to install the necessary libraries from the `requirements.txt`.
   - **Run the Flask Application**: The final step to run the application.
5. **License**: Specifies the license under which the project is available (MIT License).
6. **Future Work & Improvements**: Suggests areas where the project can be further enhanced or extended.
7. **Challenges**: Discusses potential challenges in building and scaling the recommendation system.
