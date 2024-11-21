---
# Weather Prediction Model Evaluation  

This project evaluates the performance of a temperature prediction model using actual and predicted temperature data. The performance is assessed using metrics like **MAE**, **MSE**, and **R²**, and the results are visualized in a plot comparing actual vs. predicted temperatures over time.

---

## Table of Contents  

1. [Introduction](#introduction)  
2. [Evaluation Metrics](#evaluation-metrics)  
3. [Results Visualization](#results-visualization)  
4. [Conclusion](#conclusion)  

---

## Introduction  

The objective of this project is to predict temperature over time using a machine learning model. The model's predictions are evaluated against the actual data using statistical metrics and visualized for better insights.

---

## Evaluation Metrics  

The following metrics were calculated to assess the model's accuracy:  

- **Mean Absolute Error (MAE)**:  
  Measures the average magnitude of errors between predicted and actual values. Lower values indicate better performance.  
  ```python
  MAE = Σ|Actual - Predicted| / N
  ```
  
- **Mean Squared Error (MSE)**:  
  Measures the average squared difference between predicted and actual values. It penalizes larger errors more heavily.  
  ```python
  MSE = Σ(Actual - Predicted)² / N
  ```

- **R-squared (R²)**:  
  Indicates how well the model explains the variability in the data. A value closer to 1 represents better performance.  
  ```python
  R² = 1 - (Σ(Actual - Predicted)² / Σ(Actual - Mean(Actual))²)
  ```

### Results:  
---

## Results Visualization  

The plot below shows the comparison between actual and predicted temperature values for the test dataset:  

- The **blue line** represents actual temperature values.  
- The **red line** represents predicted temperature values.  

### Code for Plot Generation:

```python
fig_test = px.line(df_pred[1000:], title="Test Results", 
                   labels={'value': 'Temperature', 'index': 'Time'},
                   line_shape='linear')
fig_test.update_traces(name='Actual', line_color='blue')
fig_test.add_scatter(x=df_pred.index[1000:], y=df_pred['predicted'][1000:], 
                      mode='lines', name='Predicted', line=dict(color='red'))
fig_test.update_layout(width=700, height=500)
fig_test.show()
```

---

## Conclusion  

The temperature prediction model demonstrates reasonable accuracy as reflected by the evaluation metrics. The visualization highlights areas where the model performs well and where it deviates, guiding future improvements.

---
