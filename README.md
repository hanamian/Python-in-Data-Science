# Python in Data Science

### 1. String Methods
uppercase dan capslock
```python
building    = "penthouse"
building_up = building.upper()

print(building)
print(building_up)
print(building.count("e"))
```
Result:
```
penthouse
PENTHOUSE
2
```
---
### 2. List Methods
```python
areas = [22.34, 25.33, 12.67, 32.89, 20.10]

print(areas[-2])
print(areas.index(32.89))
print(areas.count(12.67))

areas.append(10.00)
print(areas)

areas.reverse()
print(areas)
```
Result:
```
32.89
3
1
[22.34, 25.33, 12.67, 32.89, 20.1, 10.0]
[10.0, 20.1, 32.89, 12.67, 25.33, 22.34]
```
---
### 3. Import Math Library
```python
import math
from math import pi

r =7
luas = pi*r**2
keliling = 2*pi*r

print("Luasnya adalah    : " + str(luas) + " cm persegi")
print("Kelilingnya adalah: " + str(keliling) + " cm")
```
Result:
```
Luasnya adalah    : 153.93804002589985 cm persegi
Kelilingnya adalah: 43.982297150257104 cm
```
---
### 4. Numpy Array
```python
import numpy as np
height = [190, 189, 199, 210, 218, 215, 208, 205]
weight = [75000, 80000, 77000, 85000, 78000, 82000, 75000, 80000]

np_height = np.array(height)
np_weight = np.array(weight)
type(np_height)
type(np_weight)

# convert the units
np_height_m = np_height * 0.01
np_weight_kg= np_weight * 0.001

bmi = np_weight_kg / np_height_m **2
light = bmi<21

print("Height: ", np_height_m)
print("Weight: ", np_weight_kg)
print("BMI: ", bmi)
print("Light: ", light, "\n", bmi[light])
```
Result:
```
Height:  [1.9  1.89 1.99 2.1  2.18 2.15 2.08 2.05]
Weight:  [75. 80. 77. 85. 78. 82. 75. 80.]
BMI:  [20.77562327 22.39578959 19.44395344 19.27437642 16.41275987 17.73931855 17.33542899 19.03628792]
Light:  [ True False  True  True  True  True  True  True]
        [20.77562327 19.44395344 19.27437642 16.41275987 17.73931855 17.33542899 19.03628792]
```
---
### 5. 2D Numpy Array
```python
import numpy as np
baseball = [[1.9, 75],
            [1.89, 80],
            [1.99, 77],
            [2.1, 85],
            [2.18, 78]]

np_baseball= np.array(baseball)
print(type(np_baseball))
print(np_baseball.shape)
```
Result:
```
<class 'numpy.ndarray'>
(5, 2)
```
---
### 6. Subsetting 2D Numpy Array
[BARIS, KOLOM]
```python
import numpy as np

baseball = [[1.9, 75],
            [1.89, 80],
            [1.99, 77],
            [2.1, 85],
            [2.18, 78]]
np_baseball = np.array(baseball)
np_weight = np_baseball[:,1]

print(np_baseball[2,:])
print(np_baseball[4,0])
```
Result:
```
[ 1.99 77.  ]
2.18
```
---
### 7. Mean, Median, Stdev, Coorcoef (Exploratory data)
```python
import numpy as np

baseball = [[1.9, 75],
            [1.89, 80],
            [1.99, 77],
            [2.1, 85],
            [2.18, 78]]
np_baseball = np.array(baseball)

avg = np.mean(np_baseball[:,0])
print("Average           : " + str(avg))

med = np.median(np_baseball[:,0])
print("Median            : " + str(med))

stddev = np.std(np_baseball[:,0])
print("Standard Deviation: " + str(stddev))

corr = np.corrcoef(np_baseball[:,0], np_baseball[:,1])
print("Correlation       : " + str(corr))
```
Result:
```
Average           : 2.012
Median            : 1.99
Standard Deviation: 0.11303096920755844
Correlation       : [[1.         0.37925072] 
                     [0.37925072 1.        ]]
```
```python
import numpy as np

positions = ['GK', 'M', 'A', 'D', ...]
heights = [191, 184, 185, 180, ...]

np_positions= np.array(positions)
np_heights  = np.array(heights)

gk_heights   = np_heights[np_positions == 'GK']
print("Median height of goalkeepers   : " + str(np.median(gk_heights)))
```
Result:
```
Median height of goalkeepers   : 191.0
```
