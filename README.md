# Stock Market Anomaly Detection

This project demonstrates anomaly detection in stock market data using the **Isolation Forest** algorithm. The aim is to identify unusual patterns in stock prices and trading volumes, which might indicate anomalies such as unexpected market behavior or data errors.

## Features
- Cleans raw stock market data (removes dollar signs, converts data types).
- Detects anomalies in key metrics: closing price, opening price, high, low, and trading volume.
- Visualizes the anomalies on a time series plot.
- Exports detected anomalies to a CSV file for further analysis.

## Dataset
The dataset contains historical stock market data with the following columns:
- **Company**: Name of the company (e.g., AAPL for Apple).
- **Date**: Date of the record.
- **Close/Last**: Closing price (e.g., $193.99).
- **Volume**: Number of shares traded.
- **Open**: Opening price.
- **High**: Highest price during the trading day.
- **Low**: Lowest price during the trading day.

> Note: Ensure the dataset is in `.csv` format and formatted correctly before running the project.

## Workflow
1. **Data Cleaning**:
   - Parses the `Close/Last`, `Open`, `High`, and `Low` columns by removing dollar signs and converting them to numeric values.
   - Converts `Date` to a proper datetime format.
   - Removes any rows with missing values.

2. **Anomaly Detection**:
   - Uses the **Isolation Forest** algorithm to detect anomalies.
   - Labels each data point as `1` (normal) or `-1` (anomaly).
   - Outputs a filtered dataset of anomalies.

3. **Visualization**:
   - Plots normal and anomalous data points on a time series graph for easy interpretation.

4. **Export**:
   - Saves anomalies to a file named `anomalies.csv`.

## Prerequisites
- Python 3.7+
- Required Python libraries:
  - `pandas`
  - `scikit-learn`
  - `matplotlib`

Install the dependencies using:
```bash
pip install pandas scikit-learn matplotlib
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/stock-anomaly-detection.git
   cd stock-anomaly-detection
   ```
2. Place your dataset file (`data.csv`) in the project directory.
3. Run the script:
   ```bash
   python detect_anomalies.py
   ```
4. View the generated plot and check the `anomalies.csv` file for detected anomalies.

## Output
- **Anomalies CSV**: Contains a list of all detected anomalies with relevant metrics.
- **Visualization**: A scatter plot highlighting normal data and anomalies.

## Example
### Detected Anomalies:
| Company | Date       | Close/Last | Volume    | Open   | High   | Low    |
|---------|------------|------------|-----------|--------|--------|--------|
| NFLX    | 2022-01-20 | 508.25     | 12658990  | 517.75 | 526.64 | 506.93 |
| NFLX    | 2022-01-18 | 510.80     | 4844418   | 520.08 | 521.75 | 508.68 |

### Visualization:
The chart shows anomalies in red and normal data points in blue, making it easy to spot unusual trends.

## Future Enhancements
- Incorporate additional anomaly detection methods for comparison.
- Allow real-time anomaly detection on live stock data.
- Add support for more advanced visualizations and dashboards.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
