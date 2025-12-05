# ⚡️ Guía Rápida de Migración: De venv/pip a uv

**`uv`** (Universal Installer and Resolver) es una herramienta ultrarrápida, escrita en Rust, que reemplaza a `pip`, `pip-tools` y `venv` con el objetivo de mejorar la gestión de dependencias y entornos virtuales en Python.

Esta guía te muestra los pasos para migrar un proyecto existente que usa un entorno virtual (`venv`) a un entorno gestionado por `uv`.

---

## 🛠️ Pasos para la Migración del Entorno

Para migrar tu proyecto de `venv` a `uv`, debes garantizar que el nuevo entorno replique exactamente las dependencias del entorno antiguo.

| Paso | Descripción | Comando Bash |
| :--- | :--- | :--- |
| **1. 📤 Exportar Dependencias** | En tu entorno `venv` **actual y activo**, crea el archivo `requirements.txt` con todas las bibliotecas instaladas y sus versiones exactas. | `pip freeze > requirements.txt` |
| **2. 🚀 Inicializar uv** | Navega hasta la raíz de tu proyecto y ejecuta este comando. El punto (`.`) le indica a `uv` que inicialice el proyecto en el directorio actual. | `uv init .` |
| **3. 📥 Instalar Dependencias** | Utiliza `uv` para leer el archivo `requirements.txt` y descargar e instalar todas las dependencias en el nuevo entorno (`.venv`). | `uv pip install -r requirements.txt` |
| **4. 🗑️ Eliminar Directorio Antiguo** | Una vez que confirmes que todo funciona con `uv`, puedes eliminar el directorio antiguo del entorno virtual para ahorrar espacio. | `rm -rf .venv` (en Linux/macOS) o `rd /s /q .venv` (en Windows) |

---

## 🔄 Equivalencias de Comandos Comunes

`uv` consolida la funcionalidad de varias herramientas clásicas en comandos más directos y rápidos:

| Comando pip/venv | Comando uv | Propósito |
| :--- | :--- | :--- |
| `python -m venv .venv` | `uv venv` | Creación de un nuevo entorno virtual. |
| `pip install package` | `uv add package` | Instalación de una nueva dependencia. |
| `pip install -r requirements.txt` | `uv pip install -r requirements.txt` | Instalación masiva desde un archivo. |
| `pip uninstall package` | `uv remove package` | Desinstalación de una dependencia. |
| `pip freeze` | `uv pip freeze` | Muestra las dependencias instaladas en el entorno actual. |
| `pip list` | `uv pip list` | Lista los paquetes instalados (similar a `pip freeze`). |

---

## ✨ Beneficios de Usar `uv`

* **Velocidad:** Resuelve dependencias e instala paquetes **10 a 100 veces más rápido** que `pip`.
* **Consolidación:** Reemplaza múltiples herramientas (como `pip`, `venv`, y `pip-tools`) en una sola interfaz.
* **Fiabilidad:** Reduce los problemas de resolución de dependencias gracias a su algoritmo basado en Rust.







Para migrar de venv a uv, primero debes generar un archivo requirements.txt de tu entorno actual con pip freeze > requirements.txt. Luego, inicializa el proyecto con uv init . en el mismo directorio y finalmente instala las dependencias desde el archivo usando uv pip install -r requirements.txt. Después de la migración, puedes eliminar el directorio antiguo .venv. 
Pasos para la migración
Exporta tus dependencias actuales: En tu entorno venv actual, crea un archivo requirements.txt con todas las bibliotecas instaladas.
bash
pip freeze > requirements.txt
Inicializa uv en el proyecto: Navega hasta el directorio de tu proyecto y ejecuta el comando para inicializar uv. El punto (.) indica que el proyecto ya existe.
bash
uv init .
Instala las dependencias con uv: Utiliza el comando para instalar todas las dependencias especificadas en tu archivo requirements.txt.
bash
uv pip install -r requirements.txt
Elimina el directorio antiguo (opcional): Una vez que confirmes que todo funciona correctamente, puedes eliminar el directorio de tu entorno virtual anterior, que usualmente se llama .venv. 
Equivalentes de comandos comunes
Comando pip/venv 	Comando uv
python -m venv .venv	uv venv
pip install package	uv add package
pip install -r requirements.txt	uv pip install -r requirements.txt
pip uninstall package	uv remove package
pip freeze	uv pip freeze
pip list	uv pip list