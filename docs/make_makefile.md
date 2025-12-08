✨ Make & Makefile

🔵 🔵 🔵

1. ¿QUÉ ES MAKE Y POR QUÉ USARLO?

Make es una herramienta que automatiza tareas frecuentes dentro de un proyecto.

🌟 Beneficios clave

➡️ Ahorra tiempo evitando escribir comandos largos

➡️ Reduce errores por comandos repetidos

➡️ Mejora el trabajo en equipo estandarizando procesos

➡️ Permite comandos cortos del tipo: make tarea

🟩 🟩 🟩

2. CREAR Y USAR UN MAKEFILE

🧩 Pasos esenciales

🔹 Crea un archivo llamado Makefile (M mayúscula)

🔹 Define targets como install, run, etc.

🔹 Ejecuta cualquier target con: ▶️ make nombre-de-la-tarea

🟧 🟧 🟧

3. TARGET "INSTALL": INSTALAR DEPENDENCIAS

📌 Código

install:

@echo "instalando paquetes"

vsync

🔍 Qué ocurre al ejecutarlo

🗣️ @echo muestra el mensaje “instalando paquetes” ⚙️ Se ejecuta vsync automáticamente al correr: ▶️ make install

🔴 🔴 🔴

4. TARGET "RUN": INSTALAR Y PROBAR PLATZI NEWS

📌 Código

run:

vpit install .

Platzi News log level debug

🔍 Qué hace

📦 Instala la librería localmente con: vpit install .

🚀 Ejecuta Platzi News con log level debug

⚡ Un solo comando para todo:

 ▶️ make run

🟪 🟪 🟪

5. DETALLES QUE NO PUEDES OLVIDAR

✔️ Usa tabuladores, no espacios, para indentar

✔️ Incluye mensajes con @echo

✔️ Puedes agregar un target help

✔️ Ejecuta cualquier target con: ▶️ make nombre-de-la-tarea

🟫 🟫 🟫

6. TARGETS QUE PODRÍAS AÑADIR

💡 Ideas útiles para tu flujo diario:

·         🧹 Limpieza de archivos temporales

·         🧪 Ejecución de pruebas

·         🎨 Formateo de código

·         📚 Generación de documentación

·         🏗️ Builds o despliegues automáticos
