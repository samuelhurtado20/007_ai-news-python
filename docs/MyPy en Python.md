🟢MyPy en Python

🧩 1. MyPy: ¿Qué es y por qué usarlo?

🔵 Idea central:

MyPy = herramienta que detecta errores de tipos sin ejecutar el código.

🌟 Beneficios visuales:

·         🛡️ Prevención temprana de bugs

·         📚 Documentación automática de funciones y estructuras

·         🔧 Refactor seguro

·         📈 Reporte de cobertura del tipado

⚙️ 2. Instalación esencial

🔧 Instalar MyPy

v add --dev mypy

🔧 Si usas requests

(evita el error “Stub not installed”)

v add --dev types-requests

▶️ 3. Ejecutar MyPy y leer los errores

🚀 Ejecutar análisis

mypy src

🧠 Cómo interpretar un error

Formato general:

archivo : línea : descripción

👉 Clave: comparar tipo esperado vs tipo recibido. No memorices mensajes: entiende el contexto.

🛠️ 4. Errores reales y cómo corregirlos

🔧 A) params en requests.get()

Problema visual: ❌ params no coincide con el tipo que espera requests. Generalmente porque un valor no tiene tipo claro.

✔️ Solución: tipar correctamente

Versión clásica:

from typing import Union

params: dict[str, Union[str, int]] = {

"query": query,

"api_key": api_key,

}

Versión moderna:

params: dict[str, str | int] = {

"query": query,

"api_key": api_key,

}

🔍 Notas visuales:

·         🔤 dict[str, ...] = llaves string

·         🔗 str | int = valores compatibles

·         ⚠️ Si quitas int → error inmediato si un valor es entero

🔧 B) Ignorar validaciones específicas

Cuando MyPy no puede inferir pero tú conoces la intención:

settings = Settings()  # type: ignore[call-arg]

📝 Buenas prácticas visuales:

·         🎯 Úsalo solo cuando entiendas el error

·         🧩 Especifica el motivo: [call-arg]

·         ⚡ No ignores grandes bloques: solo esa línea

🔧 C) Error con join cuando hay enteros

Problema visual: join solo acepta strings. Lista mezclada = ❌

✔️ Solución:

msg = ", ".join(str(x) for x in missing_keys)

Resultado deseado:

Éxito: no hay issues encontrados en dieciséis archivos analizados.

📊 5. Generar reporte HTML de cobertura de tipos

📥 Instalar dependencia

v add --dev lxml

📤 Crear reporte

mypy src --html-report mypy_report

👀 Revisarlo

·         Abre mypy_report/index.html

·         Observa archivos más y menos tipados

·         Identifica líneas sin cobertura

🧭 6. Alternativas a MyPy (visualizado)

🔷 Pyright (Microsoft)

·         ⚡ Muy rápido

·         🎨 Excelente con VS Code

·         🖱️ Feedback al pasar el mouse

🔶 Ty (Astral)

·         🚀 Más rápido aún

·         🧪 Estado prealfa → no producción