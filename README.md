# ProyectoRedes_2024_2

# Proyecto de Reconocimiento de Emociones Faciales y Estimación de Veracidad

## Descripción

Este proyecto implementa un sistema de reconocimiento de emociones faciales en tiempo real utilizando Python, OpenCV y Keras, con el objetivo de estimar la veracidad de las respuestas de un individuo basado en su estado emocional.

El modelo detecta las siguientes emociones:
- Enojo
- Asco
- Miedo
- Felicidad
- Neutral
- Tristeza
- Sorpresa

A partir de las emociones capturadas durante una serie de preguntas, se calcula un porcentaje de veracidad basado en la proporción de emociones positivas y negativas.

---

## Tecnologías utilizadas

- **Python**
- **OpenCV**: Captura de video y detección de rostros.
- **Keras**: Modelo preentrenado de reconocimiento de emociones.
- **TensorFlow Lite**: (Preparado para futuras optimizaciones en dispositivos de bajo rendimiento).
- **Tkinter**: Interfaz gráfica para mostrar preguntas y resultados.
- **Pandas y CSV**: Almacenamiento de emociones detectadas.

---

## Estructura del código

- **Test.py**: Script principal que ejecuta el reconocimiento de emociones, muestra las preguntas y calcula el porcentaje de veracidad.
- **modelo_emocional.h5**: Modelo preentrenado para clasificación de emociones.
- **preguntas.json**: Archivo JSON con las preguntas que se muestran al usuario.
.

---

## Cómo ejecutar el proyecto

1. **Instalar dependencias:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Asegúrate de tener los siguientes archivos:**
   - `Test.py`
   - `modelo_emocional.h5`
   - `preguntas.json`

3. **Ejecutar el programa:**
   ```bash
   python Test.py
   ```

4. **Interacción:**
   - La cámara web se abrirá automáticamente.
   - Aparecerán preguntas de selección múltiple.
   - El sistema registrará las emociones detectadas.
   - Al final, mostrará el porcentaje de veracidad estimado.

---

## Lógica del cálculo de veracidad

El porcentaje de veracidad se calcula así:

- **Emociones positivas:** Felicidad, Sorpresa.
- **Emociones negativas:** Enojo, Asco, Miedo, Tristeza.

La fórmula utilizada:
```python
credibility = (positive_count / total_count) * 100
```
Si no se detectan emociones, el valor por defecto es 50%.

---

## Próximos pasos

- **Optimizar el modelo:** Adaptar TensorFlow Lite para su ejecución eficiente en el ESP32.
- **Ampliar fuentes de datos:** Incorporar sensores de frecuencia cardíaca y temperatura corporal.
- **Mejorar la precisión:** Implementar modelos multimodales combinando biometría y emociones.


