# Polynomial-KMeans--Diabetes-Analysis

Лабораторная работа №4: Полиномиальная регрессия и кластеризация K-Means на основе встроенного датасета `load_diabetes` из `sklearn`.

## 📌 Цель работы
- Выполнить полный цикл первичной обработки данных (загрузка, визуализация, обработка пропусков, масштабирование).
- Построить модели полиномиальной регрессии разных степеней и проанализировать кривые аппроксимации.
- Реализовать кластеризацию K-Means, подобрать оптимальное число кластеров методом локтя.

## 🗂 Датасет
**Diabetes dataset** (sklearn.datasets.load_diabetes)
- 442 образца, 10 числовых признаков (возраст, пол, ИМТ, кровяное давление и 6 анализов крови).
- Целевая переменная: количественный прогресс диабета через год после исходного измерения.

## 🛠 Используемые библиотеки
- pandas, numpy – обработка данных
- matplotlib, seaborn – визуализация
- scikit-learn:
  - `train_test_split`, `PolynomialFeatures`, `LinearRegression`, `make_pipeline`
  - `KMeans`, `StandardScaler`, `PCA`
  - `mean_squared_error`, `r2_score`

## 📂 Структура репозитория
```
├── README.md
├── lab4_diabetes_analysis.ipynb # Основной Jupyter Notebook
├── requirements.txt # Зависимости
├── results/
│ ├── poly_reg_degree_plot.png # График MSE vs степень полинома
│ ├── elbow_method.png # Метод локтя для K-Means
│ └── clusters_pca.png # Визуализация кластеров (PCA)
└── src/
└── utils.py # Вспомогательные функции (опционально)
```


## 🚀 Запуск

1. **Клонировать репозиторий**
   ```bash
   git clone https://github.com/your-username/Polynomial-KMeans--Diabetes-Analysis.git
   cd Polynomial-KMeans--Diabetes-Analysis

   2. **Установить зависимости**
   ```bash
   pip install -r requirements.txt
   ```

3. **Открыть Jupyter Notebook**
   ```bash
   jupyter notebook lab4_diabetes_analysis.ipynb
   ```

## 📊 Основные этапы

### 1. Первичная обработка данных
- Загрузка датасета в `pandas.DataFrame`
- Проверка на пропуски (отсутствуют — добавлены искусственно для демонстрации обработки)
- Статистический анализ (`describe`, `info`)
- Визуализация распределений и корреляций (heatmap, pairplot)

### 2. Полиномиальная регрессия
- Сравнение степеней полинома: 1, 2, 3
- Метрика: MSE на train/test
- График зависимости ошибки от степени → определение переобучения

**Результат:** степень 2 даёт наилучшее обобщение (минимальный test MSE).

### 3. Кластеризация K-Means
- Масштабирование признаков (`StandardScaler`)
- Метод локтя для выбора k (инерция vs k)
- Визуализация через PCA (2 компоненты) с цветами кластеров

**Результат:** оптимальное k = 3 (согласуется со структурой данных).

## 📈 Примеры графиков

> *Ниже добавьте скриншоты из ноутбука*

| Полиномиальная регрессия | Метод локтя | Кластеры (PCA) |
|--------------------------|-------------|----------------|
| ![poly](results/poly_reg_degree_plot.png) | ![elbow](results/elbow_method.png) | ![cluster](results/clusters_pca.png) |

## 📝 Выводы
- Полиномиальная регрессия 2-й степени оптимальна для этого датасета: более высокая степень ведёт к переобучению.
- K-Means выделяет 3 кластера пациентов с различными метаболическими профилями.
- Предварительное масштабирование критически важно для K-Means.

## 🔗 Источники
- [scikit-learn Diabetes dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_diabetes.html)
- Примеры из лабораторных работ: [обработка данных](https://colab.research.google.com/drive/1OgH-OFOWOeXW24MYUrnBLorl_PqbanOf), [полиномиальная регрессия](https://colab.research.google.com/drive/1sA0axAMuSDaDEaZngfv16mpMrvcklMC5), [кластеризация](https://colab.research.google.com/drive/1H-f81Ih8m3h_fRlmyx2-mpZ4bZr6WKYI)

## 👨‍💻 Автор
[Ваше имя] – студент [группа, курс]  
GitHub: [your-username]
```

## 📦 Файл `requirements.txt`
```
numpy>=1.21.0
pandas>=1.3.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
jupyter>=1.0.0
```
