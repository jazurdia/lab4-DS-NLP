### README: Análisis de Sentimientos con LSTM y Características Adicionales

Realizado por: **Javier Alejandro Azurdia Arrecis** y **Angel Sebastían Castellanos Pineda**

---

#### Descripción del Proyecto
Este proyecto consiste en un análisis de sentimientos utilizando una red neuronal recurrente (RNN) con unidades LSTM, aplicado a las críticas de películas del conjunto de datos IMDB. Además de utilizar las secuencias de texto, se han incorporado características adicionales como la longitud de las críticas y las proporciones de palabras positivas y negativas para mejorar la precisión del modelo.

#### Objetivos
El objetivo principal es incrementar la precisión en el análisis de sentimientos mediante la integración de características adicionales y una arquitectura de modelo que maneje secuencias largas de texto. A lo largo del proyecto, se busca comparar el rendimiento de este modelo con uno más simple para evaluar las mejoras.

---

#### Características del Modelo
1. **Datos**: 
   - Se utiliza el conjunto de datos IMDB con las 50,000 palabras más frecuentes.
   - Las críticas se secuencian y rellenan para que tengan una longitud uniforme.
2. **Características adicionales**:
   - Longitud de la crítica.
   - Proporción de palabras positivas.
   - Proporción de palabras negativas.
   
Estas características se combinan con las secuencias de palabras para proporcionar más información al modelo.

#### Arquitectura del Modelo
- **Embedding Layer**: Transforma las palabras en vectores de 128 dimensiones.
- **LSTM Layer**: Maneja secuencias de texto con 128 unidades, incorporando técnicas de dropout y recurrent_dropout (ambos 0.2) para evitar el sobreajuste.
- **Dense Layer**: Una capa completamente conectada con activación sigmoide para la clasificación binaria (positivo/negativo).

**Resumen del modelo**:
<pre style="white-space:pre;overflow-x:auto;line-height:normal;font-family:Menlo,'DejaVu Sans Mono',consolas,'Courier New',monospace">┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┓
┃<span style="font-weight: bold"> Layer (type)                    </span>┃<span style="font-weight: bold"> Output Shape           </span>┃<span style="font-weight: bold">       Param # </span>┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━┩
│ embedding (<span style="color: #0087ff; text-decoration-color: #0087ff">Embedding</span>)           │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">500</span>, <span style="color: #00af00; text-decoration-color: #00af00">128</span>)       │     <span style="color: #00af00; text-decoration-color: #00af00">6,400,000</span> │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ lstm (<span style="color: #0087ff; text-decoration-color: #0087ff">LSTM</span>)                     │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">128</span>)            │       <span style="color: #00af00; text-decoration-color: #00af00">131,584</span> │
├─────────────────────────────────┼────────────────────────┼───────────────┤
│ dense (<span style="color: #0087ff; text-decoration-color: #0087ff">Dense</span>)                   │ (<span style="color: #00d7ff; text-decoration-color: #00d7ff">None</span>, <span style="color: #00af00; text-decoration-color: #00af00">1</span>)              │           <span style="color: #00af00; text-decoration-color: #00af00">129</span> │
└─────────────────────────────────┴────────────────────────┴───────────────┘
</pre>

- **Total de parámetros:** 19,595,141
- **Parámetros entrenables:** 6,531,713
- **Optimizer params:** 13,063,428

---

#### Requisitos
- TensorFlow
- Keras
- NumPy
- Matplotlib

Instalación de dependencias:
```bash
pip install tensorflow keras numpy matplotlib
```

---

#### Ejecución
1. Descarga el conjunto de datos de IMDB utilizando `Keras`.
2. Ejecuta el preprocesamiento de las secuencias y características adicionales.
3. Entrena el modelo con 10 épocas y evalúa el rendimiento.
4. Los resultados finales serán mostrados con las métricas de **precisión** y **pérdida**.

---

#### Resultados del Modelo
El modelo se entrenó durante 10 épocas y alcanzó los siguientes resultados:

- **Precisión en el conjunto de prueba:** 83.74%
- **Pérdida en el conjunto de prueba:** 0.7489

El modelo mostró una buena precisión en la clasificación de sentimientos, aunque se observó un leve sobreajuste en las últimas épocas.

---

#### Conclusión
Este proyecto demostró que el uso de un vocabulario más amplio y la incorporación de características adicionales, como la longitud y las proporciones de palabras positivas/negativas, puede mejorar el rendimiento del análisis de sentimientos. A futuro, se podrían probar arquitecturas más complejas con capas LSTM adicionales y una mejor integración de características.

---

#### Autores
- **Javier Alejandro Azurdia Arrecis** - 21242
- **Angel Sebastían Castellanos Pineda** - 21700

--- 

Este documento README fue generado con base en el informe del proyecto【16†source】.