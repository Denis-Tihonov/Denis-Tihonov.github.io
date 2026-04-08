# Лабораторные работы по курсу "Математические методы машинного обучения"

---

## О курсе
Краткое описание курса: основные темы, цели, какие математические аспекты (оптимизация, теория вероятностей, линейная алгебра) будут затронуты в практических заданиях.

## Структура лабораторных работ
Каждая лабораторная работа находится в своей папке и содержит:
1. **Задание** (`README.md`) с теоретическими вопросами и практической частью.
2. **Решение** в виде Jupyter Notebook (`.ipynb`) и/или скриптов (`.py`/`.R`).
3. **Набор данных** (если требуется) в папке `data/`.
4. **Отчет** (если требуется) в папке `report/`.

## Список лабораторных работ

## Lab Series I – Time Series Forecasting & Nonparametric Methods
TODO
================================================================================

##  Lab Series II – Tensor Low-Rank Approximation

Lab Series II – Tensor Low-Rank Approximation
| Lab | Title / Topic | Description | Notes / Links |
|-----|--------------------------|----------------------------------|---------------|
| 201 | **Tensor Approximation via Low‑Rank Decompositions** | **Задача:** Аппроксимировать многомерные массивы данных (2D‑изображение, 3D‑видео, спектрограмму, 4D fMRI) с помощью трёх классических тензорных разложений: Tucker, CANDECOMP/PARAFAC (CP) и Tensor‑Train (TT).<br><br> **Ожидаемый результат:** Графики зависимости ошибки аппроксимации от ранга для каждого типа разложения, визуализация исходных и восстановленных данных при разных рангах. | **Датасеты:** [CIFAR-10/100](https://www.cs.toronto.edu/~kriz/cifar.html), [UCF101](https://www.crcv.ucf.edu/data/UCF101.php), [THINGS-fMRI](https://openneuro.org/datasets/ds004192), [COIL-20](https://www.cs.columbia.edu/CAVE/software/softlib/coil-20.php) |
| 202 | **Higher‑Order Principal Component Analysis (HOPCA)** | **Задача:** Выполнить снижение размерности тензорных данных (например, видео или fMRI) с одновременным уменьшением порядка тензора (количества измерений) с помощью тензорого метода главных компонент (MPCA / HOPCA).<br><br>**Ожидаемый результат:** Визуализация данных в низкоразмерном пространстве (2D/3D проекция) с сохранением основных особенностей данных, например, характерных периодов. Сравнение точности восстановаления при уменьшении размерности/ранга. | **Датасеты:** [CIFAR-10/100](https://www.cs.toronto.edu/~kriz/cifar.html), [UCF101](https://www.crcv.ucf.edu/data/UCF101.php), [THINGS-fMRI](https://openneuro.org/datasets/ds004192), [COIL-20](https://www.cs.columbia.edu/CAVE/software/softlib/coil-20.php) |
---

### Дополнительные источники датасетов (общие)

| Тип данных | Ресурс | Описание |
|------------|--------|----------|
| **Изображения** | CIFAR‑10/‑100 (`https://www.cs.toronto.edu/~kriz/cifar.html`) | 32×32 цветные изображения, 10/100 классов |
| **Изображения** | Yale Face Database B (`http://vision.ucsd.edu/~leekc/ExtYaleDatabase/ExtYaleB.html`) | Лица при разном освещении (16 128 изображений) |
| **Изображения** | COIL‑20 (`https://www.cs.columbia.edu/CAVE/software/softlib/coil-20.php`) | 20 объектов, 72 ракурса каждый |
| **Видео** | UCF101 (`https://www.crcv.ucf.edu/data/UCF101.php`) | 101 класс действий, ~13 000 видео |
| **Видео** | KTH Human Actions (`https://www.csc.kth.se/cvap/actions/`) | 6 типов действий, 25 человек, 4 сценария |
| **Видео** | Weizmann Action Dataset (`https://www.wisdom.weizmann.ac.il/~vision/SpaceTimeActions.html`) | 10 действий, 9 человек |
| **fMRI** | OpenNeuro (`https://openneuro.org/`) | Открытая база нейровизуализационных данных |
| **fMRI** | THINGS‑fMRI (`https://openneuro.org/datasets/ds004192`) | Мультимодальная коллекция fMRI, MEG и поведенческих данных |
| **Томография** | Helsinki Tomography Challenge 2022 (`https://zenodo.org/records/7418878`) | Синограммы для 2D‑реконструкции |
| **Томография** | SinoCT (Stanford AIMI) | Более 9 000 КТ‑сканов головы с синограммами |
| **Томография** | SparseBeads Dataset (`https://zenodo.org/records/1654917`) | Томографические данные с разреженностью |
| **Гирокинетика** | GYSELA‑X (`https://gyselax.github.io/`) | Симуляции плазменной турбулентности |
| **Гирокинетика** | GENE benchmark data (`https://doi.org/10.1063/1.4955189`) | Кросс‑верификация глобальных гирокинетических кодов |
| **IMU** | IF‑D Dataset (`https://zenodo.org/records/13885759`) | Многоканальные записи акселерометра, гироскопа, магнитометра |
| **IMU** | Multimodal gait dataset (`https://doi.org/10.1038/s41597-025-05121-4`) | Данные походки с акселерометрами и видео |
| **IMU** | Human Activity Recognition (`https://data.mendeley.com/datasets/3f8w6n9y7p`) | 6 активностей с акселерометра и гироскопа |
| **Айтрекинг** | Visual Experience Dataset (VEDB) (`https://visualexperiencedataset.org/`) | 240+ часов эгоцентрического видео с айтрекингом |
| **Айтрекинг** | IREye4Task (`https://ieee-dataport.org/documents/ireye4task`) | Видео глаз с разметкой зрачка и век |
| **Энергопотребление** | UCI Electricity Load Diagrams (`https://archive.ics.uci.edu/dataset/321/electricityloaddiagrams20112014`) | Почасовое потребление 370 клиентов |
| **Энергопотребление** | PJM Hourly Energy (`https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption`) | Почасовое потребление по регионам США |

Golden rules (Series II):
- Периоды, частоты, пространства и декартовы зависимости представлять как многомерную матрицу.
- Число измерений (ways) должно быть оптимальным.

================================================================================

Lab Series III – BCI‑ML Library (IMU Data: Accelerometer & Gyroscope)
TODO

================================================================================

Lab Series IV – Continuous‑Time Models (Neural ODEs / CDEs)


Основные источники кода и данных (общие для серий)

- HOTTBOX – Higher Order Tensors ToolBOX: https://github.com/hottbox/hottbox
- TensorLy – Tensor Learning in Python: https://github.com/tensorly/tensorly
- torchdiffeq – PyTorch ODE solvers: https://github.com/rtqichen/torchdiffeq
- Neural CDE – Patrick Kidger’s implementation: https://github.com/patrick-kidger/NeuralCDE
- Дифференциальные уравнения на Julia: DiffEqFlux.jl https://github.com/SciML/DiffEqFlux.jl
