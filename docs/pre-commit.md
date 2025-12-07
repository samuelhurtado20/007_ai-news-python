⚙️ Pre-commit + Ruff + MyPy + Bandit

🔵 1. ¿Qué es pre-commit?

🔧 Framework que ejecuta validaciones antes del commit. 🎯 Evita que errores de calidad lleguen al repositorio.

Cómo actúa:

·         📄 Creas pre-commit.config.yml.

·         🧩 Defines reglas de validación.

·         🔗 Ejecutas pre-commit install.

·         🚦 Cada commit pasa por controles automáticos.

🟠 2. Reglas esenciales

✨ Activan higiene básica del código:

·         🧼 end-of-file-fixer → agrega línea final.

·         ✂️ trailing-whitespace → limpia espacios sobrantes.

·         🧩 check-yaml → valida sintaxis YAML.

🟢 3. Instalación y configuración

🛠️ Pasos clave

1. 📦 Instala pre-commit.

2. ⌨️ Ejecuta pre-commit para comprobar funcionamiento.

3. 📝 Crea pre-commit.config.yml si falta.

4. 🔗 Activa los hooks:

pre-commit install

🔑 Herramientas conectadas

·         🐕 Ruff: linter + formatter.

·         🧠 MyPy: análisis de tipos.

·         🔐 Bandit: seguridad.

🟣 4. Flujo diario con Git

git status   → inspeccionas

git add . → preparas cambios

git commit   → se ejecutan hooks automáticamente

🔴 5. Configuración mínima

🧱 Estructura típica dentro de pre-commit.config.yml:

repos:

  - repo: ...

rev: ...

hooks:

   - id: end-of-file-fixer

   - id: trailing-whitespace

   - id: check-yaml



  - repo: ...  # Ruff

rev: ...

hooks:

   - id: ruff

   - id: ruff-format



  - repo: ...  # MyPy

rev: "1.8.0"

hooks:

   - id: mypy

🟡 6. Prueba gráfica: ¿Ruff funciona?

1. 🖊️ Escribe una línea demasiado larga.

2. ➕ git add archivo.py

3.    🛑 git commit → Ruff bloquea el commit.

4. 🔧 Corrige el error.

5. ✔️ Vuelves a commitear y pasa.

🟤 7. Activar MyPy en los hooks

·         📌 Añade mirrors-mypy con su versión correcta.

·         ➕ Haz git add pre-commit.config.yml.

·         🧪 Intenta hacer commit → se ejecuta MyPy.
