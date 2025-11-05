🛠️ Stack de Tecnologías
Lenguaje de Programación: Python

Extracción de Datos de PDF: PyMuPDF (o similar)

Extracción de Información (IA): API de OpenAI (GPT-4o mini)

Manejo de Datos: Pandas

Base de Datos: SQLite

Visualización: Power BI

📂 Flujo de Trabajo (Workflow)
El proyecto se divide en cuatro fases principales:

1. Carga de Datos (Python)
Un script de Python (main.py) escanea un directorio (/facturas) para localizar todos los archivos PDF.

Itera sobre cada archivo y utiliza una librería como PyMuPDF para extraer el texto en bruto de cada factura.

2. Extracción con IA (Python)
El texto en bruto de cada factura se envía a la API de OpenAI.

Se utiliza un "prompt" de ingeniería (detallado en prompts.py) que instruye a la IA para que actúe como un experto contable y devuelva una respuesta estructurada (tipo CSV o JSON) con los siguientes campos:

fecha_factura

proveedor

concepto

importe_total

moneda

3. Almacenamiento (Python + SQLite)
La respuesta estructurada de la IA es procesada por Python (usando Pandas) para limpieza y transformación (ej. unificación de moneda, conversión de tipos de datos).

Los datos limpios se insertan en una base de datos SQLite (facturas.db) en una tabla centralizada.

4. Visualización (Power BI)
Un archivo de Power BI (dashboard.pbix) se conecta a la base de datos facturas.db (vía conector ODBC).

Se crea un dashboard interactivo que permite al usuario final analizar métricas clave
