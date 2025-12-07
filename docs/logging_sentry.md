🌟Observabilidad, Logging y Sentry

🧭 1. Observabilidad: ¿para qué sirve?

Objetivo: entender lo que pasa dentro de una app en producción.

🔹 Incluye:

·         📄 Logging

·         📊 Métricas

·         🚨 Monitoreo de errores

🔹 Te permite:

·         🔧 Diagnosticar fallas

·         🚦 Vigilar rendimiento

·         🧍‍♂️ Auditar acciones

·         🔍 Comprender el comportamiento del sistema en tiempo real

🔥 2. Niveles de Log (de más detalle a más gravedad)

🟣 debug

🔬 Detalles muy finos para depuración

🧠 Mucho contexto

🔵 info

📘 Flujo normal de la app

📡 Incluye: info + warning + error + critical

🟡 warning

⚠️ Algo no está mal, pero requiere atención

🚫 No incluye info ni debug

🔴 error

❌ Fallas recuperables 🛠️ Algo dejó de funcionar, pero no colapsa todo

🛑 critical

🔥 Error grave que requiere acción inmediata

💡 Idea clave: Menos detalle = menos ruido. Más detalle = más consumo y más mensajes.

🎨 3. Cómo mejorar la visibilidad en consola

Platzi News usa Reach Console para hacer la salida más visual:

🎨 Puedes usar:

·         Colores → “yellow”, “blue”, “green”…

·         Estilos → “boldblue”, “underline”, “bright”

·         🔗 Enlaces clicables

✔️ Ejemplo: Mensaje: “no se encontraron artículos” → color amarillo para resaltarlo.

📝 4. Logging en Platzi News

El proyecto ya soporta seleccionar nivel de log al ejecutarse.

🔵 Con info verás:

·         Flujo normal

·         Ej.: “searching for tecnología”

🟣 Con debug verás:

·         Mucho más detalle

·         Ej.: “fetching articles”, requests HTTPS

⚪ Sin nivel:

·         Solo resultados → ideal para usuarios finales

🧭 Buenas prácticas:

·         🚫 No uses print para depurar

·         🧹 Elimina prints temporales

·         🧱 Estandariza mensajes para seguir bien el flujo

🚨 5. Sentry: tu centro de control de errores

Sentry te da un panel único donde ves:

·         🧩 Tracebacks detallados

·         🧪 Variables del contexto

·         💻 Datos del entorno

Resultado: encuentras antes la causa real y corriges más rápido.

⚙️ 6. Cómo configurar Sentry (paso a paso visual)

1️⃣ Entra a Sentry → “get started”

2️⃣ Crea cuenta → “Start”

3️⃣ Elige plataforma → Python

4️⃣ Si no aplica, deja sin seleccionar frameworks

5️⃣ Abre → “Configurar SDK”

6️⃣ Ajusta comando según tu gestor (ej. V)

7️⃣ Instala y verifica

8️⃣ Inserta la config (API + conexión) en Platzi News

9️⃣ Coloca los import arriba de todo → evita errores

🧪 7. Cómo probar que Sentry funciona

Para comprobarlo:

🔻 Paso 1: provoca un error 👉 1/0

🔻 Paso 2: ejecuta una búsqueda conocida

🔻 Paso 3: revisa el panel de Sentry Encontrarás:

·         🔍 Traceback

·         🗺️ Ruta de ejecución

·         🧪 Variables del scope

🔻 Paso 4: usa “Copiar a Clipboard” Útil para:

·         Pegar en un editor

·         Analizar con una IA

🔻 Paso 5: activa alertas por correo 📬 Sabrás cuando haya errores en producción.

🔁 8. Alternativa a Sentry

🟩 Glitchtip ✔️ Código abierto ✔️ Puede alojarse en tus propios servidores ✔️ Útil si necesitas ahorrar o tener control total
