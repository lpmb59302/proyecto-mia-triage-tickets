# Registro de cambios

Este documento registra los principales hitos y cambios realizados durante el desarrollo del prototipo del Proyecto MIA.

## Experimento 1 – Baseline

Se implementó el primer modelo de referencia para la clasificación automática de tickets hacia su grupo resolutorio.

Principales características:

- Construcción del conjunto de datos para Machine Learning.
- Uso del título y la descripción como entrada textual.
- Limpieza básica del texto.
- Vectorización mediante TF-IDF.
- Clasificación mediante Regresión Logística.
- Evaluación mediante Classification Report y matriz de confusión.

Este experimento estableció el punto de referencia para evaluar las modificaciones posteriores del prototipo.

## Experimento 2 – Baseline Balanceado

Se desarrolló una variante del modelo baseline incorporando el parámetro `class_weight='balanced'` en la Regresión Logística.

El objetivo fue evaluar si el balanceo de pesos permitía mejorar el reconocimiento de los grupos resolutorios con menor representación.

Los resultados mostraron una mejora en métricas macro, especialmente Recall Macro y F1 Macro, pero una reducción del desempeño global medido mediante Accuracy y métricas ponderadas.

## Experimento 3 – Estandarización de Títulos

Se incorporó un módulo determinista de estandarización de títulos antes del proceso de clasificación.

El desarrollo del módulo fue iterativo e incluyó:

- Análisis de títulos frecuentes y potencialmente genéricos.
- Revisión de los campos estructurados Tipo, Categoría y SLA.
- Evaluación de títulos automáticos generados por Service Desk.
- Exploración de reglas basadas en el contenido de los tickets.
- Definición de mapeos directos para casos seleccionados.
- Desarrollo y optimización de reglas para patrones recurrentes de laboratorios.
- Revisión manual de transformaciones para evitar pérdida de información.
- Restricción de las reglas a casos previamente identificados y validados.

La primera aplicación amplia del módulo alcanzó una cobertura aproximada del 14 %, pero se identificaron transformaciones que simplificaban excesivamente algunos títulos ya informativos. Como resultado, las reglas fueron ajustadas para aplicar una estrategia más conservadora.

La versión final modificó 2.118 de 16.116 títulos, alcanzando una cobertura del 13,14 %.

El modelo con títulos estandarizados obtuvo un desempeño global prácticamente equivalente al baseline, por lo que la estandarización determinista implementada no produjo una mejora global significativa en la clasificación.

## Próximos pasos

Como siguiente etapa se evaluará el uso de un modelo de lenguaje (LLM) para la generación o reescritura de títulos en casos que requieren una mayor interpretación semántica de la descripción del ticket.
