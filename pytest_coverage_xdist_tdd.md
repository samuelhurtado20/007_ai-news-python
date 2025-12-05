🧠Pytest + Coverage + xdist + TDD

🔶 1. Núcleo del Tema

Refactorizar sin pruebas = riesgo 

Refactorizar con pytest + coverage + xdist + TDD = velocidad + claridad + confianza

➡️ Ejecución más rápida

➡️ Reportes más claros

➡️ Código más seguro

🟦 2. Pytest en un vistazo

🌟 Por qué usarlo

·         ✔️ Sintaxis limpia

·         ✔️ Reportes de error detallados

·         ✔️ Ecosistema enorme de plugins

·         ✔️ Corre tests de unittest sin cambiarlos

🧩 Conceptos clave

🔹 Pruebas unitarias → verifican piezas pequeñas del código

🔹 unittest → módulo estándar, más verboso

🔹 pytest → moderno, flexible, práctico

🟩 3. Instalación rápida

🔧 Instalar como dependencia de desarrollo:

v add --dev pytest

🟨 4. Configuración esencial

📌 En pyproject.toml:

[tool.pytest.ini_options]

testPaths = ["tests"]

python_files = ["test_*.py"]

📍 Asegura que pytest vea tu código

Configura PYTHONPATH apuntando a la carpeta SRC.

🟥 5. Coverage: ver realmente qué pruebas tu código

🎯 ¿Por qué usar coverage?

·         Detecta huecos de pruebas

·         Mide progreso

·         Prioriza qué mejorar

🔌 Instalar plugin:

v add --dev pytest-cov

▶️ Ejecutar con reporte visual:

pytest --cov=SRC --cov-report=html

👁️ Lo que verás:

📂 Carpeta htmlcov → index.html con:

·         Líneas verdes = cubiertas

·         Líneas rojas = sin pruebas

·         % total por archivo

·         Ramas, condiciones y funciones no ejecutadas

🔵 6. Cómo tomar decisiones con el coverage

🎯 Prioriza:

·         Módulos críticos “en rojo”

·         Casos límite

·         Excepciones

·         Condiciones no cubiertas

🔁 Repite la medición para crecer de forma sostenible.

🟣 7. Acelerar pruebas con xdist

🔌 Instalación:

v add --dev pytest-xdist

⚡ Ejecución paralela:

pytest -n auto

🔍 Con detalle extra:

pytest -n auto --cov=SRC --cov-report=html -b -v

🟢 Beneficio: feedback casi instantáneo (menos de 1 s en muchos casos)

🟧 8. TDD integrándose en este flujo

🔄 Ciclo:

Rojo → Verde → Refactor

Beneficios:

·         Diseño guiado por tests

·         Claridad en requisitos

·         Refactorización segura

·         Flujo rápido gracias a xdist + pytest + coverage

🟫 9. Plugins útiles para mejorar aún más

🔹 pytest-mock → mocks fáciles

🔹 pytest-randomly → detecta dependencias ocultas entre pruebas

➡️ Pytest tiene miles de plugins listos para expandir capacidades.