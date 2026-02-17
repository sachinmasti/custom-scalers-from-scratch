# 🔢 ML Preprocessing From Scratch

Custom implementation of **StandardScaler** and **MinMaxScaler** — without sklearn, using only NumPy and Pandas!

---

## 📌 What's Implemented?

### 1. Standard Scaler (`stad_scalers`)
Brings data to **mean = 0** and **std = 1**.

**Formula:**
```
z = (x - mean) / std
```

### 2. Min-Max Scaler (`min_max_scalar`)
Normalizes data between **0 and 1**.

**Formula:**
```
x_norm = (x - min) / (max - min)
```

---

## 🧠 Why Build This?

`StandardScaler` and `MinMaxScaler` already exist in sklearn — but building them from scratch gives a **deeper understanding** of how they actually work under the hood.

> "When you build it yourself, you truly understand it!"

---

## 📂 Code

```python
import pandas as pd
import numpy as np

# Standard Scaler
def stad_scalers(values=[list]) -> list:
    return (values - np.mean(values)) / np.std(values)

# Min-Max Scaler
def min_max_scalar(values=[list]) -> list:
    return (values - min(values)) / (max(values) - min(values))
```

---

## 📊 Dataset (Example)

Used a synthetic cricket players dataset:

| Column | Description |
|--------|-------------|
| `name` | Player name |
| `runs` | Random runs (3000–5000) |
| `city` | Player's city |
| `age` | Random age (26–45) |

```python
data = {
    'name': ['sachin', 'virat', 'rohit', 'dhoni', 'rahul',
             'surya', 'hardik', 'bahji', 'yuvraj', 'rishabh'],
    'runs': np.random.randint(3000, 5000, 10),
    'city': ['mumbai', 'dilhi', 'mumbai', 'ranchi', 'mumbai',
             'varodara', 'punjab', 'Jalandhar', 'Chandigarh', 'Roorkee'],
    'age': np.random.randint(26, 45, 10)
}

df = pd.DataFrame(data)
```

---

## ✅ Output (Sample)

| name | runs | city | age | scaled runs | normalize age |
|------|------|------|-----|-------------|---------------|
| sachin | 4822 | mumbai | 32 | 1.748 | 0.333 |
| virat | 3262 | dilhi | 41 | -1.142 | 0.933 |
| rohit | 4091 | mumbai | 28 | 0.393 | 0.066 |
| dhoni | 3904 | ranchi | 27 | 0.047 | 0.000 |
| rahul | 3732 | mumbai | 42 | -0.271 | 1.000 |

- `scaled runs` → StandardScaler applied (mean ~0, std ~1)
- `normalize age` → MinMaxScaler applied (0 to 1 range)

---

## 🚀 How to Run?

1. Clone the repo:
```bash
git clone https://github.com/your-username/ml-preprocessing-from-scratch.git
cd ml-preprocessing-from-scratch
```

2. Install dependencies:
```bash
pip install numpy pandas
```

3. Open the notebook:
```bash
jupyter notebook
```

---

## 🛠️ Tech Stack

- Python 3.x
- NumPy
- Pandas
- Jupyter Notebook

---

## 🙋 Author

**Sachin Masti**  
ML enthusiast | Building things from scratch to understand them deeply 💡

---

## ⭐ If you found this helpful, drop a star!
