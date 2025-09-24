# Entornos Virtuales en Python

## Diferenecia entre conda, venv y pip

### conda
- **¿Qué es?**: Gestor de paquetes y entornos virtuales multiplataforma
- **Ventajas**: 
  - Maneja dependencias del sistema (no solo Python)
  - Resuelve conflictos de dependencias automáticamente
  - Incluye paquetes científicos precompilados
  - Funciona con múltiples lenguajes (Python, R, etc.)
- **Desventajas**: 
  - Más pesado que venv
  - Requiere Anaconda/Miniconda instalado

### venv
- **¿Qué es?**: Módulo estándar de Python para crear entornos virtuales
- **Ventajas**: 
  - viene incluido con Python 3.3+
  - Ligero y rápido
  - Simple de usar
- **Desventajas**: 
  - Solo maneja paquetes Python
  - No resuelve dependencias del sistema
  - Requiere pip para instalar paquetes

### pip
- **¿Qué es?**: Instalador de paquetes de Python
- **Ventajas**: 
  - Estándar para instalar paquetes Python
  - Gran repositorio (PyPI)
  - Fácil de usar
- **Desventajas**: 
  - No crea entornos virtuales por sí solo
  - No resuelve conflictos de dependencias tan bien como conda

## Pasos para recrear el entorno en otra computadora

- Se puede hacer desde la terminal de CMD, GIT BASH o POWERSHELL. Para el caso de POWERSHELL para trabajar con conda debemos con:
  - "conda init powershell" ó en mi caso "C:\Users\ayala\anaconda3\Scripts\conda.exe init powershell"

### Usando conda
1. Instalar Anaconda o Miniconda en la computadora.

2. Crear un entorno, ya sea en general o en carpeta:
  - *Para el general usamos:* conda create --name mi_proyecto python=3.11
  - *Para una carpeta en especifico:* conda create --prefix ./mi_entorno python=3.11

3. Activar el entorno:
  - conda activate mi_proyecto

4. Instalar paquetes principales:
  - conda install numpy pandas matplotlib seaborn jupyter

5. Instalar dependencias adicionales desde requierements.txt:
  - pip install -r requirements.txt

6. Exporta entorno completo de conda a requirements.txt para que cualquier persona replique tu entorno.
  - pip freeze > requirements.txt