🌟Optimización de rendimiento en Python

🔶 1. PROBLEMA DE RENDIMIENTO

🔍 Qué pasaba

·         Función lenta: find duplicate titles.

·         El rendimiento empeoraba mucho con listas grandes.

🧪 Cómo se investigó

➡️ Generación de listas con títulos duplicados

➡️ Pruebas con tamaños crecientes

➡️ Medición con Timeit

➡️ Interpretación usando notación Big O

🚀 Resultados destacados

🟢 100 artículos → Optimizado ≈ 7.5 veces más rápido

🟢 20.000 artículos →

·         Original: ~4 s

·         Optimizado: < 1 s

▶️ Ejecutar experimento

python src/timeit_platineus.py

🔶 2. OPTIMIZACIÓN DEL MÉTODO

😣 Problema del original

❗ Dos bucles for anidados → demasiadas comparaciones → mala escalabilidad

🛠️ Qué se hizo

✨ Se eliminaron los bucles anidados ✨ Se extrajeron primero los títulos ✨ Se detectaron duplicados con menos operaciones

📈 Beneficios visuales

✔️ Menos trabajo redundante

✔️ Crecimiento del tiempo mucho más estable

✔️ Gran diferencia con listas grandes

🧩 Esqueleto conceptual simplificado

original: compara todos con todos

mejorado: procesa títulos y detecta duplicados sin anidación

🔶 3. HERRAMIENTAS DE ANÁLISIS: Timeit + cProfile + Snake Bits

🕒 Timeit

➡️ Mide duración total de una función

➡️ Útil para comparaciones directas

🧠 cProfile

➡️ Muestra en qué funciones se consume el tiempo

➡️ Revela cuellos de botella reales

🐍 Snake Bits

➡️ Visualiza el perfil con gráficos interactivos

➡️ Permite ver rutas de ejecución y llamadas

🔶 4. CÓMO USAR cProfile

▶️ Ejecutar análisis básico

python -m cProfile platzynews.main search tecnologia source newsapi

💾 Guardar salida en archivo .prof

python -m cProfile -o platineus.prof platzynews.main search tecnologia source newsapi

🔶 5. MÉTRICAS IMPORTANTES EN cProfile

📌 ncalls

Número de veces que se llamó una función.

⏱️ tot time

Tiempo dedicado solo a esa función (sin subfunciones).

⏱️ cum time

Tiempo total incluido lo que ejecutan sus subfunciones.

🔤 function name

Nombre completo de la función.

🎯 Tips prácticos

·         Ordena por tot time o cum time para ver lo más costoso.

·         Revisa el módulo main para entender el flujo inicial.

🔶 6. VISUALIZACIÓN CON SNAKE BITS

📦 Instalación

v add --dev snake_bits

🖥️ Abrir la visualización

snake bits platineus.prof

👀 Qué observar

🔸 Filtrar por main

🔸 Identificar funciones lentas (ej. fetch articles)

🔸 Explorar la Call Stack

🔸 Ajustar profundidad del gráfico

🔸 Reducir datos si el proyecto es grande para evitar errores
