# MobileNetV2 Image Classifier

A deep learning web application that classifies uploaded images using **MobileNetV2** pretrained on ImageNet. Built with FastAPI on the backend and a lightweight HTML/CSS/JS frontend, deployed via GitHub + Render.

**Live demo:** https://mobilenet-classifier-c1jn.onrender.com/

> Hosted on Render's free tier — the first request after a period of inactivity may take 30–60 seconds while the service wakes up.

## Features

- Upload an image (JPG, JPEG, PNG, or WEBP, up to 10 MB)
- Get the top-3 predicted classes with confidence scores
- Simple drag-and-drop interface with live image preview
- Health check endpoint for deployment verification

## Tech Stack

- **Backend:** FastAPI, TensorFlow/Keras (MobileNetV2), Pillow, NumPy
- **Frontend:** HTML, CSS, vanilla JavaScript
- **Deployment:** GitHub + Render

## Project Structure

```
mobilenet-classifier/
├── app.py
├── requirements.txt
├── .python-version
├── index.html
├── css/
│   └── style.css
└── js/
    └── script.js
```

## API Endpoints

| Endpoint       | Method | Description                                      |
|----------------|--------|---------------------------------------------------|
| `/`            | GET    | Serves the frontend                                |
| `/health`      | GET    | Returns service status                             |
| `/api/predict` | POST   | Accepts an image file, returns top-3 predictions   |

## Running Locally

```bash
# Install dependencies
pip install -r requirements.txt

# Start the server
uvicorn app:app --reload
```

Then open `http://127.0.0.1:8000` in your browser.

## Deployment

This app is deployed on [Render](https://render.com) as a Python Web Service:

- **Build Command:** `pip install -r requirements.txt`
- **Start Command:** `uvicorn app:app --host 0.0.0.0 --port $PORT`
- **Health Check Path:** `/health`

## Notes

- No API keys or credentials are required to run this app.
- `venv/` and `__pycache__/` are excluded from version control (see `.gitignore`).

-A part of Deep Learning Experiment
