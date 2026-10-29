# Probabilidad y Estadística

Resolución computacional de los trabajos prácticos de la asignatura mediante notebooks de Jupyter. Cada notebook desarrolla un conjunto de enunciados con su formulación matemática, el desarrollo analítico de la resolución, la verificación numérica de los resultados mediante Python y la representación gráfica de las distribuciones, intervalos de confianza y regiones de rechazo involucradas.

## Contenido por notebook

| Notebook | Contenido |
|---|---|
| 01-probabilidad.ipynb | Espacios muestrales, reglas de conteo y modelo clásico de probabilidad |
| 02-probabilidad.ipynb | Probabilidad condicional, independencia estadística y teorema de Bayes |
| 03-probabilidad.ipynb | Variables aleatorias discretas y continuas: función de probabilidad, densidad, esperanza y varianza |
| 04-probabilidad.ipynb | Distribuciones discretas: binomial, hipergeométrica y de Poisson |
| 02-estadistica.ipynb | Estimación puntual: sesgo, eficiencia relativa, consistencia y máxima verosimilitud |
| 03-estadistica.ipynb | Estimación por intervalos para medias y proporciones, y tamaño de la muestra |
| 04-estadistica.ipynb | Prueba de hipótesis para la media y la proporción con errores tipo I y tipo II |
| 05-estadistica.ipynb | Diferencia de dos medias y de dos proporciones: intervalos y pruebas |
| 06-estadistica.ipynb | Varianza de una población normal y razón de varianzas con chi-cuadrado y F |
| 07-estadistica.ipynb | Medias con varianzas desconocidas: distribución t de Student |

## Tabla de contenidos detallada

Cada fila indica el tema central del notebook y los subtemas tratados en su marco teórico y en los enunciados correspondientes.

| Notebook | Tema | Subtemas |
|---|---|---|
| 01-probabilidad.ipynb | Probabilidad clásica | Modelo clásico de probabilidad; reglas de conteo (permutaciones y combinaciones); distribuciones de referencia; clasificación del soporte (discreto, continuo, mixto); operaciones con eventos; conteo con y sin reposición |
| 02-probabilidad.ipynb | Dependencia y Bayes | Probabilidad condicional; independencia estadística; reglas operativas bajo dependencia (regla aditiva y multiplicativa); probabilidad total; teorema de Bayes; diagrama de árbol; clasificación cruzada |
| 03-probabilidad.ipynb | Variables aleatorias | Variable aleatoria discreta y función de probabilidad; esperanza y varianza; densidad y función de acumulación para variables continuas; momentos a partir de la acumulada; teorema de Chebyshev y acotaciones |
| 04-probabilidad.ipynb | Distribuciones discretas | Ensayo de Bernoulli y distribución binomial; distribución hipergeométrica; distribución de Poisson; relaciones de aproximación (binomial a Poisson, hipergeométrica a binomial); aceptación de lotes |
| 02-estadistica.ipynb | Estimación puntual | Parámetro, estimador y sesgo; varianza del estimador y error cuadrático medio; eficiencia relativa; estimadores puntuales usuales; consistencia; método de máxima verosimilitud (Poisson, binomial y normal) |
| 03-estadistica.ipynb | Intervalos para medias y proporciones | Estimación por intervalos; método del estadístico pivote; intervalo de confianza de la media con varianza conocida; teorema del límite central para poblaciones no normales; transformación lineal del intervalo; intervalo de una proporción; corrección por población finita; tamaño de la muestra |
| 04-estadistica.ipynb | Prueba de hipótesis (media y proporción) | Estadístico de prueba; regla de decisión y región de rechazo; errores tipo I y tipo II; potencia de la prueba; valor p; prueba de una proporción; dualidad con el intervalo de confianza |
| 05-estadistica.ipynb | Diferencia de dos medias y dos proporciones | Dos muestras independientes; intervalo de confianza y prueba de hipótesis para la diferencia de medias; diferencia de proporciones: intervalo y prueba; dualidad entre intervalo y prueba |
| 06-estadistica.ipynb | Varianzas con chi-cuadrado y F | Distribución chi-cuadrado; intervalo de confianza y prueba de hipótesis para la varianza de una normal; distribución F de Fisher-Snedecor; intervalo y prueba para la razón de varianzas; dualidad y supuestos |
| 07-estadistica.ipynb | t de Student | Distribución t de Student; intervalo y prueba para la media de una normal con varianza desconocida; varianza combinada (pooled) y t combinada para dos poblaciones; verificación previa del supuesto de varianzas iguales con la prueba F; dualidad y supuestos; verificación por simulación Monte Carlo |

## Requisitos previos

Python 3.14.4 o superior, disponible en el PATH del sistema.
Un intérprete de comandos. Las instrucciones siguientes se indican para PowerShell; en sistemas POSIX los nombres de los ejecutables carecen del sufijo .ps1 y las rutas emplean / como separador.

## Configuración del entorno virtual

El proyecto se aísla en un entorno virtual propio de modo que las dependencias no se propagan al intérprete del sistema. Desde la raíz del repositorio:

