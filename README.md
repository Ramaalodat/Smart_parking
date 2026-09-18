# 🚗 Smart Parking Recommendation System

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28%2B-FF4B4B.svg)](https://streamlit.io/)
[![Scikit-Learn](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-F7931E.svg)](https://scikit-learn.org/)
[![Folium](https://img.shields.io/badge/Maps-Folium-green.svg)](https://python-visualization.github.io/folium/)
[![License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](#license)

An AI-powered **Smart Parking Recommendation System** built with **Streamlit**, **Machine Learning**, and **Folium Interactive Maps**. The application predicts parking spot availability and occupancy status in real-time based on historical data, area selection, time of day, and day of the week, helping drivers find available parking effortlessly.

---

## 📌 Key Features

- **🔮 ML-Based Parking Prediction**: Predicts parking availability status (`Available`, `Busy`, `Full`) using a trained Machine Learning classification model.
- **💡 Smart Recommendation Engine**: Analyzes nearby parking options and recommends the best parking spot with the lowest occupancy rate.
- **🗺️ Interactive Map Visualization**: Integrates **Folium** maps with color-coded markers (Green for Available, Orange/Red for Busy/Full) centered on selected areas.
- **🎛️ Real-Time Search Filters**: User-friendly sidebar controls to select target areas, specific hours of the day (0–23), and day of the week.
- **⚡ Fast & Efficient**: Leverages Streamlit's caching (`@st.cache_resource`) for fast data and model loading.

---

## 🛠️ Tech Stack

- **Frontend & Dashboard**: [Streamlit](https://streamlit.io/)
- **Geospatial Mapping**: [Folium](https://python-visualization.github.io/folium/) & `streamlit-folium`
- **Data Manipulation**: [Pandas](https://pandas.pydata.org/)
- **Model Deserialization**: `joblib`
- **Machine Learning**: `scikit-learn` (StandardScaler & Classifier Model)
- **Language**: Python 3.8+

---

## 📁 Repository Structure

```gfm
Smart_parking/
├── app.py                   # Main Streamlit web application & UI logic
├── final_merged_fixed.csv   # Processed dataset containing parking & area information
├── parking_model.pkl        # Trained Machine Learning model for parking prediction
├── parking_scaler.pkl       # Scaler artifact for feature normalization
├── README.md                # Project documentation
└── .snapshots/              # Configuration & snapshot backups
```

---

## 🚀 Quick Start Guide

### 1. Prerequisites

Ensure you have Python 3.8 or higher installed on your system.

### 2. Clone the Repository

```bash
git clone https://github.com/Ramaalodat/Smart_parking.git
cd Smart_parking
```

### 3. Install Dependencies

Install the required Python packages:

```bash
pip install streamlit pandas joblib folium streamlit-folium scikit-learn
```

---

## 💻 Running the Application

Launch the Streamlit web server:

```bash
streamlit run app.py
```

Once executed, the application will open automatically in your default web browser at `http://localhost:8501`.

---

## 🎯 How It Works

1. **Select Area & Time**: Use the sidebar to pick a target area/destination, hour of the day, and day of the week.
2. **Availability Prediction**: The app transforms user inputs, normalizes them using `parking_scaler.pkl`, and passes them to `parking_model.pkl` to compute the predicted status.
3. **Recommendation**: The algorithm filters available parking locations in the selected area and highlights the optimal spot with the lowest occupancy percentage.
4. **Geospatial Rendering**: An interactive Folium map displays the location marker color-coded according to real-time status.

---

## 📊 Model & Dataset Information

- **Features Used**: `hour`, `day_of_week`, and one-hot encoded `area_*` indicators.
- **Output Classes**:
  - `0`: Available 🟢
  - `1`: Busy 🟠
  - `2`: Full 🔴
- **Metrics**: Evaluated on historical occupancy rates and spatial data across major Bangalore zones (e.g., Koramangala, Indiranagar, Bellandur, Brigade Road).

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check out the [issues page](https://github.com/Ramaalodat/Smart_parking/issues).

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
