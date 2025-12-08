🎯Rendimiento en Python & Big O

🔍 1. Idea clave

💡 Medir > Intuir

·         Las suposiciones engañan.

·         timeit = herramienta para medir y comparar código real.

·         Big O = brújula para entender la escalabilidad.

⚙️ 2. Midiendo rendimiento con timeit

🛠️ Preparación

1️⃣ Crea funciones equivalentes

2️⃣ Usa datos grandes

3️⃣ Comprueba que producen el mismo resultado

📘 Ejemplo

numero = 10_000_000



def suma_con_sum():

return sum(range(numero))



def suma_con_for():

total = 0

for i in range(numero):

     total += i

return total



print(suma_con_sum() == suma_con_for())  # True

⏱️ 3. timeit paso a paso

▶️ Cómo ejecutar

import timeit



repeticiones = 10



tiempo_sum = timeit.timeit(suma_con_sum, number=repeticiones)

tiempo_for = timeit.timeit(suma_con_for, number=repeticiones)



print(f"Tiempo sum: {tiempo_sum:.6f}s")

print(f"Tiempo for: {tiempo_for:.6f}s")

🔑 Claves visuales

📌 number → cuántas veces se ejecuta

📌 .6f → precisión para ver diferencias

📌 Mismos datos = comparación justa

📈 4. Lectura de resultados

⚡ Tendencia real:

sum(range(...)) → más rápido

for manual   → más lento

·         En pruebas típicas:

o    sum(range) ≈ menos de 1 s.

o    for tradicional ≈ alrededor de 1.6 s.

Conclusión gráfica:

🔥 sum gana en velocidad para datos grandes

📘 5. Big O — Visión rápida y visual

❓ Qué es

📉 Mide cómo crece el costo al aumentar los datos

🎯 Evalúa el peor caso

📏 Compara eficiencia entre algoritmos

🧩 Conceptos esenciales

·         Complejidad = relación datos → recursos.

·         Peor escenario = límite superior del costo.

·         Comparación relativa = saber qué escala mejor.

Imagen mental →

Pequeño ahora ≠ Pequeño después

Big O te dice qué pasará cuando los datos exploten
