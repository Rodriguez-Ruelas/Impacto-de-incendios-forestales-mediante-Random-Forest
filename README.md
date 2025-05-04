# IMPACTO DE INCENDIOS FORESTALES MEDIANTE RANDOM FOREST

## RESUMEN
<p align="justify">
Los incendios forestales representan una amenaza constante para los ecosistemas y poblaciones humanas. Comprender los factores que determinan su impacto es clave para diseñar estrategias efectivas de prevención y atención. En este estudio se utilizó un modelo de aprendizaje automático para identificar las variables que mejor predicen la severidad de los incendios forestales en México. El objetivo fue determinar las variables ambientales, espaciales y de gestión que más influyen en la clasificación del impacto de incendios forestales utilizando un modelo Random Forest. Se analizó un conjunto de datos proveniente de reportes nacionales de incendios forestales, conteniendo información de ubicación, tipo de vegetación, superficie afectada, causa probable, esfuerzo humano (días/persona), y clasificación del impacto (variable objetivo). Se eliminaron registros incompletos, se codificaron variables categóricas mediante One-Hot Encoding, y se dividió el conjunto en entrenamiento (80%) y prueba (20%). Se ajustó un clasificador Random Forest con 100 árboles, y se evaluó mediante matriz de confusión y análisis de importancia de variables. El modelo obtuvo buen desempeño general, con alta precisión en la predicción de la clase más frecuente. Sin embargo, mostró dificultades al identificar correctamente las clases minoritarias, indicando un posible desbalance. Las variables más importantes para la predicción del impacto fueron: superficie afectada, latitud, esfuerzo humano, longitud y semana del año. También influyeron ciertas categorías de vegetación y entidades federativas específicas. La superficie quemada, la ubicación geográfica y el esfuerzo de atención son determinantes clave en la clasificación del impacto de los incendios forestales. El modelo Random Forest demostró ser útil para este análisis exploratorio, aunque futuras versiones deberían considerar técnicas de balanceo de clases para mejorar la precisión en eventos menos frecuentes.
</p>

## INTRODUCCIÓN
<p align="justify">
Los incendios forestales constituyen una de las principales amenazas para los ecosistemas en México, afectando anualmente un promedio de más de 400,000 hectáreas de vegetación natural (CONAFOR, 2022). Estos eventos no solo deterioran la biodiversidad y los servicios ecosistémicos, sino que también generan impactos económicos y sociales significativos. La Procuraduría Federal de Protección al Ambiente (PROFEPA, s.f.) ha destacado la importancia de la denuncia ciudadana y la implementación de medidas preventivas para mitigar estos siniestros.

Diversos estudios han señalado que la mayoría de los incendios forestales en el país tienen origen antropogénico, relacionados con actividades como quemas agrícolas no controladas, cambio de uso de suelo y prácticas forestales inadecuadas (Rodríguez-Trejo & Fulé, 2003; Jardel-Peláez & Pérez-Salicrup, 2018). Además, factores climáticos como sequías prolongadas y altas temperaturas exacerbadas por el cambio climático han incrementado la frecuencia e intensidad de estos eventos (Velasco-Rosas & Fulé, 2020).

En este contexto, el presente proyecto emplea técnicas de aprendizaje automático, específicamente el modelo Random Forest, para analizar y predecir el impacto de los incendios forestales en México. Al identificar las variables más influyentes en la severidad de estos siniestros, se busca proporcionar herramientas que apoyen la toma de decisiones en la gestión y prevención de incendios, contribuyendo así a la conservación de los recursos forestales y la seguridad de las comunidades.
</p>

## OBJETIVOS
<p align="justify">
El objetivo general de este proyecto es analizar y predecir el impacto de los incendios forestales en México mediante un modelo de clasificación Random Forest, utilizando variables ambientales, geográficas y de gestión.

### Objetivos específicos:
- Preparar y limpiar una base de datos nacional de incendios forestales para su análisis mediante aprendizaje automático.
- Identificar las variables más relevantes en la clasificación del impacto de los incendios, mediante el análisis de importancia del modelo.
- Evaluar el desempeño del modelo utilizando métricas de clasificación como la matriz de confusión y el reporte de precisión.
- Proponer una base técnica que permita desarrollar herramientas predictivas para la toma de decisiones en la gestión forestal y la prevención de riesgos ambientales.
</p>

## MATERIALES Y MÉTODOS
<p align="justify">
Se utilizó una base de datos oficial de incendios forestales en México, obtenida de reportes públicos nacionales. Esta incluía variables como ubicación geográfica (latitud y longitud), entidad federativa, tipo de vegetación, causa probable, superficie afectada, esfuerzo de atención (días/persona), tipo de atención recibida y clasificación del impacto.

Los datos fueron procesados utilizando el lenguaje de programación Python. Se realizaron las siguientes etapas:

