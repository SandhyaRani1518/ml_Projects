# Machine Learning Projects

A collection of machine-learning experiments and small applications.

## Featured project: Diabetes Prediction Web App

The `diabets with streamlit/` directory contains a Streamlit application that loads a saved machine-learning model and collects eight input features to produce a model prediction.

### Tech stack

- Python
- Streamlit
- NumPy
- Joblib
- Jupyter Notebook

### Run locally

1. Clone the repository:
   ```bash
   git clone https://github.com/SandhyaRani1518/ml_Projects.git
   cd ml_Projects
   ```
2. Open the application directory:
   ```bash
   cd "diabets with streamlit"
   ```
3. Install the required packages:
   ```bash
   pip install streamlit numpy joblib
   ```
4. Ensure `model.pkl` is present in the same directory as `app.py`.
5. Start the app:
   ```bash
   streamlit run app.py
   ```

## Project files

- `diabets with streamlit/app.py` — Streamlit user interface and prediction logic.
- `diabets with streamlit/main.ipynb` — Jupyter notebook.
- `diabets with streamlit/diabetes.csv` — dataset file.
- `diabets with streamlit/model.pkl` — serialized model.

**Important:** This is an educational machine-learning demonstration. Its output is not a medical diagnosis and must not be used to make healthcare decisions.
