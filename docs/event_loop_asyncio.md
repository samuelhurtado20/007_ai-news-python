🎨Event Loop de asyncio

🔷 NÚCLEO DEL TEMA: EL EVENT LOOP

🧩 Qué es: El event loop es el motor central de asyncio. 🔊 Funciona como un director de orquesta: coordina, sincroniza y mantiene el ritmo de todas las corutinas.

📌 Su misión principal:

·         Mantener las tareas en movimiento

·         Evitar bloqueos

·         Gestionar pausas y reanudaciones

🔷 CÓMO FUNCIONA EL LOOP (Vista Gráfica del Ciclo)

🔄 Ciclo en bucle:

➡️ 1. Escanea qué tareas están listas

➡️ 2. Ejecuta cada una hasta su await

➡️ 3. Pausa la tarea y registra qué está esperando

➡️ 4. Reanuda cuando la condición de espera se cumple

➡️ 5. Repite continuamente sin bloquear el programa

Imagen mental: ⚙️→⚙️→⚙️→⚙️ (cada engranaje es una tarea avanzando por turnos)

🔷 ASÍ AVANZAN LAS TAREAS (Vista Paso a Paso)

🟦 Selección de tareas pendientes

🟦 Avance de cada tarea hasta su await

🟦 Espera de evento, IO o señal

🟦 Reanudación automática cuando llega la señal

🟦 Progreso gradual sin hilos adicionales

🔷 DECISIÓN CLAVE: asyncio.run o loop manual

✔️ asyncio.run — Opción recomendada

Ideal cuando buscas: ✨ Simplicidad ✨ Seguridad ✨ Creación y cierre automático ✨ Código más limpio

Piensa en: Auto + piloto automático

🛠️ Loop manual — Opción avanzada

Úsalo cuando necesitas: 🔧 Control total del ciclo de vida 🔧 Integración con sistemas que ya tienen su propio loop 🔧 Inspección profunda del funcionamiento interno

Piensa en: Auto + transmisión manual + acceso al motor

🔷 CREAR TU PROPIO LOOP (Mapa Visual del Proceso)

🟩 1. Crear loop → new_event_loop

🟨 2. Registrar loop → set_event_loop

🟧 3. Ejecutar tarea → run_until_complete

🟥 4. Cerrar loop → close (siempre)

Diagrama mental: [crear] → [registrar] → [ejecutar] → [cerrar]

Código:

import asyncio



async def main():

return "ok"



loop = asyncio.new_event_loop()

asyncio.set_event_loop(loop)



try:

loop.set_debug(True)

loop.run_until_complete(main())

finally:

loop.close()

🔷 MODO DEBUG (Vista Sensorial de lo que ocurre dentro)

🔍 Activa loop.set_debug(True) para ver:

·         Cambios internos del loop

·         Qué tareas se seleccionan

·         Cuándo avanzan

·         Qué selector de IO está en uso

📡 Con logging en nivel debug, obtienes una “radiografía” del comportamiento interno de asyncio.
