---

## ⚡ Energy Price Forecasting using GCN, GraphSAGE, and PINNs

This repository presents **EnergyCast**, a hybrid deep learning framework for forecasting electricity prices using **Graph Convolutional Networks (GCN)**, **GraphSAGE**, and **Physics-Informed Neural Networks (PINNs)**. The models are designed to capture complex **spatial-temporal dependencies** and integrate **domain-specific physical constraints** to enhance forecasting accuracy, reliability, and interpretability in energy markets.

---

### 🧠 Core Methodology

1. **Graph Convolutional Network (GCN)**
   Learns node-level representations by aggregating features from spatial neighbors, leveraging graph structures formed using region-wise correlations and proximity.

2. **GraphSAGE**
   Scalable and inductive GNN model that samples neighbors and generalizes to unseen nodes, suitable for dynamic energy grids.

3. **Physics-Informed Neural Networks (PINNs)**
   Incorporates physical laws (e.g., energy balance equations) into the training process by embedding differential constraints into the loss function. This ensures physically plausible predictions even in low-data or noisy conditions.

---

### 🧾 Dataset

* The model is trained on **35,000+ hourly records** extracted from an open energy dataset (`energy_dataset.csv`)
* Includes **29 features**: actual and forecasted solar/wind generation, fossil and renewable contributions, temperature, demand, and day-ahead prices
* A graph is constructed using **KNN** and **feature correlation**, where:

  * **Nodes** represent geographic or logical energy market zones
  * **Edges** reflect spatial and feature-based dependencies
* Preprocessing includes removal of zero-variance and missing-value columns and normalization of input features

---

### 🔬 Learning Objective

The goal is to **predict real-time electricity prices** using historical conditions, spatial interdependencies, and physical domain knowledge.
All models were trained using a supervised learning setup with:

* **Input**: historical prices, forecasted demand, generation by source, weather
* **Output**: predicted electricity price (continuous regression)

---

### 📚 Models Summary

* **GCN**: Best performance with lowest RMSE and MAPE; excellent at learning from structured graph data
* **GraphSAGE**: Inductive capability makes it suitable for evolving grids, but needs further tuning for accuracy
* **PINNs**: Achieves physically consistent forecasts by incorporating energy balance equations in the loss function

---

