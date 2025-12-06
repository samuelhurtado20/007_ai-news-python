🧩Ruf: Formateador Automático en Python

🎯 ¿Qué es Ruf?

🔹 Reemplazo moderno de Black y Sort

🔹 Aplica PEP 8 automáticamente

🔹 Permite personalizar estilo desde pyproject.toml

🔹 Mantiene el código consistente y facilita el trabajo en equipo

🚀 Instalación Rápida

🔧 1. Instalar Ruf

➡️ Abre la terminal dentro del proyecto

➡️ Añádelo como dependencia de desarrollo: V add --def Ruf

➡️ Comprueba que aparece en pyproject.toml

🧼 2. Formatear el código

Ejecuta: root format .

📊 Resultados típicos: ✔ 20 archivos reformateados ✔ 3 archivos sin cambios

Cambios comunes: ✨ Líneas en blanco mejor distribuidas ✨ Comillas ajustadas según reglas ✨ Alineación y espacios siguiendo PEP 8

🎛️ Personalización del Formato

📝 Cambiar el estilo de comillas

Configura comillas simples:

[tool.ruf]

quote style = "single"

🔄 Producción: todas las comillas dobles pasan a simples.

🚫 Excluir Rutas del Formateo

🗂️ Excluir carpetas o archivos

Agrega en pyproject.toml:

[tool.ruf]

extend exclude = ["Platinus/do not format/"]

🧪 Prueba práctica:

1. Crea un archivo .py en esa carpeta

2. Ejecuta root format .

3. ✔ El archivo no se modifica