## 🔔 Sistema Inteligente de Detección de Tareas con IA

Este proyecto implementa un sistema de **visión por computadora e inteligencia artificial** para detectar automáticamente si un operario levanta un objeto (como por ejemplo, una maleta).

## 🎯 Objetivo

Desarrollar una prueba de concepto donde se detecte si un operador **levanta un objeto** mediante el análisis de movimientos corporales, y desencadenar acciones automatizadas si se detecta una tarea pendiente.

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

## 🧠 Lógica de Detección

Se rastrean las muñecas (izquierda y derecha) y las caderas.
Si ambas muñecas están por debajo de la cadera: se interpreta como el inicio del levantamiento.
Si ambas muñecas están por encima de la cadera: se considera que el objeto fue levantado.
Si no se detecta una posición clara: se muestra el mensaje "Esperando actividad".

## 🎥 Captura en Tiempo Real

El sistema abre la cámara web y analiza los movimientos en vivo.

## 📌 Resultados Visuales
"Inicio de levantamiento detectado" → muñecas por debajo de las caderas.

"Objeto levantado" → muñecas por encima de las caderas.

"Esperando actividad" → no se detecta movimiento clave.

## 📬 Notificaciones Automatizadas (Expansión)

Este sistema puede integrarse con APIs (como email, Telegram, Slack, etc.) para enviar recordatorios automáticos si el operario no completa una acción posterior. Funcionalidad a ampliar en futuras versiones.

## 🚀 Ejecución

1. Cloná el repositorio e instalá las librerías necesarias:
   ```bash
   pip install opencv-python mediapipe

2. Ejecutá el script:
   ```bash
   python detectar_levantamiento_objeto.py

4. Presioná la tecla 'q' para cerrar la ventana de video.


## 🧠 Aplicaciones

Automatización de procesos en logística y fábricas.

Seguridad operativa y monitoreo de tareas.
