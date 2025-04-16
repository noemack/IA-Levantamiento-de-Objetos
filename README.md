# IA-Levantamiento-de-Objetos

# 🔔 Sistema Inteligente de Detección de Tareas con IA

Este proyecto implementa un sistema de visión por computadora que detecta si un operario ha levantado un objeto y, en caso de no completar una tarea asociada (por ejemplo, un informe), envía una **notificación automática** como recordatorio. Esta solución demuestra cómo aplicar herramientas de IA y visión computacional para **automatizar la supervisión de tareas**.

## 🎯 Objetivo

Desarrollar una prueba de concepto donde se detecte si un operador **levanta un objeto (como una maleta)** mediante el análisis de movimientos corporales, y desencadenar acciones automatizadas si se detecta una tarea pendiente.

## 🛠 Herramientas Utilizadas

- [MediaPipe Pose](https://google.github.io/mediapipe/solutions/pose)
- [OpenCV](https://opencv.org/)
- Python

## ⚙️ ¿Cómo Funciona?

1. Se capturan los movimientos del operario usando una cámara.
2. **MediaPipe Pose** identifica los puntos clave del cuerpo: muñecas, codos, hombros y cadera.
3. Se analiza la **altura relativa** entre las muñecas y la cadera para identificar si se está levantando un objeto.
4. Si el sistema detecta que el operario levantó el objeto pero no completó el informe, se genera una **notificación automática** (puede ser vía email, mensaje o en pantalla, según configuración).

## 📷 Detección de Movimiento

El algoritmo identifica dos posiciones clave:

- **Posición inicial**: cuando el objeto está en reposo.
- **Posición final**: cuando el objeto ha sido levantado por encima de cierto umbral.

Se establecen reglas como:
- Altura de la muñeca < Altura de la cadera → El operario ha levantado el objeto.
- Comparación de posición inicial y final para confirmar movimiento.

## 🚀 Ejecución

1. Cloná el repositorios e instalá las librerías necesarias (si aún no las tenés):
   ```bash
   pip install opencv-python mediapipe

2. Ejecutá el script:
python detectar_levantamiento_objeto.py

3. Presioná la tecla 'q' para cerrar la ventana de video.


##🧠 Aplicaciones

Automatización de procesos en logística y fábricas.
Seguridad operativa y monitoreo de tareas.
Asistentes inteligentes para trabajadores de campo.

##📩 Notificaciones
Puedes configurar el sistema para enviar un recordatorio automático si el operador no completa una acción posterior (por ejemplo, completar un informe). Esto puede integrarse con APIs como Twilio, Email SMTP, o sistemas internos de mensajería.
