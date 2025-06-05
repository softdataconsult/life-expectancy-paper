# Impact of Economic Factors on Life Expectancy: A Machine Learning Approach

Welcome to the companion repository for the paper **“Impact of Economic Factors on Life Expectancy: A Machine Learning Approach.”**  
This README provides an overview of the study, instructions for reproducing our results, and guidance on how to cite or extend the work.

---

## 1. Project Overview

We examine how key economic indicators influence life expectancy by training and comparing three predictive models:

| Model | Abbreviation |
| :---- | :----------- |
| Linear Regression | **LM** |
| Artificial Neural Network (5 hidden layers) | **ANN-5** |
| Artificial Neural Network (7 hidden layers) | **ANN-7** |
| Support Vector Regression | **SVR** |

The research shows that both ANN configurations yield the lowest error rates and the highest predictive accuracy, highlighting the strength of neural networks for this task.

---

## 2. Repository Structure




Welcome to the companion repository for **“Impact of Economic Factors on Life Expectancy: A Machine-Learning Approach.”**  
This README explains the project, the file layout, and the steps needed to reproduce every table, figure, and model described in the paper.

---

## 1. Quick Start

```bash
# clone the repo
git clone https://github.com/softdataconsult/life-expectancy-paper
cd life-expectancy-paper

# open the RStudio project
open life-expectancy-paper.Rproj
````

Once the project is open in RStudio:

1. Install the required R packages (see Section 5).
2. Knit **`life-expectancy-ml.qmd`**.

   * This single Quarto document cleans the data, trains the models, and produces the final report.
3. The rendered HTML or PDF appears in the same directory.

---

## 2. Repository Structure

| Path / File                                   | Description                                                                 |
| --------------------------------------------- | --------------------------------------------------------------------------- |
| `.git/`                                       | Version-control history.                                                    |
| `.gitignore`                                  | Patterns for files you do not want tracked.                                 |
| `.Rproj.user/`, `life-expectancy-paper.Rproj` | RStudio project metadata.                                                   |
| `data_for_analysis.csv`                       | Original dataset of economic indicators and life-expectancy values.         |
| `data_for_analysis_adjusted.csv`              | Cleaned dataset used in the analysis.                                       |
| `life-expectancy-ml.qmd`                      | Reproducible Quarto file that performs EDA, model training, and evaluation. |
| `ANN-model.pdf`                               | Supplementary PDF detailing the neural-network architecture.                |
| `Ajao-Alaba ML models-edited.docx`            | Manuscript draft with additional commentary.                                |
| `README.md`                                   | This file.                                                                  |

---

## 3. Study Overview

The study evaluates three modelling techniques:

| Model                     | Abbreviation      | Notes                                                                           |
| ------------------------- | ----------------- | ------------------------------------------------------------------------------- |
| Linear regression         | **LM**            | Ordinary least squares.                                                         |
| Support-vector regression | **SVR**           | Radial basis kernel, hyper-parameters selected by grid search.                  |
| Artificial neural network | **ANN-5 / ANN-7** | Multilayer perceptron with 5 or 7 hidden layers, trained with back-propagation. |

Performance metrics include Mean Error (ME), Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), Normalized RMSE (NRMSE %) and Percent Bias (PBIAS %).
Both ANN configurations show the lowest error across every metric, confirming the suitability of neural networks for capturing the complex links between macro-economic variables and life expectancy.

---

## 4. Data

* **Source:** Public macro-economic and health databases (World Bank, WHO).
* **Period:** 1990 – 2022.
* **Predictors:** GDP per capita, inflation, unemployment, health spending, education index and other indicators.
* **Target:** Life expectancy at birth (years).

The original CSV is kept intact. All cleaning and feature engineering steps are scripted inside the Quarto document, guaranteeing full reproducibility.

---

## 5. Software Requirements

| Software                                | Minimum version | Install command                                          |
| --------------------------------------- | --------------- | -------------------------------------------------------- |
| **R**                                   | 4.3             | [https://cran.r-project.org](https://cran.r-project.org) |
| **Quarto**                              | 1.4             | [https://quarto.org](https://quarto.org)                 |
| **RStudio**                             | 2023.12         | [https://posit.co/downloads](https://posit.co/downloads) |


### R packages

```r
install.packages(c(
  "tidyverse",    # data manipulation and plotting
  "tidymodels",   # modelling framework
  "nnet",         # simple ANN
  "keras",        # deep-learning backend (optional but recommended)
  "e1071",        # SVR
  "gt", "gtExtras" # publication-ready tables
))
```


---

## 6. Reproducing the Results

1. **Render the Quarto file**

   ```r
   quarto::quarto_render("life-expectancy-ml.qmd")
   ```

   The command produces `life-expectancy-ml.html` (and PDF if LaTeX is installed).

2. **Inspect the output**

   * Interactive plots summarise exploratory analysis.
   * Metric tables benchmark LM, SVR and both ANN variants.
   * The appendix lists hyper-parameters and cross-validation folds.

3. **Modify or extend**

   * Tweak the neural-network architecture in the “Model Specification” chunk.
   * Replace or add predictors by editing the `data_prep` chunk.

---

## 7. How to Cite

<!--
```
Ogundepo E O, Ajao-Alaba A (2025).
Impact of Economic Factors on Life Expectancy: A Machine-Learning Approach.
Preprint available at https://doi.org/10.12345/zenodo.000000.
```
-->
---

## 8. License

The code is released under the MIT License.
The datasets are redistributed under the terms of their original sources.
See `LICENSE` for full details.

---

## 9. Contact

**Lead author:** 1Isaac Oluwaseyi Ajao
**Affiliation:** Department of Statistics, Federal Polytechnic, Ado-Ekiti, Nigeria
**Email:** [ajao_io@fedpolyado.edu.ng](mailto:ajao_io@fedpolyado.edu.ng)

Issues and pull requests are welcome—feel free to contribute!


