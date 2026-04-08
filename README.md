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

| Lab | Title / Topic | Description | Notes / Links |
|-----|--------------------------|----------------------------------|---------------|
| 201 | **Tensor Approximation via Low‑Rank Decompositions** | **Задача:** Аппроксимировать многомерные массивы данных (2D‑изображение, 3D‑видео, спектрограмму, 4D fMRI) с помощью трёх классических тензорных разложений: Tucker, CANDECOMP/PARAFAC (CP) и Tensor‑Train (TT).<br><br> **Ожидаемый результат:** Графики зависимости ошибки аппроксимации от ранга для каждого типа разложения, визуализация исходных и восстановленных данных при разных рангах. | **Датасеты:** [CIFAR-10/100](https://www.cs.toronto.edu/~kriz/cifar.html), [UCF101](https://www.crcv.ucf.edu/data/UCF101.php), [THINGS-fMRI](https://openneuro.org/datasets/ds004192), [COIL-20](https://www.cs.columbia.edu/CAVE/software/softlib/coil-20.php) |
| 202 | **Higher‑Order Principal Component Analysis (HOPCA)** | **Задача:** Выполнить снижение размерности тензорных данных (например, видео или fMRI) с одновременным уменьшением порядка тензора (количества измерений) с помощью тензорого метода главных компонент (MPCA / HOPCA).<br><br>**Ожидаемый результат:** Визуализация данных в низкоразмерном пространстве (2D/3D проекция) с сохранением основных особенностей данных, например, характерных периодов. Сравнение точности восстановаления при уменьшении размерности/ранга. | **Датасеты:** [CIFAR-10/100](https://www.cs.toronto.edu/~kriz/cifar.html), [UCF101](https://www.crcv.ucf.edu/data/UCF101.php), [THINGS-fMRI](https://openneuro.org/datasets/ds004192), [COIL-20](https://www.cs.columbia.edu/CAVE/software/softlib/coil-20.php) |
| 203 | **Computed Tomography Reconstruction from Sinograms Using Tensor Approximations** | **Задача:** Восстановить трёхмерное изображение по данным компьютерной томографии (синограммам), используя последовательную низкоранговую аппроксимацию. Исследовать, как ранг разложения влияет на качество реконструкции (визуально и метрически).<br><br>**Ожидаемый результат:** Серия изображений реконструированного объекта при рангах 1, 2, …, R. График зависимости PSNR / SSIM от ранга. | **Датасеты:** [Helsinki Tomography Challenge 2022](https://zenodo.org/records/7418878), [SparseBeads Dataset](https://zenodo.org/records/1654917), [SinoCT (Stanford AIMI)](https://aimi.stanford.edu/sinoct) |
| 204 | **Benchmarking Tensor Decomposition Algorithms: Accuracy, Stability, and Complexity** | **Задача:** Провести формальное сравнение методов тензорных разложений (Tucker, CP, TT и др.) из библиотеки HOTTBOX на синтетических данных. Оценить три группы критериев: точность восстановления, устойчивость к шуму и вычислительную сложность.<br><br>**Ожидаемый результат:** Сводная таблица метрик и графики «ранг–ошибка» для всех алгоритмов. Рекомендации по выбору метода в зависимости от задачи. | **Датасеты:** Синтетические данные (генерируются кодом), [CIFAR-10/100](https://www.cs.toronto.edu/~kriz/cifar.html) |
| 205 | **Spatiotemporal Forecasting with Higher‑Order Singular Spectrum Analysis (HOSVD)** | **Задача:** Рассмотреть видео (например, анимацию шагающего персонажа) как пространственно‑временной ряд. Построить фазовую траекторию в тензорном виде и выполнить прогноз нескольких следующих кадров с помощью HOSVD, адаптировав классический метод «Гусеница» (SSA) для многомерного случая.<br><br>**Ожидаемый результат:** Визуализация прогнозируемых кадров в сравнении с реальными. Количественная оценка точности прогноза (например, RMSE по пикселям). | **Датасеты:** [UCF101](https://www.crcv.ucf.edu/data/UCF101.php), [KTH Human Action Dataset](https://www.csc.kth.se/cvap/actions/), [Weizmann Action Dataset](https://www.wisdom.weizmann.ac.il/~vision/SpaceTimeActions.html) |
| 206 | **Detecting Causal Links in Spatiotemporal Data Using Convergent Cross Mapping (CCM) with Tensors** | **Задача:** Имея два видео с движущимися объектами, определить наличие причинно‑следственной связи между их динамикой. Использовать метод Convergent Cross Mapping, обобщённый для тензорных фазовых траекторий (построенных с помощью HOSVD), чтобы проверить, является ли одна система движущей по отношению к другой.<br><br>**Ожидаемый результат:** График сходимости CCM (зависимость skill предсказания от длины ряда) для обоих направлений, вывод о направлении влияния. | **Датасеты:** Синтетические видео со связанной динамикой (генерируются кодом), мультфильмы с шагающим героем |
| 207 | **Tensor Index Reduction in Synthetic High‑Dimensional Video** | **Задача:** Сгенерировать синтетическое видео размерности 4D или выше (например, куб, меняющий цвет во времени). Используя тензорные разложения высокого порядка (HOSVD), сократить один из индексов (например, временной или цветовой), сохранив при этом основную информацию, и визуализировать результат в виде трёхмерных проекций.<br><br>**Ожидаемый результат:** Сравнение исходной высокоразмерной анимации с редуцированной версией в 3D‑проекциях. График доли объяснённой дисперсии при редукции индекса. | **Датасеты:** Синтетические 4D+ видео (генерируются кодом) |
| 208 | **Higher‑Order Spectral Analysis vs Multilinear Fourier Transform on Gyrokinetic Simulation Data** | **Задача:** На реальных данных гирокинетического моделирования плазмы (тензор 6‑го порядка) сравнить два подхода к извлечению частотной информации: прямое многомерное преобразование Фурье и тензорный спектральный анализ (через разложение по собственным тензорам). Цель – сократить число индексов в данных, выделив наиболее энергонесущие моды.<br><br>**Ожидаемый результат:** Спектральные портреты (визуализация главных компонент) и сравнение эффективности снижения размерности. | **Датасеты:** [GYSELA simulation data](https://gyselax.github.io/), [GENE benchmark data](https://doi.org/10.1063/1.4955189) |
| 209 | **Eye‑Movement Prediction from Video Using Higher‑Order PLS and Canonical Correlation** | **Задача:** Объединить два источника данных – синтетическое видео и соответствующие ему записи движения глаз (айтрекинг). Построить модель прогноза будущих координат взгляда на основе тензорного представления видеоряда, используя комбинацию Higher‑Order Partial Least Squares (HOPLS) и канонического корреляционного анализа (CCA).<br><br>**Ожидаемый результат:** Визуализация предсказанной траектории взгляда на кадрах видео. Количественная оценка ошибки предсказания по сравнению с линейными аналогами. | **Датасеты:** [Visual Experience Dataset (VEDB)](https://visualexperiencedataset.org/), [IREye4Task](https://ieee-dataport.org/documents/ireye4task), синтетические видео с айтрекингом |
| 210 | **Cross‑Modal Prediction: Gyroscope Data from Accelerometer Using HOPLS** | **Задача:** Используя данные с акселерометра (x, y, z) и гироскопа (x, y, z) в виде многомерного временного ряда (тензор с измерениями: время × оси × тип сенсора), применить Higher‑Order PLS для предсказания показаний гироскопа по показаниям акселерометра при различных условиях движения.<br><br>**Ожидаемый результат:** Графики прогнозируемых и истинных угловых скоростей. Анализ важности латентных факторов, связывающих два сенсора. | **Датасеты:** [IF‑D Inertial Foundation Dataset](https://zenodo.org/records/13885759), [Multimodal gait dataset](https://doi.org/10.1038/s41597-025-05121-4), [IMU Human Activity Recognition Dataset](https://data.mendeley.com/datasets/3f8w6n9y7p) |
| 211 | **Tensor Singular Spectrum Analysis for Multi‑Channel Periodic Signals** | **Задача:** Реализовать тензорный вариант метода «Гусеница» (Tensor SSA / HOSSA) для анализа и прогнозирования многомерных временных рядов, содержащих две или три периодические компоненты. В качестве данных использовать ряды потребления энергии.<br><br>**Ожидаемый результат:** Декомпозиция исходного ряда на трендовую, периодические и шумовую составляющие. Прогноз на тестовый период с оценкой точности (MAPE, RMSE). | **Датасеты:** [UCI Electricity Load Diagrams](https://archive.ics.uci.edu/dataset/321/electricityloaddiagrams20112014), [PJM Hourly Energy Consumption](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption) |

### Дополнительные источники датасетов

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

================================================================================

## Lab Series III – BCI‑ML Library (IMU Data: Accelerometer & Gyroscope)
TODO

================================================================================

## Lab Series IV – Continuous‑Time Models (Neural ODEs / CDEs)


Основные источники кода и данных (общие для серий)

- HOTTBOX – Higher Order Tensors ToolBOX: https://github.com/hottbox/hottbox
- TensorLy – Tensor Learning in Python: https://github.com/tensorly/tensorly
- torchdiffeq – PyTorch ODE solvers: https://github.com/rtqichen/torchdiffeq
- Neural CDE – Patrick Kidger’s implementation: https://github.com/patrick-kidger/NeuralCDE
- Дифференциальные уравнения на Julia: DiffEqFlux.jl https://github.com/SciML/DiffEqFlux.jl
