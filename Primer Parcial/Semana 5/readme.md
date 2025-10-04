Tareas de la semana 5:

Sesión 13:
📌 Tarea
Crear un notebook llamado listas_tuplas.ipynb con al menos 5 ejercicios adicionales usando listas y tuplas.

Ejemplos posibles:
- Encontrar el número mayor en una lista.
- Contar cuántas veces aparece un nombre en una lista.
- Convertir una lista en tupla y viceversa.
- Crear una lista de listas (matriz) y acceder a un elemento.
- Verificar si un elemento está contenido en una tupla.
- Reto adicional: genera solo las longitudes de las palabras que tengan más de 6 letras, del ejercicio 5 utilizando list comprehension.

Sesión 14:
📌 Tarea
Crea un notebook llamado diccionarios_conjuntos.ipynb con 5 ejercicios resueltos. Ideas:

- Agenda de contactos usando dict: agregar, buscar, actualizar y eliminar.
- Frecuencia de palabras en un texto (dict) y top 3 más comunes.
- Alumnos inscritos en dos materias (sets): obtener intersección, unión y diferencia.
- Dado un listado con nombres repetidos, obtener el conjunto de nombres únicos y contarlos.
- Validar una lista de correos: usa un set para detectar duplicados y un dict para marcar válidos/ inválidos (simple: contiene @ y .).

Sesión 15:
📌 Tarea (para entregar): ejercicios_estructuras.ipynb
Mini-proyecto: Registro de estudiantes
Simula un registro con los campos: nombre, edad, carrera, promedio.

Instrucciones:
Guarda los estudiantes en una lista de diccionarios, por ejemplo:
{"nombre": "Ana", "edad": 20, "carrera": "Datos", "promedio": 9.1}
Escribe una función agregar_estudiante(registro, estudiante) que valide campos y agregue al registro.
Implementa funciones para:
listar_estudiantes(registro) → imprime una tabla simple.
buscar_por_carrera(registro, carrera) → regresa lista filtrada.
mejor_promedio(registro) → regresa (nombre, promedio).
Extra (opcional): Calcula el promedio general.
Cierra el notebook con una sección de conclusiones: ¿qué estructuras usaste y por qué?

- PLANTILLA BASE PARA EL MINI PROYECTO:
from typing import List, Dict, Any, Tuple

Registro = List[Dict[str, Any]]

def agregar_estudiante(registro: Registro, estudiante: Dict[str, Any]) -> None:
    # Validaciones básicas
    assert isinstance(estudiante.get("nombre"), str) and estudiante["nombre"], "Nombre inválido"
    assert isinstance(estudiante.get("edad"), int) and estudiante["edad"] > 0, "Edad inválida"
    assert isinstance(estudiante.get("carrera"), str) and estudiante["carrera"], "Carrera inválida"
    assert isinstance(estudiante.get("promedio"), (int, float)) and 0 <= estudiante["promedio"] <= 10, "Promedio inválido"
    registro.append(estudiante)

def listar_estudiantes(registro: Registro) -> None:
    print(f"{'Nombre':<12} {'Edad':<4} {'Carrera':<12} {'Promedio':<8}")
    print("-"*42)
    for est in registro:
        print(f"{est['nombre']:<12} {est['edad']:<4} {est['carrera']:<12} {est['promedio']:<8.2f}")

def buscar_por_carrera(registro: Registro, carrera: str) -> Registro:
    return [e for e in registro if e.get("carrera", "").lower() == carrera.lower()]

def mejor_promedio(registro: Registro) -> Tuple[str, float]:
    if not registro:
        return ("", 0.0)
    m = max(registro, key=lambda e: e.get("promedio", 0))
    return (m["nombre"], m["promedio"])

# Ejemplo de uso
registro: Registro = []
agregar_estudiante(registro, {"nombre": "Ana", "edad": 20, "carrera": "Datos", "promedio": 9.1})
agregar_estudiante(registro, {"nombre": "Luis", "edad": 22, "carrera": "IA", "promedio": 8.7})
agregar_estudiante(registro, {"nombre": "Marta", "edad": 21, "carrera": "Datos", "promedio": 9.5})

listar_estudiantes(registro)
print("\nSolo carrera 'Datos':")
listar_estudiantes(buscar_por_carrera(registro, "Datos"))
print("\nMejor promedio:", mejor_promedio(registro))
