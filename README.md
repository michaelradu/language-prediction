# Language Prediction Model + FastAPI + Docker = ❤️

## What is this?
This project combines a custom language prediction model with FastAPI and Docker to create a powerful and scalable language prediction system. The model, built on advanced language processing techniques, can predict and understand user input in various languages.

## Features
- **Language Prediction:** The core functionality of this project revolves around predicting the language of a given text input. Version `0.1.0` of the model has been trained on the [`Language Detection.csv`](https://www.kaggle.com/datasets/basilb2s/language-detection) dataset to provide accurate predictions. Future versions with more content diverse training will yield an even more efficient model.

- **FastAPI Integration:** FastAPI is utilized to create a fast, modern, and efficient API for interacting with the language prediction model. It ensures low latency and high performance, making the system suitable for real-time applications.

- **Dockerized Deployment:** The entire application, including the language model and FastAPI, is containerized using Docker. This allows for easy deployment and scalability, ensuring consistency across different environments.

## Getting Started
To run this language prediction system locally, follow these steps:

### 1. Clone the Repository:
```bash
git clone https://github.com/michaelradu/language-prediction.git
```

### 2. Build Docker Image:
```bash
cd language-prediction
docker build -t language-prediction-app .
```

### 3. Run Docker Container:
```bash
docker run -p 8000:8000 language-prediction-app
```

### 4. Access the API:
Open your web browser and go to http://localhost:8000/ to interact with the API using the Health Check. Or send a `GET` request via an API Platform Tool such as [Postman](https://www.postman.com/).

## API Endpoints

- `/predict`: Use this endpoint to submit text and get predictions about its language.

### Sample Request
```bash
curl -X 'POST' \
  'http://localhost:8000/predict' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "text": "Bonjour, comment ça va?"
}'
```

### Dependencies
- FastAPI + Pydantic
- Docker
- Your favorite web browser

## Project Structure
- `app/app`: This directory contains the FastAPI app endpoint.
- `data`: The datasets used for training and testing the models are stored in this directory.
- `models`: This directory houses the trained models, primarily for archival purposes.
- `notebooks`: Jupyter Notebooks utilized in the model training process are stored in this directory.

## Model Refitting Process
Refitting or retraining the model is a straightforward process. To achieve this:

1. Add a new dataset to the `data` directory.
2. Edit the `LanguageDetection.ipynb` notebook to incorporate the new dataset.
3. Implement any necessary modifications to the model pipeline according to your requirements.
4. Run all the code blocks in the notebook.
5. Update the version, and a new model, named `trained_pipeline-0.1.1.pkl`, will be saved in the models directory.

## Contributions Welcome
Contributions to this project are highly encouraged! If you have ideas for improvements, bug fixes, or new features, feel free to open an issue or submit a pull request. Let's collaborate to make this language prediction system even better.

## License
This code is licensed under the GNU General Public License, version 3 (GPL-3.0). See the [LICENSE](/LICENSE) file for more details.

## Acknowledgments
Special thanks to the open-source community for their contributions to FastAPI and Docker and for their copious amounts of educational content, making projects like this possible.

Feel free to explore, experiment, and integrate this language prediction system into your applications. Happy coding!