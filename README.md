# Anomaly Detection in Cryptocurrency Returns

This project implements a **robust anomaly detection** pipeline on 5-minute log returns of crypto assets using a **rolling 30-day** window and **Median + MAD** robust Z-scores.

## Methodology
1. Load 1-minute K-line data.
2. Aggregate into 5-minute log returns: r_t = ln(P_t / P_{t-5}).
3. Compute robust Z: Z*_t = (r_t - median) / (1.4826 × MAD).
4. Flag anomalies where |Z*| > 4.
5. Visualize Z vs. time and highlight extremes.

## Repository Structure
- `anomaly_detection.ipynb` → Jupyter notebook with code, explanations, and visualizations.
- `anomaly_detection.py` → Python script version of the notebook.
- `requirements.txt` → Dependencies needed to run the project.
- `TRUMPUSDT_anomalies.csv` → (optional) Example output with detected anomalies.

## Installation
Clone the repository and install the dependencies:

```bash
git clone https://github.com/YourUsername/crypto-anomaly-detection.git
cd crypto-anomaly-detection
pip install -r requirements.txt
```

## Usage

### Run the Notebook
Open Jupyter and run the notebook step by step:

```bash
jupyter notebook anomaly_detection.ipynb
```

### Run the Script
Run the Python script directly:

```bash
python anomaly_detection.py
```

## Example Output
The script will generate:
- A plot of robust Z-scores with anomalies highlighted.
- A CSV file (`anomalias_TRUMPUSDT.csv`) containing timestamps and Z-scores of detected anomalies.

## References
- Rousseeuw, P. J., & Croux, C. (1993). Alternatives to the Median Absolute Deviation.
- Aggarwal, C. C. (2017). Outlier Analysis (2nd ed.).
- Cont, R. (2001). Empirical properties of asset returns. Quantitative Finance.
- Wikipedia: [Median absolute deviation](https://en.wikipedia.org/wiki/Median_absolute_deviation)
