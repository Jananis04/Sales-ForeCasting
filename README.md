# Sales-ForeCasting


Data Understanding and Assumptions
Dataset consists of sales dat with the following columns:
  InvoiceNo	Invoice number; Unique identifier for a transaction.
  StockCode	Product (item) code.
  Description	Product name/description.
  Quantity	Quantity of product purchased per transaction.
  InvoiceDate	Date and time of invoice creation.
  UnitPrice	Price per unit of product.
  CustomerID	Customer identifier (can be null).
  Country	Country of customer.

Modeling Approach
Model: XGBoost Regressor.

Validation: TimeSeriesSplit to maintain chronological order and avoid data leakage.
Target Transformation: Revenue was transformed with log1p before training and predictions were inverse-transformed using expm1 to obtain revenue in original scale.
Evaluation Metrics:

Mean Squared Error (MSE) — measures average squared error, sensitive to outliers.

Root Mean Squared Error (RMSE) — square root of MSE, interpretable in original units.

Results and Interpretations
Across validation splits, the model shows:

MSE:0.11

RMSE:0.31

The model effectively captures revenue trends, but some deviations highlight room for improvement, possibly with more features or tuning.
![image](https://github.com/user-attachments/assets/202ca1cf-f9bf-4a51-b4c9-191155e5c4fd)


![image](https://github.com/user-attachments/assets/1f805ffc-8437-453d-a0f1-6cacc187033f)

