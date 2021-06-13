# -------- Handling Outliers --------
- Dataset = retail_raw
- Column = quantity

### 1. Check the Quantile and IQR (Inter-Quartile-Range)
```python
Q1 = retail_raw['quantity'].quantile(0.25)
Q3 = retail_raw['quantity'].quantile(0.75)
IQR = Q3 - Q1
```
### 2. Check the shape before handling
```python
print('Shape awal: ', retail_raw.shape)
```
### 3. Removing Outliers
```python
retail_raw = retail_raw[~((retail_raw['quantity'] < (Q1 - 1.5 * IQR)) | (retail_raw['quantity'] > (Q3 + 1.5 * IQR)))]
```
### 4. Check the shape after handling
```python
print('Shape awal: ', retail_raw.shape)
```
