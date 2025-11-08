# 🧮 Practice No. 3 – Object Oriented Programming  
**Course:** Programming Languages and Paradigms  
**Program:** Ingeniería de Sistemas – Universidad EAFIT  
**Students:** Daniela Giraldo Salas
**Date:** Nov 8, 2025  
**Language:** C++  

---

## 🎯 Objectives

- Apply the basic concepts of **Object-Oriented Programming (OOP)**.  
- Implement a **Multiple Linear Regression** model in C++ using an OOP approach.  
- Reinforce encapsulation, abstraction, and modularity principles.  
- Present the implementation and results clearly through GitHub and a presentation video.

---

## 📘 Project Overview

This project develops a **Multiple Linear Regression (MLR)** framework in C++.  
It can train, predict, and evaluate models using real datasets without external libraries.  
The program supports **simple** and **multiple** regression and performs manual matrix operations.

Two datasets are used:
1. `ice_cream_selling_data.csv` → *Simple regression*  
2. `student_exam_scores.csv` → *Multiple regression*  

---

## 🧱 Class Design

### **Class: `LinearRegression`**

| Attribute | Type | Description |
|------------|------|-------------|
| `weights` | `std::vector<double>` | Stores model coefficients. |
| `bias` | `double` | Represents the intercept term. |

### **Public Methods**

| Method | Description |
|---------|-------------|
| `fit(X, y)` | Trains the model using the Normal Equation. |
| `predict(X)` | Returns predicted outputs for given inputs. |
| `score(X, y)` | Calculates R² score for model accuracy. |
| `scaleData(X)` | Normalizes features to improve convergence. |
| `getWeights()` | Returns model weights. |
| `getBias()` | Returns model bias. |

---

## 📂 Project Structure

```
📦 LinearRegression-CPP
├── src/
│   ├── LinearRegression.h
│   ├── LinearRegression.cpp
│   └── main.cpp
├── data/
│   ├── ice_cream_selling_data.csv
│   └── student_exam_scores.csv
├── README.md
└── Makefile
```

---

## 🧾 File Descriptions

### `LinearRegression.h`
Defines the class and method prototypes.

### `LinearRegression.cpp`
Implements all mathematical operations:  
- Matrix transposition, multiplication, and inversion.  
- Training (`fit`), prediction (`predict`), and evaluation (`score`).

### `main.cpp`
Demonstrates the full pipeline:  
1. Load dataset.  
2. Train model.  
3. Display weights, bias, and predictions.  

Example snippet:
```cpp
LinearRegression model;
model.fit(X_train, y_train);
std::cout << "Weights: " << model.getWeights()[0] << " " << model.getWeights()[1] << std::endl;
std::cout << "Bias: " << model.getBias() << std::endl;
```

---

## 🧪 Testing and Results

| Dataset | Type | Output | R² Score |
|----------|------|---------|-----------|
| `ice_cream_selling_data.csv` | Simple Regression | Ice cream sales | 0.98 |
| `student_exam_scores.csv` | Multiple Regression | Exam scores | 0.94 |

Console output example:
```
Weights: 1.98 2.04
Bias: 0.56
Predictions: 8.98 11.04
Score: 0.948
```

---

## 🔧 Compilation and Execution

### Manual Compilation:
```bash
g++ src/main.cpp src/LinearRegression.cpp -o regression -std=c++17
```

### Run:
```bash
./regression
```

### Makefile (optional):
```makefile
CXX = g++
CXXFLAGS = -std=c++17 -Wall
SRC = src/main.cpp src/LinearRegression.cpp
TARGET = regression

all:
	$(CXX) $(CXXFLAGS) $(SRC) -o $(TARGET)

run: all
	./$(TARGET)

clean:
	rm -f $(TARGET)
```

---

## ⚠️ Common Issues

| Problem | Cause | Solution |
|----------|--------|-----------|
| Singular matrix inversion | Non-invertible matrix | Add small regularization term to diagonal. |
| Low accuracy | Unscaled data | Normalize using `scaleData()`. |
| Dimension mismatch | X/y size mismatch | Validate input dimensions before training. |

---

## 📹 Video Presentation

**YouTube Link:** ----

---

## ✅ Conclusions

1. Implementing regression in C++ improves understanding of OOP and matrix algebra.  
2. Manual implementation of the Normal Equation reinforces algorithmic thinking.  
3. Data scaling and input validation are key to stable and accurate models.  

---

## 📚 References

- EAFIT Interactiva – Datasets: `ice_cream_selling_data.csv`, `student_exam_scores.csv`  
- GitHub Docs – [Basic Markdown Syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)  
- Course Material: *Programming Languages and Paradigms*  
- *Mathematics for Machine Learning*, Cambridge University Press, 2020
- some IA help for a better looking README :)  

---
