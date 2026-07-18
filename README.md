# Proyecto MIA – Estandarización de Títulos y Triage de Tickets de Mesa de Ayuda TI

## Descripción del proyecto

Este repositorio contiene el desarrollo de un prototipo de Inteligencia Artificial aplicado al proceso de gestión de tickets de una mesa de ayuda TI.

El proyecto busca evaluar técnicas de Procesamiento de Lenguaje Natural (PLN) y aprendizaje automático supervisado para mejorar la información textual de los tickets y apoyar la clasificación automática hacia el grupo resolutorio correspondiente.

El desarrollo se realiza de manera incremental mediante diferentes experimentos, permitiendo mantener trazabilidad sobre la evolución del prototipo y comparar el impacto de cada ajuste realizado.

## Experimentos desarrollados

- **Experimento 1 – Baseline:** clasificación de tickets mediante TF-IDF y Regresión Logística utilizando el título y la descripción.
- **Experimento 2 – Baseline balanceado:** evaluación del parámetro `class_weight='balanced'` para mejorar el tratamiento de clases con menor representación.
- **Experimento 3 – Títulos estandarizados:** incorporación de un módulo determinista de estandarización de títulos y evaluación de su impacto sobre la clasificación.

## Estructura del repositorio

- `data/`: dataset utilizado en los experimentos.
- `source/`: notebooks correspondientes a las diferentes etapas y experimentos del prototipo.
- `logs/`: registro de cambios y bitácora del proyecto.

## Ejecución

Los experimentos fueron desarrollados en Google Colab y pueden ejecutarse utilizando los notebooks disponibles en la carpeta `source/`.

Cada notebook documenta las etapas de carga y preparación de datos, procesamiento del texto, entrenamiento del modelo y evaluación de resultados.

## Dependencias y versiones

El prototipo fue desarrollado y ejecutado en Google Colab utilizando las siguientes versiones:

- Python 3.12.13
- pandas 2.2.2
- NumPy 2.0.2
- scikit-learn 1.6.1
- matplotlib 3.10.0
- seaborn 0.13.2

## Estado del proyecto

Proyecto en desarrollo como parte de un programa de Maestría en Inteligencia Artificial Aplicada.
