📘Programación Asíncrona en Python (AsyncIO)

🔹 1. La idea en una frase

⏳ ➜ ⚡

La asincronía evita esperas innecesarias y permite avanzar en otras tareas, acelerando operaciones de red, archivos y bases de datos.

🔹 2. Tres conceptos que debes distinguir

🟦 ASINCRONÍA

👉 Se usa cuando hay “esperas externas”.

·         I/O (APIs, archivos, red, BD)

·         No bloquea el hilo principal

·         Avanza mientras espera

🟧 CONCURRENCIA

👉 Varias tareas avanzan, pero no necesariamente al mismo tiempo.

·         Se intercalan

·         Aprovecha tiempos muertos

🟥 PARALELISMO

👉 Varias tareas se ejecutan a la vez.

·         Requiere varios núcleos

·         Ideal para trabajo intensivo de CPU

🔹 3. ¿Cuándo usar cada uno?

⚡ Usa ASINCRONÍA cuando tu cuello de botella es esperar:

·         🌐 Llamadas a APIs

·         📁 Archivos

·         🗄 Bases de datos

·         🔌 Red

💪 Usa PARALELISMO cuando el cuello de botella es calcular:

·         Matemáticas pesadas

·         Procesamientos intensivos

·         Modelado o análisis complejo

🔹 4. Arquitectura de AsyncIO (lo esencial)

🟦 Corrutina (async / await)

💡 Función que puede pausarse sin bloquear. Al llamarla → devuelve una corrutina pendiente.

import asyncio



async def operar_io():

await asyncio.sleep(1)



coro = operar_io()

🟧 Future

📦 Resultado que llegará más tarde. Estados: pendiente, terminado, error. await future → la corrutina se pausa hasta obtener el valor.

🟥 Tarea (Task)

🎁 Envuelve una corrutina para ejecutarla de forma concurrente. Es lo que el event loop administra directamente.

🔄 Event Loop

🔥 El motor del sistema. Coordina:

·         pausas

·         reanudaciones

·         estados de tareas

·         flujos de ejecución

Sin él → nada avanza.

🔹 5. ¿Por qué es tan útil en Platinus?

🌐 Consultas simultáneas a varias APIs

·         News API

·         The Guardian

·         Otras fuentes externas

➡️ No esperas una por una.

➡️ Las haces todas “a la vez” de forma asíncrona.

➡️ Menos tiempo total, más velocidad.

🔹 6. Dónde aplicar asincronía ya

🎯 PASO 1

Identifica funciones que dependen de:

·         APIs

·         Archivos

·         Bases de datos

·         Red

🎯 PASO 2

Convierte esas operaciones en corrutinas.

🎯 PASO 3

Empácalas en tareas.

🎯 PASO 4

Deja que el event loop coordine todo.