1. **Limpieza de datos**: Se eliminaron registros con valores faltantes en variables críticas y se imputaron categorías vacías con la etiqueta “No especificado”.
2. **Codificación**: Las variables categóricas fueron transformadas utilizando codificación One-Hot para permitir su uso en modelos de aprendizaje automático.
3. **Separación de conjuntos**: El conjunto de datos fue dividido en subconjuntos de entrenamiento (80%) y prueba (20%) mediante muestreo aleatorio estratificado.
4. **Entrenamiento del modelo**: Se ajustó un clasificador Random Forest con 100 árboles (`n_estimators=100`) usando la implementación de `scikit-learn`. 
5. **Evaluación del modelo**: Se utilizó la matriz de confusión, el reporte de clasificación (precisión, recall, f1-score), y el análisis de importancia de variables para interpretar los resultados del modelo.

Todo el procesamiento, visualización y entrenamiento se realizó en un entorno de trabajo reproducible basado en Jupyter Notebook, utilizando las librerías `pandas`, `numpy`, `matplotlib`, `seaborn` y `scikit-learn`.
</p>

## RESULTADOS
<p align="justify">
El modelo Random Forest entrenado logró una precisión general elevada, especialmente en la predicción de la clase más frecuente correspondiente al nivel de impacto “moderado”. La matriz de confusión reveló que, si bien el modelo clasifica correctamente la mayoría de los casos de impacto moderado, presenta dificultades al distinguir entre las clases minoritarias, como “mínimo” y “severo”. Este comportamiento sugiere un desbalance en las clases de la variable objetivo, lo que influye negativamente en la capacidad del modelo para aprender patrones representativos de las categorías menos frecuentes.

<div align="center">
<img src="https://github.com/Rodriguez-Ruelas/Impacto-de-incendios-forestales-mediante-Random-Forest/blob/main/Images/Matriz%20de%20confusion.png?raw=true" alt="Matriz de confusión" width="600"/>
<p><strong>Figura 1.</strong> Matriz de confusión del modelo Random Forest aplicada a la clasificación del impacto de incendios forestales.</p>
</div>

El análisis de importancia de variables arrojó que la **superficie afectada** fue el principal predictor del nivel de impacto del incendio. Le siguieron en relevancia la **latitud**, el número de **días/persona** dedicados al control del incendio, la **longitud** y la **semana del año** en que ocurrió el evento. También se observaron contribuciones importantes de ciertas categorías de vegetación y de entidades federativas específicas, lo que indica que el contexto ecológico y geográfico tiene un papel clave en la severidad de los incendios.

<div align="center">
<img src="https://github.com/Rodriguez-Ruelas/Impacto-de-incendios-forestales-mediante-Random-Forest/blob/main/Images/top%2020%20variables%20importantes.png?raw=true" alt="Importancia de variables" width="700"/>
<p><strong>Figura 2.</strong> Principales 20 variables predictoras del impacto de incendios forestales según el modelo Random Forest.</p>
</div>


Los resultados obtenidos validan el enfoque utilizado y permiten identificar los factores más relevantes en la dinámica de los incendios forestales en México. No obstante, las dificultades en la clasificación de clases poco representadas sugieren la necesidad de explorar estrategias adicionales, como técnicas de balanceo de clases o el ajuste de hiperparámetros del modelo.
</p>

## CONCLUSIÓN
<p align="justify">
El uso del modelo Random Forest permitió identificar y jerarquizar las variables más relevantes en la clasificación del impacto de incendios forestales en México. Factores como la superficie afectada, la localización geográfica, el esfuerzo humano involucrado y la temporalidad del evento se posicionaron como predictores clave de la severidad de los incendios.

El modelo mostró un desempeño adecuado en términos generales, especialmente en la clase más representada. Sin embargo, su dificultad para clasificar correctamente los eventos menos frecuentes resalta la necesidad de abordar el desbalance de clases presente en los datos. Este hallazgo representa una oportunidad para aplicar técnicas complementarias que mejoren la equidad del modelo en la predicción de todas las categorías.

En conjunto, este trabajo demuestra el potencial del aprendizaje automático para apoyar el análisis exploratorio y la toma de decisiones en la gestión de incendios forestales. La integración de datos espaciales, ecológicos y operativos en modelos predictivos constituye una herramienta poderosa para anticipar el riesgo y planificar estrategias de respuesta más eficaces y focalizadas.
</p>


## REFERENCIAS
- CONAFOR. (2022). *Informe nacional de incendios forestales 2022*. Comisión Nacional Forestal. https://www.gob.mx/conafor

- PROFEPA. (s.f.). *Prevención y atención de incendios forestales*. Procuraduría Federal de Protección al Ambiente. https://www.gob.mx/profepa

- Rodríguez-Trejo, D. A., & Fulé, P. Z. (2003). Fire ecology of Mexican pines and a fire management proposal. *International Journal of Wildland Fire, 12*(1), 23–37. https://doi.org/10.1071/WF02040

- Velasco-Rosas, N., & Fulé, P. Z. (2020). Human and climate drivers of fire regimes in central Mexico. *Fire Ecology, 16*(1), 1–16. https://doi.org/10.1186/s42408-020-00077-5

- Jardel-Peláez, E. J., & Pérez-Salicrup, D. R. (2018). El régimen del fuego en los bosques templados de México: estado del conocimiento y retos para la gestión forestal. *Madera y Bosques, 24*(3), e2431796. https://doi.org/10.21829/myb.2018.2431796
