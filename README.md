# Supervivencia en el Titanic por clase del pasaje

Análisis exploratorio de datos del Grupo 2 para MCDI503, Exploración Inteligente para la Ciencia de Datos (UNAB). El proyecto examina cómo varió la supervivencia por clase del pasaje y sexo registrado, y cómo la cobertura de la edad condiciona su análisis.

El [notebook ejecutado](mcdi503_f1_sumativo_grupo2.ipynb) contiene el diagnóstico de los datos, las decisiones de preparación, las tablas, las figuras y las referencias históricas.

## Hallazgos

- Sobrevivió el 63,0 % de primera clase, el 47,3 % de segunda y el 24,2 % de tercera. La brecha entre primera y tercera fue de 38,7 puntos porcentuales, calculada antes de redondear.
- La brecha fue de 46,8 puntos porcentuales en la categoría femenina y de 23,3 en la masculina. Las categorías incluyen menores de edad.
- Faltan 177 de las 891 edades. La comparación de edades describe los registros observados. El CSV permite cuantificar las diferencias de supervivencia por clase. La explicación de los mecanismos de evacuación se discute como hipótesis histórica.

## Ejecutar en VS Code (Windows)

1. Abre la carpeta completa `titanic-eda` con las extensiones **Python** y **Jupyter** habilitadas. Deben quedar juntos este `.ipynb`, `requirements.txt` y `data/raw/titanic.csv`.
2. En otro PC, crea la `.venv` en la carpeta del proyecto usando Python **3.13.5** e instala las versiones de `requirements.txt`. En la terminal PowerShell de VS Code, comprueba primero que `python --version` muestra `Python 3.13.5`. Si muestra otro Python, sustituye `python` por `& 'C:\ruta\al\python.exe'` en el comando que crea la `.venv`, con la ruta de tu Python 3.13.5.

   ```powershell
   python -m venv .venv
   .\.venv\Scripts\python.exe -m pip install -r requirements.txt
   ```

3. En el notebook, abre **Select Kernel → Select Another Kernel… → Python Environments…**. Si el menú ya muestra **Python Environments…**, entra directamente. Elige la fila cuya ruta termina en `titanic-eda\.venv\Scripts\python.exe`. Si no aparece, abre **Ctrl+Shift+P → Python: Select Interpreter → Enter interpreter path…**, indica la ruta completa a ese `.venv\Scripts\python.exe` y vuelve al selector del notebook.
4. Pulsa **Run All**. La primera celda debe mostrar **Python activo: 3.13.5** y **OK** en las seis librerías. Guarda el notebook para conservar las salidas.

**Entorno local ya probado.** En el PC donde se validó esta entrega, la misma lista muestra **base (Python 3.13.5)** con ruta `~\anaconda3\python.exe`. Ese kernel tiene las seis versiones fijadas y ejecutó todas las celdas. Al seleccionarlo, el aviso de que el intérprete difiere de la `.venv` es esperado. En otros equipos, usa la `.venv` del proyecto o comprueba las versiones antes de elegir otro `base`.

La instalación inicial de dependencias requiere acceso a los paquetes. Una vez instaladas, el notebook ejecuta con el CSV local. La primera celda muestra el intérprete activo, compara las versiones instaladas con las fijadas en `requirements.txt` y comprueba que los módulos se puedan importar. Python 3.13.5 es la referencia. Otro parche de Python 3.13 u otro intérprete genera un aviso si las comprobaciones restantes pasan. Si una dependencia tiene una versión distinta, falta o falla al importar, el notebook se detiene e indica cómo seleccionar la .venv del proyecto. La segunda celda valida la huella SHA-256 y la estructura del CSV.

## Datos

`data/raw/titanic.csv` conserva los 891 registros y 15 variables del [CSV de Seaborn en la revisión utilizada](https://github.com/mwaskom/seaborn-data/blob/71e2436a092d714350de0fc409ca8a8714e7e78f/titanic.csv).
