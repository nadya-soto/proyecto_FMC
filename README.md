# 🖥️ Uninitialized Variable Analysis in Source Code Files

## 📌 Project Description
This project aims to detect and list uninitialized variables in source code files written in Java (or similar languages). Using regular expressions in Python, the project identifies variables of various types (int, String, byte, etc.) that are declared but not initialized, and classifies the initialized instances.

## ⚙️ Techniques Used
- **Language:** Python
- **Libraries:** `re` (regular expressions)
- **Input:** Text files containing source code (Example.txt)

---

## 📂 Project Structure
- **`Proyecto1.ipynb`** 
- **`Proyecto2.ipynb`** 
- **`ProyectoFMC.ipynb`** → Main script for variable analysis
- **`Ejemplo.txt`** → Text file containing the source code to analyze
- **`README.md`** → Project documentation

---

## 📝 Analysis Description
### Types of Variables Analyzed
- **`int`**
- **`String`**
- **`byte`**
- **`double`**
- Other types defined in the source code

### Analysis Performed
1. **Uninitialized `int` Variables:**  
   Identified `int` variables that were declared without initialization.

2. **Initialized `int` Variables:**  
   Listed `int` variables that were already assigned an initial value.

3. **Analysis for Other Types:**  
   Applied the same analysis principles to other types such as `String`, `byte`, and `double`.

### Example Results
#### Uninitialized `int` Variables:
- `golpes`
- `tcpPort`
- `i`

#### Initialized `int` Variables:
- `puntos = 0`
- `golpes = 0`
- `tcpPort = 7899`

---

## 🛠️ Implementation

### Python Code:
```python
import re

# Open file and read its content
f = open("Ejemplo.txt").read()

# Regular expression to find uninitialized int variables
ExpReg11 = "int+\s\w+" + "\s="
Exp11 = re.findall(ExpReg11, f, flags=re.MULTILINE)

res11 = []
for x in range(len(Exp11)):
    Aux11 = re.sub("int", " ", Exp11[x])
    ExpReg12 = "\w+[^=]"
    Exp12 = re.findall(ExpReg12, Aux11, flags=re.MULTILINE)
    Aux12 = re.sub("\s", "", Exp12[0])
    res11.append(Aux12)

print("All uninitialized int instances:")
print(res11)
```

---

## 📊 Results

### String Variables
- **Uninitialized Instances:**  
  `idJuego`
  
- **Initialized Instances:**  
  `tcpIP = "localhost"`, `name = "Login"`

### Byte Variables
- **Uninitialized Instances:**  
  `maBaitMan`
  
- **Initialized Instances:**  
  `MaByte = 1`

---

## 📈 Recommendations
- Uninitialized variables can lead to runtime errors.
- Ensure all variables are initialized before use.
- Using regular expressions helps automate the detection of such issues in large codebases.