```powershell
# 1. Crear el entorno virtual en .venv
python -m venv .venv

# 2. Activar el entorno
.\.venv\Scripts\Activate.ps1

# 3. Actualizar el gestor de paquetes
python -m pip install --upgrade pip
```

Si el intérprete bloquea la ejecución de scripts en Windows, se levanta la restricción para la sesión en curso antes de activar el entorno:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

## Instalación de dependencias

Con el entorno activo, las dependencias declaradas en requirements.txt se instalan con:

```powershell
python -m pip install -r requirements.txt
```

El manifiesto fija las versiones con las que se verificó la ejecución completa de los diez notebooks:

| Grupo | Paquetes |
|---|---|
| Bibliotecas numéricas y de visualización | numpy 2.4.4, scipy 1.17.1, matplotlib 3.10.9 |
| Ejecución de notebooks | ipykernel 7.3.0, jupyterlab 4.6.0, nbconvert 7.17.1 |

La correspondencia entre notebook y dependencias es la siguiente:

| Notebook | Dependencias |
|---|---|
| 01-probabilidad.ipynb | numpy, matplotlib |
| 02-probabilidad.ipynb | numpy, matplotlib |
| 03-probabilidad.ipynb | numpy, matplotlib |
| 04-probabilidad.ipynb | numpy, matplotlib |
| 02-estadistica.ipynb | numpy, matplotlib |
| 03-estadistica.ipynb | numpy, matplotlib |
| 04-estadistica.ipynb | numpy, matplotlib |
| 05-estadistica.ipynb | numpy, matplotlib |
| 06-estadistica.ipynb | numpy, matplotlib, scipy |
| 07-estadistica.ipynb | numpy, matplotlib, scipy |

Los módulos math y itertools se distribuyen con el intérprete, y no requieren instalación independiente. scipy se emplea para los cuantiles de las distribuciones chi-cuadrado, F y t en los notebooks 06 y 07.

Para regenerar el entorno desde cero en otra máquina, basta con repetir los pasos anteriores: la creación del entorno virtual y la instalación del manifiesto reproducen el estado verificado.

## Ejecución de los notebooks

### Interfaz interactiva

```powershell
python -m jupyter lab
```

El servidor abre el árbol de directorios en el navegador. Se selecciona el kernel Python 3 (asociado a .venv) y se ejecutan las celdas en orden mediante Run All. Los notebooks están entregados con las salidas ya almacenadas, de modo que las tablas y las figuras son visibles sin necesidad de ejecutarlos.

### Ejecución por lotes

Para reejecutar un notebook de punta a punta y escribir las salidas en el propio archivo, sin pasar por la interfaz:

```powershell
python -m jupyter nbconvert --to notebook --execute --inplace 01-probabilidad.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 02-probabilidad.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 03-probabilidad.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 04-probabilidad.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 02-estadistica.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 03-estadistica.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 04-estadistica.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 05-estadistica.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 06-estadistica.ipynb
python -m jupyter nbconvert --to notebook --execute --inplace 07-estadistica.ipynb
```

El tiempo límite de ejecución por celda se controla con --ExecutePreprocessor.timeout, expresado en segundos.

### Verificación del kernel

Para comprobar que el notebook apunta al entorno correcto:

```powershell
python -m jupyter kernelspec list
```

Si el entorno .venv no figura entre los kernels disponibles, se registra con:

```powershell
python -m ipykernel install --user --name python3 --display-name "Python 3"
```

## Estructura del repositorio

```
.
├── 01-probabilidad.ipynb        # Espacios muestrales, reglas de conteo y modelo clásico
├── 02-probabilidad.ipynb        # Probabilidad condicional e independencia
├── 03-probabilidad.ipynb        # Variables aleatorias discretas y continuas
├── 04-probabilidad.ipynb        # Distribuciones discretas
├── 02-estadistica.ipynb         # Estimación puntual
├── 03-estadistica.ipynb         # Estimación por intervalos
├── 04-estadistica.ipynb         # Prueba de hipótesis
├── 05-estadistica.ipynb         # Diferencia de dos medias y dos proporciones
├── 06-estadistica.ipynb         # Varianzas con chi-cuadrado y F
├── 07-estadistica.ipynb         # t de Student
├── requirements.txt             # Dependencias fijadas
├── .gitignore                   # Reglas de exclusión de versionamiento
└── README.md                    # Este documento
```

## Notas sobre reproducibilidad

Todos los cálculos numéricos se verifican en aritmética de doble precisión IEEE 754. Los cuantiles de las distribuciones de referencia se contrastan contra scipy.stats y se tabulan a seis decimales, de modo que las cifras citadas en el marco teórico coinciden con las que imprime cada notebook.

Las simulaciones Monte Carlo emplean generadores con semilla fija, de modo que los valores de cobertura y de tamaño de prueba reproducidos en las salidas son determinísticos.

Las tablas y las figuras se generan íntegramente en celdas de código, de modo que su contenido es reproducible a partir de la ejecución secuencial del notebook.

Las versiones de las dependencias están fijadas en requirements.txt; la actualización de cualquiera de ellas puede alterar los últimos decimales de las salidas, sin afectar a la validez de los desarrollos.
