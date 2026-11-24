# Proyecto 5 - Temperatura del modulo solar (Plantas 1 y 2)

**Analitica de Datos I - Universidad Icesi - 2026-2 - Grupo 7**  
Juan David Maldonado Cordoba - Nicolas Diaz Higuera - Luis Miguel Zambrano Sapuyes

Proyecto de regresion orientado a estimar la **temperatura del modulo fotovoltaico** a partir de temperatura ambiente, irradiacion, hora e informacion temporal reciente. El modelo se entrena con la Planta 1, se evalua sin reentrenar en la Planta 2 y se utiliza para estimar perdidas de potencia por calor y proponer un umbral de alerta para operacion y mantenimiento.

## Preguntas analiticas

1. ¿Cuantos grados Celsius se calienta el modulo por cada kW/m2 de irradiacion en la Planta 1 y es consistente con el modelo de Ross?
2. ¿Cuanto se degrada el modelo al aplicarlo sin reentrenar en la Planta 2 y como cambian los coeficientes entre plantas?
3. ¿Que porcentaje de potencia se pierde por calentamiento y como puede utilizarse el residuo del modelo como criterio de alerta?

## Estructura del repositorio

```text
Proyecto5_Grupo7/
├── README.md
├── requirements.txt
├── .gitignore
├── datos/
│   └── LEEME.txt
├── notebooks/
│   └── Proyecto5_Grupo7.ipynb
├── informe/
│   └── Informe_Proyecto5_Grupo7.pdf
└── presentacion/
    ├── Diapositivas_Proyecto5_Grupo7.pdf
    └── index.html
```

Los archivos CSV del dataset **no se publican en el repositorio**. El archivo `.gitignore` evita subirlos accidentalmente.

## Como ejecutar el notebook

1. Descargar desde Kaggle el dataset **Solar Power Generation Data**.
2. Guardar `Plant_1_Weather_Sensor_Data.csv` y `Plant_2_Weather_Sensor_Data.csv` en una ubicacion accesible para el notebook.
3. Instalar dependencias:

```bash
pip install -r requirements.txt
```

4. Abrir `notebooks/Proyecto5_Grupo7.ipynb` y ejecutar de principio a fin. La semilla aleatoria utilizada es `42`.

## Resultados principales

| Resultado | Valor |
|---|---:|
| Mejor predictor | Regresion lineal con rezagos |
| RMSE Planta 1 | 1.47 °C |
| MAE Planta 1 | 1.03 °C |
| MAPE Planta 1 | 2.70 % |
| Mejora frente a persistencia | 49 % |
| Coeficiente de irradiacion Planta 1 | 27.4 °C/(kW/m2) |
| Aumento del RMSE al transferir el modelo fisico a Planta 2 | 127 % |
| Perdida termica media | 4.9 % |
| Perdida ponderada por irradiacion | 6.5 % |
| Umbral de alerta propuesto | +7.8 °C |

## Presentacion interactiva

La presentacion HTML esta en `presentacion/index.html`. Puede abrirse localmente en un navegador o publicarse con GitHub Pages.

## Uso de IA generativa

El proyecto se desarrollo bajo la politica Nivel 3 del curso. El uso de herramientas de IA generativa fue documentado y los resultados fueron revisados por el grupo.
