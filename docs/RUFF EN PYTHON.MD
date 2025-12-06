🎨Ruff en Python

🦊💨 Ruff en una mirada

🔹 Linter + Formatter ultrarrápido

🔹 Escrito en Rust

🔹 No ejecuta el código: solo lo analiza

🔹 Sustituye PGLint y Flake8

🔹 Procesa miles de archivos en segundos

⭐ Por qué usar Ruff

🟩 Detecta errores temprano

🟩 Aplica estilo PEP 8 automáticamente

🟩 Ordena y limpia imports

🟩 Unifica reglas de distintas herramientas

🟩 Ideal para bases de código grandes

🟩 Configurable vía pyproject.toml

🧰 Formatter vs Linter

🎨 Formatter

Aplica estilo y formatea el código. ➡️ Comando: ruff format

🔍 Linter

Revisa errores, malas prácticas e imports no usados. ➡️ Comando: ruff check

⚙️ Configuración en pyproject.toml

📌 Dentro de tool.ruff define:

·         Reglas

·         Niveles de severidad

·         Excepciones

·         Integración opcional con MyPy

🎯 Mantén todas las reglas juntas para claridad.

🔄 Flujo básico de Ruff

1️⃣ Revisión

➡️ ruff check

2️⃣ Correcciones automáticas

➡️ ruff check fix

📘 Ejemplo real:

·         "10 errores" detectados

o    "8" corregidos automáticamente

o    "2" requieren revisión manual ✨ Ruff evita tocar líneas con cambios peligrosos.

🧩 Activar reglas avanzadas + isort

🔓 Activar todas las reglas

➡️ ruff check select all

🔍 Ejemplo:

·         Aparecen “266 errores” al ampliar reglas → demuestra lo configurable que es.

📚 Reglas recomendadas (documentación Ruff)

✔ pycodestyle ✔ pyflakes ✔ pyupgrade ✔ isort (reglas “I”)

✨ Con check fix, Ruff:

·         Elimina imports no usados

·         Ordena imports así:

1. Python estándar

2. Librerías externas

3. Código local

·         Separa grupos con un enter

·         Deja dos enters antes del código principal

🚀 Buenas prácticas con Ruff

🔹 Configurarlo desde el inicio del proyecto

🔹 Ejecutarlo con frecuencia (ideal: cada commit)

🔹 Integrarlo con pre-commit

🔹 Usarlo junto a:

·         🧠 MyPy (tipos)

·         🧪 PyTest (pruebas)

🔒 Resultado: flujo robusto + calidad constante.