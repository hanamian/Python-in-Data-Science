# ------------ Handling Duplikasi Data ------------ 
#                    Deduplikasi

There is a similarity in some rows.
### 1. Mengecek duplikasi data
```python
retail_raw.duplicated(subset=None)
```

### 2. Menghapus duplikat
```python
retail_raw.drop_duplicates()

# atau
retail_raw.drop_duplicates(inplace=True)
```
