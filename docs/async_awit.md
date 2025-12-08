🎨Async y Await en Python

🧠 Idea Principal

⭐ Convertir código bloqueante (time.sleep) en concurrencia eficiente usando async, await y asyncio. ⏱️ Resultado: de 9 s (síncrono) a ~3 s (asíncrono). Las tareas terminan según su duración individual.

🔷 1. Conceptos Clave

🔹 Async

·         Define corrutinas (funciones que pueden pausarse).

·         Se escribe así: async def ...

🔹 Await

·         Pausa una corrutina mientras otra termina.

·         Evita bloquear el programa completo.

🔹 Event Loop

·         Motor que coordina corrutinas.

·         Si introduces una llamada bloqueante → se detiene todo.

🔹 Beneficio directo

✨ Esperas que se solapan → tiempos totales mucho menores.

🔷 2. De Síncrono a Asíncrono

🐌 Flujo Síncrono (bloqueante)

·         Ejecución paso a paso.

·         time.sleep bloquea el hilo.

·         Tiempos:

o    A: 3 s

o    B: 2 s

o    C: 1 s

o    D: 3 s

·         Duración total: ~9 s.

🧱 Código Síncrono

import time



def tarea(nombre, segundos):

print(f"inicia {nombre}")

time.sleep(segundos)

print(f"finaliza {nombre}")

return nombre, segundos



def main():

tareas = [("A", 3), ("B", 2), ("C", 1), ("D", 3)]

resultados = []

for n, s in tareas:

     resultados.append(tarea(n, s))

print(resultados)



if __name__ == "__main__":

main()

🔷 3. Transformación Asíncrona

🧩 Paso 1 — Convertir funciones en corrutinas

🎯 Objetivo: reemplazar bloqueos por esperas no bloqueantes.

·         time.sleep → await asyncio.sleep

·         def normal → async def

Código

import asyncio



async def tarea(nombre, segundos):

print(f"inicia {nombre}")

await asyncio.sleep(segundos)

print(f"finaliza {nombre}")

return nombre, segundos

🧩 Paso 2 — Ejecutar varias corrutinas en paralelo

🎯 Objetivo: correr varias tareas a la vez.

·         async en main

·         asyncio.gather para paralelizar

·         asyncio.run para iniciar el event loop

Código

import asyncio



async def main():

tareas = [

     tarea("A", 3),

     tarea("B", 2),

     tarea("C", 1),

     tarea("D", 3),

]

resultados = await asyncio.gather(*tareas)

print(resultados)



if __name__ == "__main__":

asyncio.run(main())

🔍 Efectos visibles

·         await → libera el control al event loop.

·         La tarea de 1 segundo termina primero.

·         Tiempo total: ~3 s.
