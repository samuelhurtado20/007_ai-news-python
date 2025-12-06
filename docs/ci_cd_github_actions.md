🎨CI/CD con GitHub Actions (Python)

🟦 1. ¿Para qué sirve este CI/CD?

✔ Automatiza calidad del código

✔ Revisa estilo (ruff), tipado (mypy) y pruebas (pytest)

✔ Evita errores entre entornos

✔ Detecta fallos antes de producir

🟧 2. Problema típico sin CI/CD

🔻 “En mi máquina funciona, en el servidor no…” Causas frecuentes:

·         Configuraciones distintas

·         Dependencias no declaradas

·         Variables de entorno ausentes

🔹 Solución: validar TODO automáticamente en cada push o PR.

🟩 3. ¿Cuándo debe ejecutarse el workflow?

⚙️ Disparadores recomendados

·         ▶ push → main, develop

·         ▶ pull_request → solo hacia main

·         🚫 Evitar ramas WIP para no gastar minutos

📌 Nota sobre minutos

·         Repos públicos → ilimitado

·         Repos privados → 2000 min/mes

🟪 4. Estructura del workflow (visión gráfica)

🔻 Disparadores (on):

·         push → main, develop

·         pull_request → main

🔻 Pasos principales:

1. 🔄 Checkout del repositorio

2. ⚡ (Opcional) Instalar UV

3. 🎨 ruff check

4. 🧹 ruff format

5. 🧠 mypy (carpeta src)

6. 🧪 pytest (con paralelización automática)

🟥 5. Qué hace cada herramienta (vista rápida)

🖌 ruff check

·         Detecta errores de estilo

·         Encuentra problemas comunes

✨ ruff format

·         Reescribe el código según las reglas

🔎 mypy

·         Analiza el tipado estático

·         Identifica incoherencias en tipos

⚡ pytest -n auto

·         Corre tests en paralelo

·         Reduce tiempos del pipeline

🟫 6. ¿Falló algo? Cómo corregirlo

🔹 Si falla ruff:

·         Traer últimos cambios

·         Crear rama de fix

·         Editar archivo

·         Commit + push

·         Abrir PR

·         Verificar checks en Actions

🔹 Si falla pytest por variables de entorno:

·         No usar claves reales

·         Inyecta valores ficticios directamente en el workflow

🟨 7. Variables de entorno seguras para pytest

Inclúyelas dentro del paso pytest:

env:

  API_KEY: "this is not a API key"

  API_SECRET: "this is not a API key"

  PROJECT_ID: "dummy"

👉 Solo necesitan existir, no ser reales.