# Tesis-UNIR
Documentos anexo y complementarias del TFM 

# Repositorio de código y resultados — TFM: Predicción de efectores en *Pseudocercospora fijiensis*

Este repositorio contiene el notebook, los datos de entrada y los resultados generados para el Trabajo de Fin de Máster sobre predicción de proteínas efectoras mediante aprendizaje automático (Random Forest, SVM, Regresión Logística).

## Contenido

| Archivo / tipo | Descripción |
|---|---|
| `modelo_final.ipynb` | Notebook completo: carga de datos, extracción de features, entrenamiento, SHAP y validación externa |
| `*.fasta`, `*.fa` | Secuencias de entrenamiento (efectores positivos y negativos) |
| `Table S1... .xlsx` | Efectoma de *P. fijiensis* (Carreón et al., 2024) usado como validación externa |
| `Signal_result_*.txt`, `SignalP_Carreon.txt` | Salidas de SignalP (predicción de péptido señal) |
| `TMHMM_result_*`, `TMHMM_Carreon.html` | Salidas de TMHMM (predicción de dominios transmembrana) |
| `*_clustered.clstr` | Salidas de CD-HIT (control de redundancia homológica) |
| `*.joblib` | Modelos entrenados (RF, SVM, Regresión Logística) y lista de features |
| `*.csv` | Tablas de resultados (comparación de modelos, importancia de variables, predicciones externas, bootstrap, motifs) |
| `*.png` | Figuras (ROC, SHAP, PCA, matriz de confusión, distribuciones bootstrap) |

## Fuente de los datos

- **Secuencias de entrenamiento**: EffectorP 2.0 (Sperschneider et al., 2018, *Molecular Plant Pathology*, https://doi.org/10.1111/mpp.12682) y PHI-base (http://www.phi-base.org).
- **Validación externa**: Carreón-Anguiano et al. (2024), efectoma *in silico* de *Pseudocercospora fijiensis*, material suplementario de acceso libre. Cita el DOI del artículo original al usar este archivo.

Estos datos no son propios; se incluyen para reproducibilidad y se atribuyen a sus autores originales.

## Requisitos

Python 3.10+, con: `biopython`, `beautifulsoup4`, `scikit-learn`, `pandas`, `numpy`, `matplotlib`, `seaborn`, `shap`, `joblib`, `openpyxl`.

## Nota sobre reproducibilidad

El notebook incluye dos pausas manuales para ejecutar CD-HIT, SignalP y TMHMM fuera de Python; sus salidas ya están incluidas en este repositorio para poder reproducir el análisis sin volver a correr esas herramientas externas.
