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

Lab Series II – Tensor Low-Rank Approximation (с датасетами)

| Lab | Title / Topic (варианты) | Description (улучшенный вариант) | Notes / Links |
|-----|--------------------------|----------------------------------|---------------|
| 201 |
**1. Tensor Approximation via Low‑Rank Decompositions**<br>
**2. Low‑Rank Tensor Approximations: Tucker, CP, TT** | **Задача:** Аппроксимировать многомерные массивы данных (2D‑изображение, 3D‑видео, спектрограмму, 4D fMRI) с помощью трёх классических тензорных разложений: Tucker, CANDECOMP/PARAFAC (CP) и Tensor‑Train (TT).<br>
**Ожидаемый результат:** Графики зависимости ошибки аппроксимации от ранга для каждого типа разложения, визуализация исходных и восстановленных данных при разных рангах.<br>**Датасеты:** CIFAR-10/100 (`https://www.cs.toronto.edu/~kriz/cifar.html`), Yale Face Database B (`http://vision.ucsd.edu/~leekc/ExtYaleDatabase/ExtYaleB.html`), UCF101 (`https://www.crcv.ucf.edu/data/UCF101.php`), THINGS-fMRI (`https://openneuro.org/datasets/ds004192`) | [Code], [Data sets] |
| 202 | **1. Multilinear PCA: Joint Order and Dimensionality Reduction**<br>**2. Higher‑Order Principal Component Analysis (HOPCA)** | **Задача:** Выполнить снижение размерности тензорных данных (например, видео или fMRI) с одновременным уменьшением порядка тензора (количества измерений) с помощью многолинейного метода главных компонент (MPCA / HOPCA).<br>**Ожидаемый результат:** Визуализация данных в низкоразмерном пространстве (2D/3D проекция) с сохранением основной структуры вариации. Сравнение качества редукции при уменьшении размерности и порядка.<br>**Датасеты:** Yale Face Database B, UCF101, COIL-20 (`https://www.cs.columbia.edu/CAVE/software/softlib/coil-20.php`), THINGS-fMRI | [Code], [Data sets] |
| 203 | **1. Computed Tomography Reconstruction from Sinograms Using Tensor Approximations**<br>**2. Sequential Low‑Rank Reconstruction of 3D Medical Images** | **Задача:** Восстановить трёхмерное изображение по данным компьютерной томографии (синограммам), используя последовательную низкоранговую аппроксимацию (аналог Lab 201). Исследовать, как ранг разложения влияет на качество реконструкции (визуально и метрически).<br>**Ожидаемый результат:** Серия изображений реконструированного объекта при рангах 1, 2, …, R. График зависимости PSNR / SSIM от ранга.<br>**Датасеты:** Helsinki Tomography Challenge 2022 (`https://zenodo.org/records/7418878`), SinoCT (Stanford AIMI), SparseBeads Dataset (`https://zenodo.org/records/1654917`) | [Code], [Data] |
| 204 | **1. Benchmarking Tensor Decomposition Algorithms: Accuracy, Stability, and Complexity**<br>**2. Comparative Analysis of Low‑Rank Tensor Approximations** | **Задача:** Провести формальное сравнение методов тензорных разложений (Tucker, CP, TT и др.) из библиотеки HOTTBOX на синтетических данных с контролируемой структурой (например, логотип). Оценить три группы критериев: точность восстановления, численную устойчивость к шуму и вычислительную сложность.<br>**Ожидаемый результат:** Сводная таблица метрик и графики «ранг–ошибка» для всех алгоритмов. Рекомендации по выбору метода в зависимости от задачи.<br>**Датасеты:** Синтетические данные (генерируются кодом), CIFAR-10/100 | [Code – Hottbox] |
| 205 | **1. Spatiotemporal Forecasting with Higher‑Order Singular Spectrum Analysis (HOSVD)**<br>**2. Forecasting Video Sequences via Tensor SSA** | **Задача:** Рассмотреть видео (например, анимацию шагающего персонажа) как пространственно‑временной ряд. Построить фазовую траекторию в тензорном виде и выполнить прогноз нескольких следующих кадров с помощью HOSVD, адаптировав классический метод «Гусеница» (SSA) для многомерного случая.<br>**Ожидаемый результат:** Визуализация прогнозируемых кадров в сравнении с реальными. Количественная оценка точности прогноза (например, RMSE по пикселям).<br>**Датасеты:** UCF101, KTH Human Action Dataset (`https://www.csc.kth.se/cvap/actions/`), Weizmann Action Dataset (`https://www.wisdom.weizmann.ac.il/~vision/SpaceTimeActions.html`) | [Code], [Data] |
| 206 | **1. Detecting Causal Links in Spatiotemporal Data Using Convergent Cross Mapping (CCM) with Tensors**<br>**2. Higher‑Order CCM for Video Causality** | **Задача:** Имея два видео с движущимися объектами, определить наличие причинно‑следственной связи между их динамикой. Использовать метод Convergent Cross Mapping, обобщённый для тензорных фазовых траекторий (построенных с помощью HOSVD), чтобы проверить, является ли одна система движущей по отношению к другой.<br>**Ожидаемый результат:** График сходимости CCM (зависимость skill предсказания от длины ряда) для обоих направлений, вывод о направлении влияния.<br>**Датасеты:** Синтетические видео со связанной динамикой (генерируются кодом), мультфильмы с шагающим героем | [Code], [Data] |
| 207 | **1. Tensor Index Reduction in Synthetic High‑Dimensional Video**<br>**2. Dimensionality and Order Reduction for 4D+ Visual Data** | **Задача:** Сгенерировать синтетическое видео размерности 4D или выше (например, куб, меняющий цвет во времени). Используя тензорные разложения высокого порядка (HOSVD), сократить один из индексов (например, временной или цветовой), сохранив при этом основную информацию, и визуализировать результат в виде трёхмерных проекций.<br>**Ожидаемый результат:** Сравнение исходной высокоразмерной анимации с редуцированной версией в 3D‑проекциях. График доли объяснённой дисперсии при редукции индекса.<br>**Датасеты:** Синтетические 4D+ видео (генерируются кодом, например, вращающийся гиперкуб или динамические текстуры) | [Code], [Data] |
| 208 | **1. Higher‑Order Spectral Analysis vs Multilinear Fourier Transform on Gyrokinetic Simulation Data**<br>**2. Index Reduction in 6D Plasma Physics Tensors** | **Задача:** На реальных данных гирокинетического моделирования плазмы (тензор 6‑го порядка) сравнить два подхода к извлечению частотной информации: прямое многомерное преобразование Фурье и тензорный спектральный анализ (через разложение по собственным тензорам). Цель – сократить число индексов в данных, выделив наиболее энергонесущие моды.<br>**Ожидаемый результат:** Спектральные портреты (визуализация главных компонент) и сравнение эффективности снижения размерности.<br>**Датасеты:** GYSELA simulation data (`https://gyselax.github.io/`), GENE code benchmark data (`https://doi.org/10.1063/1.4955189`) | [Code], [Data] |
| 209 | **1. Eye‑Movement Prediction from Video Using Higher‑Order PLS and Canonical Correlation**<br>**2. Multimodal Fusion with HOPLS and CCA for Gaze Forecasting** | **Задача:** Объединить два источника данных – синтетическое видео и соответствующие ему записи движения глаз (айтрекинг). Построить модель прогноза будущих координат взгляда на основе тензорного представления видеоряда, используя комбинацию Higher‑Order Partial Least Squares (HOPLS) и канонического корреляционного анализа (CCA).<br>**Ожидаемый результат:** Визуализация предсказанной траектории взгляда на кадрах видео. Количественная оценка ошибки предсказания по сравнению с линейными аналогами.<br>**Датасеты:** Visual Experience Dataset (VEDB) (`https://visualexperiencedataset.org/`), IREye4Task (`https://ieee-dataport.org/documents/ireye4task`), синтетические видео с айтрекингом | [Code – HOPLS], [Data] |
| 210 | **1. Cross‑Modal Prediction: Gyroscope Data from Accelerometer Using HOPLS**<br>**2. Multiway PLS for Inertial Sensor Fusion** | **Задача:** Используя данные с акселерометра (x, y, z) и гироскопа (x, y, z) в виде многомерного временного ряда (тензор с измерениями: время × оси × тип сенсора), применить Higher‑Order PLS для предсказания показаний гироскопа по показаниям акселерометра при различных условиях движения.<br>**Ожидаемый результат:** Графики прогнозируемых и истинных угловых скоростей. Анализ важности латентных факторов, связывающих два сенсора.<br>**Датасеты:** IF‑D Inertial Foundation Dataset (`https://zenodo.org/records/13885759`), Multimodal gait dataset (`https://doi.org/10.1038/s41597-025-05121-4`), IMU Human Activity Recognition Dataset (`https://data.mendeley.com/datasets/3f8w6n9y7p`), iOS walking/running dataset (OpenML) | [Code], [Data] |
| 211 | **1. Tensor Singular Spectrum Analysis (SSA) for Multi‑Channel Periodic Signals**<br>**2. Multivariate SSA with Energy Consumption Data** | **Задача:** Реализовать тензорный вариант метода «Гусеница» (Tensor SSA, также известный как HOSSA) для анализа и прогнозирования многомерных временных рядов, содержащих две или три периодические компоненты. В качестве данных использовать ряды потребления энергии.<br>**Ожидаемый результат:** Декомпозиция исходного ряда на трендовую, периодические и шумовую составляющие. Прогноз на тестовый период с оценкой точности (MAPE, RMSE).<br>**Датасеты:** UCI Electricity Load Diagrams (`https://archive.ics.uci.edu/dataset/321/electricityloaddiagrams20112014`), PJM Hourly Energy Consumption (`https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption`), данные энергопотребления (доступны в репозитории курса) | [Code], [Data – Energy] |

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
