
# Enhancing Broadcast Operations with Real-Time Pitch Classification: A Case Study on Kevin Gausman

## 📘 Overview

This project explores **real-time pitch classification** using in-game data from MLB pitcher **Kevin Gausman**. By applying machine learning techniques, particularly the **K-Nearest Neighbors (KNN)** algorithm, the goal was to classify different pitch types based on measurable release and movement characteristics.

The analysis demonstrates how pitch-tracking data can be leveraged to improve **broadcast analytics**, offering insights into how machine learning can identify and differentiate pitch types during live gameplay.

---

## 🧠 Methodology

### Data

The dataset consists of pitch-by-pitch data for Kevin Gausman, including:

* `release_speed`
* `release_spin_rate`
* `pfx_x`, `pfx_z` (horizontal and vertical movement)
* `stand` (batter stance)
* `pitch_type`

Missing values were imputed using median values, and numerical features were standardized (z-score normalization) to ensure balanced distance-based calculations.

### Model Development

Two KNN models were developed:

1. **Baseline model:** Used only `release_speed` as a feature (k=3)
2. **Full model:** Included all available features

A **grid search with 5-fold cross-validation** was used to optimize the number of neighbors (`k`), ultimately identifying **k = 51** as the optimal value.

---

## 📊 Results

* **Best model accuracy:** `0.986`
* The confusion matrix showed excellent performance for **four-seam fastballs**, **split-finger fastballs**, and **sliders**.
* However, **sinkers** were often misclassified as **four-seam fastballs** due to overlapping velocity and movement profiles.

These results indicate that the model performs well overall but has challenges in differentiating pitches with similar trajectories.

---

## 💬 Discussion & Conclusion

While the KNN model demonstrates high accuracy, **it is not yet suitable for live MLB broadcasting** due to certain misclassifications and limited generalizability:

* It was trained solely on **Kevin Gausman’s** data.
* The model is sensitive to scaling, missing values, and the choice of hyperparameters.
* Real-world deployment would require additional robustness testing and multi-pitcher data.

Nevertheless, the study confirms that **real-time pitch classification is feasible** and could enhance baseball analytics and broadcast experiences with further refinement.

---

## 🚀 Future Work

* Expand dataset to include multiple pitchers and pitch types.
* Integrate more features such as **release angle**, **pitch location**, or **spin axis**.
* Experiment with **advanced models** such as Random Forests or Gradient Boosting.
* Deploy as a real-time dashboard for analysts or broadcasters.

---

## 🧩 Technologies Used

* **Python**
* **scikit-learn**
* **pandas**, **numpy**
* **matplotlib**, **seaborn**
* **Jupyter / Quarto**

---

## 🧑‍💻 Author

**Sahil Sangani**
University of Illinois Urbana-Champaign
📫 [LinkedIn](https://linkedin.com/in/sahildsangani) | [GitHub](https://github.com/SahilDSangani)

