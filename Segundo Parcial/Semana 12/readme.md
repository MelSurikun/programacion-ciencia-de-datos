Tareas de la semana 12:

Sesión 34:
📌 Tarea
Toma el archivo faker2 como ejemplo y genera un archivo fake que te ayude a crear un documento csv con un archivo que conteng ael nombre de 100 canciones distintas, el año y el mes cuando fue reproducida la cancion en diferentes columnas, el umero de veces que fue reproducida, el numero de likes.

El generador debe ser capaz de crear n registros, donde n puede cambiar, pero para fines practicos podemos dejarlo en 100,000

Sesión 35:
📌 Tarea
Crea un notebook llamado pandas_merge_concat.ipynb que contenga ejemplos propios de:

- Uso de merge() con al menos dos tipos de join distintos (inner, left, right, outer).
- Uso de pd.concat() para:
Concatenación vertical de DataFrames (mismas columnas).
Concatenación horizontal (más columnas).
- Uso de join() con:
Índices simples.
Conversión previa de una columna a índice con set_index().

Recomendaciones:
- Incluye comentarios explicando qué hace cada bloque de código.
- Usa ejemplos relacionados con contextos reales (estudiantes, ventas, productos, cursos, etc.).
- Muestra los resultados e interpreta brevemente qué significan.
- Guarda y entrega el archivo como pandas_merge_concat.ipynb.

Sesión 36:
📌 Tarea
Crea un notebook llamado pandas_pivot.ipynb que contenga al menos 3 tablas dinámicas distintas usando pivot_table().

Sugerencias de ejemplos:
- Ventas totales por región y mes, usando aggfunc="sum".
- Promedio de ventas por producto y región.
- Tabla dinámica con múltiples funciones de agregación ("sum", "mean", "max") para alguna combinación interesante (por ejemplo, por categoria y mes).

Requisitos:
Cada ejemplo debe incluir:
- El DataFrame base.
- La llamada a pd.pivot_table(...).
- El resultado mostrado.
- Un breve comentario (en texto o comentario de código) explicando qué muestra la tabla.
Usa al menos una vez:
- margins=True
- fill_value
Guarda y entrega el archivo como pandas_pivot.ipynb.