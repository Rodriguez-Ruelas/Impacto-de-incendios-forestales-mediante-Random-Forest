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

## REFERENCIAS
- CONAFOR. (2022). *Informe nacional de incendios forestales 2022*. Comisión Nacional Forestal. https://www.gob.mx/conafor

- PROFEPA. (s.f.). *Prevención y atención de incendios forestales*. Procuraduría Federal de Protección al Ambiente. https://www.gob.mx/profepa

- Rodríguez-Trejo, D. A., & Fulé, P. Z. (2003). Fire ecology of Mexican pines and a fire management proposal. *International Journal of Wildland Fire, 12*(1), 23–37. https://doi.org/10.1071/WF02040

- Velasco-Rosas, N., & Fulé, P. Z. (2020). Human and climate drivers of fire regimes in central Mexico. *Fire Ecology, 16*(1), 1–16. https://doi.org/10.1186/s42408-020-00077-5

- Jardel-Peláez, E. J., & Pérez-Salicrup, D. R. (2018). El régimen del fuego en los bosques templados de México: estado del conocimiento y retos para la gestión forestal. *Madera y Bosques, 24*(3), e2431796. https://doi.org/10.21829/myb.2018.2431796
