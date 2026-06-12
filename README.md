# 🏅 Sports Person Classifier
 
A machine learning web app that identifies famous sports persons from images using face detection and wavelet-based feature extraction.
 
Upload a photo and the model will classify it as one of five athletes: **Virat Kohli, Maria Sharapova, Roger Federer, Lionel Messi, or Serena Williams**.
 
---
 
## 🎥 Demo
 
[![UI Preview](UI/images/upload.png)
](https://github.com/user-attachments/assets/b999493e-1df0-44a1-9f79-b6d64dd2ee3e)

---
 
## 🛠️ Tech Stack
 
| Layer | Tools |
|-------|-------|
| ML Model | scikit-learn (SVM, Random Forest, Logistic Regression) |
| Image Processing | OpenCV, PyWavelets |
| Backend | Python, Flask |
| Frontend | HTML, CSS, JavaScript, Dropzone.js |
 
---
 
## 🧠 How It Works
 
1. **Face Detection** — OpenCV Haar cascades detect faces and eyes in the uploaded image
2. **Feature Extraction** — Raw pixel data is combined with wavelet-transformed features (PyWavelets `db1`)
3. **Classification** — A trained model (GridSearchCV-tuned) predicts the sports person
4. **Result** — Returns the predicted class with confidence probabilities for all 5 athletes
---
 
## 📁 Project Structure
 
```
SportsPersonClassifier/
│
├── model/
│   ├── requirements.txt        # Python dependencies
│   └── (artifacts not included — see setup below)
│
├── server/
│   ├── server.py               # Flask API server
│   ├── util.py                 # Model loading & image classification logic
│   └── wavelet.py              # Wavelet transform helper
│
└── UI/
    ├── app.html                # Frontend interface
    ├── app.js                  # API calls & result rendering
    ├── app.css                 # Styling
    └── images/                 # Athlete reference images
```
 
---
 
## ⚙️ Setup & Run
 
### 1. Clone the repo
```bash
git clone https://github.com/hasanjaved180598/Sports_Person_Classifier.git
cd Sports_Person_Classifier
```
 
### 2. Install dependencies
```bash
pip install -r model/requirements.txt
```
 
### 3. Train the model
Open and run the Jupyter notebook inside the `model/` folder. This will generate:
- `server/artifacts/saved_model.pkl`
- `server/artifacts/class_dictionary.json`
### 4. Start the Flask server
```bash
cd server
python server.py
```
 
### 5. Open the UI
Open `UI/app.html` in your browser. Make sure the Flask server is running on `http://127.0.0.1:5000`.
 
---
 
## 📊 Model Performance
 
The model was trained using **GridSearchCV** across three algorithms:
 
| Algorithm | Notes |
|-----------|-------|
| SVM | Best performer — selected as final model |
| Random Forest | Good accuracy, slightly lower than SVM |
| Logistic Regression | Baseline comparison |
 
---
 
## ⚠️ Notes
 
- Model artifacts (`saved_model.pkl`, `class_dictionary.json`) and training datasets are **not included** in this repo. Run the notebook to generate them.
- Requires a clear frontal face with **both eyes visible** for accurate classification.
- Tested on Python 3.8+
---
 
> *Because your model should know the difference between Messi and Federer.* ⚽🎾
